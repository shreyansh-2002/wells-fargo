# wells-fargo

<!-- Here are the classes for each entity in the Wells Fargo Task 2 data model: -->
namespace WellsFargoTask2.Entities { public class Account { [Key] public int Id { get; set; }
    public string Name { get; set; }

    public string AccountNumber { get; set; }

    public decimal Balance { get; set; }

    public virtual Customer Customer { get; set; }

    public Account() {}

    public Account(string name, string accountNumber, decimal balance)
    {
        Name = name;
        AccountNumber = accountNumber;
        Balance = balance;
    }

    public virtual ICollection<Transaction> Transactions { get; set; }
}

public class Customer
{
    public int Id { get; set; }

    public string FirstName { get; set; }

    public string LastName { get; set; }

    public string DateOfBirth { get; set; }

    public string Address { get; set; }

    public string City { get; set; }

    public string State { get; set; }

    public string ZipCode { get; set; }

    public virtual ICollection<Account> Accounts { get; set; }

    public Customer() {}

    public Customer(string firstName, string lastName, string dateOfBirth, string address, string city, string state, string zipCode)
    {
        FirstName = firstName;
        LastName = lastName;
        DateOfBirth = dateOfBirth;
        Address = address;
        City = city;
        State = state;
        ZipCode = zipCode;
    }
}

public class Transaction
{
    public int Id { get; set; }

    public DateTime Date { get; set; }

    public decimal Amount { get; set; }

    public string Description { get; set; }

    public virtual Account Account { get; set; }

    public Transaction() {}

    public Transaction(DateTime date, decimal amount, string description, Account account)
    {
        Date = date;
        Amount = amount;
        Description = description;
        Account = account;
    }
}
}

