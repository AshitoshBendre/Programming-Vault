Encapsulation involves bunding data (attributes) and methods (functions) that operate on the data into a single unit called a class. It restricts direct access to some of the object's components, typically by making attributes private or protected, and provides controlled access through public methods

```
Script Name:Program.cs

BankAccount bankAccount = new BankAccount(100);
System.Console.WriteLine(bankAccount.GetBalance());

bankAccount.Deposit(50);
System.Console.WriteLine(bankAccount.GetBalance());

bankAccount.Withdraw(100);
System.Console.WriteLine(bankAccount.GetBalance());

```

```
Script Name:BankAccount.cs

public class BankAccount
{
	private decimal balance;

	public BankAccount (decimal balance)
	{
		Deposit(balance); 
	}

	public decimal GetBalance()
	{
		return balance;
	}

	public void Deposit(decimal amount)
	{
		if(amount <=0)
		{
			throw new ArgumentException("Deposit amount must be positive");
		}
		this.balance += amount;
	}

	public void Withdraw(decimal amount)
	{
		if(amount <=0)
		{
			throw new ArgumentException("Withdrawal amount must be positive");
		}

		if(amount > balance)
		{
			throw new ArgumentException("Insufficient funds");
		}	

		this.balance -= amount;
	}

}
```