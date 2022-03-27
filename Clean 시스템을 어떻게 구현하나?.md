# Clean 시스템을 어떻게 구현하나?

> *시스템 제작(Construction)과 사용(Use)은 아주 다르다!*
> 

Q. 어떻게 시작해야 할까?

A. 관심사(concern)를 먼저 분리해보자. 런타임 로직에 객체 생성 로직을 섞어 놓지 말자

Q. 그렇다면 어떻게 객체를 생성하는가? 셋팅 로직과 다른 수행작업 로직은 어떻게 분리하는가?

A. **일단 Main을 분리하자.** **의존성 주입을 하자**.

ex) setter 메소드 or init(_ data: Data?) 와 같은 DI 컨테이너

**Q. 시스템 수준에서, 아키텍처 수준에서는 점진적인 발전(=확장)을 어떻게 할 수 있나?**

A-1. 관심사를 적절히 분리하여 확장 가능한 아키텍처 만들 수 있음.

 **“개별 객체나 클래스에서 메서드 호출을 감싸자”**

```swift
protocol Bank {
	func getAccounts() → [Account]
	func setAccounts(_ accounts: [Account])
}
```

```swift
class BankImplement: Bank {
	private var accounts: [Account] = []
	func getAccounts() → [Account] {
		return accounts
	}

	func setAccounts(_ accounts: [Account]) {
		accounts.forEach { self.accounts.append($0) }
	}
}
```

```swift
class BankProxyHandler: InvocationHandler {
	private var bank: Bank?
	init(_ bank: Bank) {
		self.bank = bank
	}

// InvocationHandler에 정의된 메서드
func invoke(_ proxy: Object, method: Method, args: [Object]) throws Throwable {
	let methodName = method.getName()

	switch methodName {
		case “getAccounts”:
			bank.setAccounts(args[0])
			return bank.getAccounts()

		case “setAccounts”:
			bank.setAccounts(args[0])
			setAccountsToDatabase(bank.getAccounts())
			return nil
		case “...”:
			...
	}

	func getAccountsFromDatabase() → [Account] { ... }
	func setAccountsToDatabase(_ accounts: [Accounts]) { ... }
}

```

```swift
// 프로토콜 Bank와 비즈니스 로직을 구현하는 BankImplement를 프록시로 감싼다
var bank = Proxy
	.newProxyInstance(Bank.create(), Bank(), BankProxyHandler(BankImplement()) )
```

**A-2. 테스트 주도 아키텍처 구축하자** *(= 단순하면서도 분리된 아키텍처기반으로! 일단 결과물 먼저 출시 후 → 조금씩 확장해나가는 애자일 방식으로)*

**A-3. 의사 결정을 최적화하라** *(=최대한의 정보, 최신 정보에 기반해 최선의 시점에 최적의 결정을 내려서 모듈을 나누자!)*

**A-4. 명백한 가치가 있을때 표준을 현명하게 사용하라** *(= ‘표준’이기 때문에 사용하는것보단 원래의 목적에 부합하는가 체크하기)*

**A-5. 시스템은 도메인 특화 언어가 필요하다** *(= 도메인 논리가 흐려지면 버그발생률 높고, 구현 더 어려워짐...)*

## 따라서, 시스템 역시 clean 아키텍처 필요하다