import java.util.Scanner;

class ATM {
    private double balance = 1000;

    public void deposit(double amount) {
        balance += amount;
        System.out.println("Deposited: $" + amount);
    }

    public void withdraw(double amount) {
        if (amount > balance) System.out.println("Insufficient funds.");
        else {
            balance -= amount;
            System.out.println("Withdrawn: $" + amount);
        }
    }

    public void checkBalance() {
        System.out.println("Balance: $" + balance);
    }
}

public class ATMSystem {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        ATM atm = new ATM();

        while (true) {
            System.out.println("\n1. Deposit\n2. Withdraw\n3. Balance\n4. Exit");
            int choice = scanner.nextInt();

            if (choice == 1) {
                System.out.print("Amount: ");
                atm.deposit(scanner.nextDouble());
            } else if (choice == 2) {
                System.out.print("Amount: ");
                atm.withdraw(scanner.nextDouble());
            } else if (choice == 3) {
                atm.checkBalance();
            } else break;
        }
    }
}
