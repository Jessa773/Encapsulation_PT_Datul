# Encapsulation_PT_Datul
<?php
class BankAccount {
    private $accountHolderName;
    private $accountNumber;
    private $balance;

    
    public function __construct($accountHolderName, $accountNumber, $balance) {
        $this->accountHolderName = $accountHolderName;
        $this->accountNumber = $accountNumber;
        $this->balance = $balance;
    }


    public function getAccountHolderName() {
        return $this->accountHolderName;
    }

    public function getAccountNumber() {
        return $this->accountNumber;
    }

    public function getBalance() {
        return $this->balance;
    }

    
    public function setBalance($balance) {
        $this->balance = $balance;
    }

    
    public function deposit(float $amount) {
        if ($amount > 0) {
            $this->balance += $amount;
        }
    }

    
    public function withdraw(float $amount) {
        if ($amount > 0 && $amount <= $this->balance) {
            $this->balance -= $amount;
        }
    }

    
    public function displayAccountInfo() {
        echo "Account Holder Name: " . $this->getAccountHolderName() . "\n";
        echo "<br>";
        echo "Account Number: " . $this->getAccountNumber() . "\n";
        echo "<br>";
        echo "Balance: " . $this->getBalance() . "\n";
        echo "<br>";
    }
}


$account = new BankAccount("Jessa Dy", "19-2027-26", 500.00);
echo "<br>";
echo "Initial Account Information:\n";
echo "<br>";
$account->displayAccountInfo();

$account->deposit(500);
echo "<br>";
$account->withdraw(200);

echo "\nAccount Information After Transactions:\n";
echo "<br>";
$account->displayAccountInfo();
echo "----------------------------------";
$account = new BankAccount("Macs Dy", "92-1976-12", 1000.00);
echo "<br>";
echo "Initial Account Information:\n";
echo "<br>";
$account->displayAccountInfo();

$account->deposit(100);
echo "<br>";
$account->withdraw(500);

echo "\nAccount Information After Transactions:\n";
echo "<br>";
$account->displayAccountInfo();
echo "----------------------------------";
$account = new BankAccount("Maxine Dy", "10-1975-26", 10000.00);
echo "<br>";
echo "Initial Account Information:\n";
echo "<br>";
$account->displayAccountInfo();

$account->deposit(10);
echo "<br>";
$account->withdraw(4000);

echo "\nAccount Information After Transactions:\n";
echo "<br>";
$account->displayAccountInfo();
echo "-----------------------------------";
$account = new BankAccount("Alexandra Mills", "76-6412-54", 1000000.00);
echo "<br>";
echo "Initial Account Information:\n";
echo "<br>";
$account->displayAccountInfo();

$account->deposit(0);
echo "<br>";
$account->withdraw(500000);

echo "\nAccount Information After Transactions:\n";
echo "<br>";
$account->displayAccountInfo();
echo "---------------------------------";
$account = new BankAccount("Keifer Ellen ", "74-6845-84", 50000.00);
echo "<br>";
echo "Initial Account Information:\n";
echo "<br>";
$account->displayAccountInfo();

$account->deposit(50000);
echo "<br>";
$account->withdraw(20000);

echo "\nAccount Information After Transactions:\n";
echo "<br>";
$account->displayAccountInfo();
?>
