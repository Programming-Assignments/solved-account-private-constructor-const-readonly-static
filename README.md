Download Link: https://assignmentchef.com/product/solved-account-private-constructor-const-readonly-static
<br>
<h1></h1>

Description of class members

<h5><strong>Fields:</strong></h5>

<strong>CURRENT_ACCOUNT_NUMBER </strong>– this private class variable is an int representing the unique number to be used when creating a new account. This is initialized in the static constructor. This is incremented in the instance constructor

<table width="100%">

 <tbody>

  <tr>

   <td>A <strong>readonly</strong> field is like a <strong>consts</strong> but it is normally assigned when the program is running.</td>

  </tr>

 </tbody>

</table>

<table width="100%">

 <tbody>

  <tr>

   <td>A <strong>const</strong> is a value that cannot be modified. Its value is set at declaration. i.e. When the program is compiled.</td>

  </tr>

 </tbody>

</table>

<strong>Number</strong> – this public instance variable is a string indicating the current account number of this object reference. This must be decorated with the readonly keyword. This is set in the <strong>CreateAccount()</strong> method.

<strong>TRANSIT_NUMBER</strong> – this private int is a constant representing the branch number of all the accounts. That is initialized to 314. It is used in the <strong>CreateAccount()</strong> method to build the account number of this account.

<h5>Properties:</h5>

<strong>Balance</strong> – this property is a double that represents the current balance of this object. . This getter   is public and the setter is private.

<strong>Names</strong> – this property   is a list of string representing the name associated with this object. This getter   is public and the setter is private.

<h5>Constructor:</h5>

There are two constructors for this class: a static and a private one

<strong>static</strong>

<table width="100%">

 <tbody>

  <tr>

   <td>A static constructor is used to initialise the static fields and properties. It is invoked once in the life time of a program, before ANY member is accessed. There is no access modifier i.e. public, protected or private</td>

  </tr>

 </tbody>

</table>

<strong>Account()</strong> – This is the static constructor. It will be used to initialize the class variable <strong>CURRENT_ACCOUNT_NUMBER</strong> to a suitable value e.g. <strong>100000</strong>

<strong>private</strong><strong> Account(string number, string name, double balance)</strong> – This is a private constructor that does the following:

<ul>

 <li>The Number field and the Balance property are initialized to the values of the arguments</li>

 <li>The Names property is initialised to an empty list (use the new operator). And the argument is added to this collection</li>

</ul>

<h5>Methods</h5>

<strong>public void</strong><strong> AddName(string name)</strong> – This is a public method adds the argument int0 the Names collection. It is possible to have multiple names associated with this account. This method does not return a value.

<strong>public void</strong><strong> Deposit(double amount)</strong> – This is a public method that increases the property Balance by the amount specified by the argument. This method does not return a value.

<strong>public void</strong>

<table width="100%">

 <tbody>

  <tr>

   <td>The static string method Join enables you to stringify a collection. Use the following code to get string from a collection:<strong>string</strong><strong>.Join(</strong><strong>“, “</strong><strong>, Names);</strong></td>

  </tr>

 </tbody>

</table>

<strong>Withdraw(double amount)</strong> – This is a public method that decreases the property Balance by the amount specified by the argument. This method does not return a value.

<strong>public override string</strong><strong> ToString()</strong> – This is a public method overrides the corresponding method in the object class to return a stringify form of the object. To display the Names field, you will have to do some extra work because it is a list of strings []

<strong>public static</strong> <strong>Account</strong><strong> CreateAccount(string name, double balance = 0)</strong> – This is a public static method is used to create accounts. It does the following:

<ul>

 <li>Builds an account number from the <strong>TRANSIT_NUMBER</strong> and <strong>CURRENT_ACCOUNT_NUMBER</strong> according to the template “AC-[transit number]-[current account number]. e.g. if the value of <strong>TRANSIT_NUMBER</strong> and <strong>CURRENT_ACCOUNT_NUMBER</strong> are 314 and 10005 respectively then the account number will be “AC-314-10005”. [Hint: use <strong>Format()</strong> method to do this.]</li>

 <li>It also increments the <strong>CURRENT_ACCOUNT_NUMBER</strong> field so the next object will have a unique number.</li>

 <li>Instantiate a new account object with the appropriate arguments.

  <ul>

   <li>Returns the above object</li>

  </ul></li>

</ul>




<h3>Test Harness</h3>

Insert the following code statements in your Program.cs file:







List&lt;Account&gt; accounts = new List&lt;Account&gt;();

Random rand = new Random();




accounts.Add(Account.CreateAccount(“Narendra”, rand.Next(50, 500)));

accounts.Add(Account.CreateAccount(“Ilia”, rand.Next(50, 500)));

accounts.Add(Account.CreateAccount(“Yin”, rand.Next(50, 500)));

accounts.Add(Account.CreateAccount(“Arben”, rand.Next(50, 500)));

accounts.Add(Account.CreateAccount(“Patrick”, rand.Next(50, 500)));

accounts.Add(Account.CreateAccount(“Joanne”, rand.Next(50, 500)));

accounts.Add(Account.CreateAccount(“Nicoleta”, rand.Next(50, 500)));

accounts.Add(Account.CreateAccount(“Mohammed”, rand.Next(50, 500)));




Console.WriteLine(“
All accounts”);

foreach (Account account in accounts)

{

Console.WriteLine(account);

}




foreach (Account account in accounts)

{

account.Deposit(55.55);

}




Console.WriteLine(“
After $55.55 deposit “);

foreach (Account account in accounts)

{

Console.WriteLine(account);

}




foreach (Account account in accounts)

{

account.Withdraw(1.11);

if(account.Balance &gt; 300)

account.AddName(“(Hacked)”);

}




Console.WriteLine(“
After $1.11 withdrawal”);

foreach (Account account in accounts)

{

Console.WriteLine(account);

}










<h3>Test Harness</h3>

Output




All accounts

[AC-314-10000] Narendra $390.00

[AC-314-10001] Ilia $228.00

[AC-314-10002] Yin $210.00

[AC-314-10003] Arben $351.00

[AC-314-10004] Patrick $224.00

[AC-314-10005] Joanne $210.00

[AC-314-10006] Nicoleta $126.00

[AC-314-10007] Mohammed $194.00




After $55.55 deposit

[AC-314-10000] Narendra $445.55

[AC-314-10001] Ilia $283.55

[AC-314-10002] Yin $265.55

[AC-314-10003] Arben $406.55

[AC-314-10004] Patrick $279.55

[AC-314-10005] Joanne $265.55

[AC-314-10006] Nicoleta $181.55

[AC-314-10007] Mohammed $249.55




After $1.11 withdrawal

[AC-314-10000] Narendra, (Hacked) $444.44

[AC-314-10001] Ilia $282.44

[AC-314-10002] Yin $264.44

[AC-314-10003] Arben, (Hacked) $405.44

[AC-314-10004] Patrick $278.44

[AC-314-10005] Joanne $264.44

[AC-314-10006] Nicoleta $180.44

[AC-314-10007] Mohammed $248.44

Press any key to continue . . .