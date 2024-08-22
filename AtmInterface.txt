import java.util.Scanner;

class  Atm {
    int pin = 7071;
    double Balance=1000;

    public  void checkPin(){
        System.out.println(" Hello Customer ");
        System.out.println(" Welcome to Atm ");
        System.out.println("Please Enter your Pin");
        Scanner Sc = new Scanner(System.in);
        int PIN = Sc.nextInt();
        if (PIN == pin) {

            menu();
        }
        else {
            System.out.println("You entered wrong pin");
            System.out.println("Please Enter a valid pin");
            int PiN = Sc.nextInt();
            if (PiN==pin){
                menu();
            }
            else {
                System.out.println("You entered again wrong pin");
                System.out.println(" ");
                System.out.println("Sorry you have one more attempts");
                System.out.println(" ");
                System.out.println("Please Enter a valid pin");
                int PIn= Sc.nextInt();
                if(PIn==pin){
                    menu();
                }
                else{
                    System.out.println("Sorry you have no more attempts");
                    System.out.println("Your ATN card is blocked .");
                    System.out.println("Please contact with your branch .");
                }
            }
        }

    }

    public void menu() {
        System.out.println(" ");
        //System.out.println("HOME");
        System.out.println("1.Check Balance ");
        System.out.println("2.Deposit Money");
        System.out.println("3.Withdraw money");
        System.out.println("4.Exit");
        System.out.println("Enter your choice");
        Scanner Sc = new Scanner(System.in);
        int choice = Sc.nextInt();
        if (choice == 1) {
            checkBalance();
        } else if (choice == 2) {
            depositeMoney();

        } else if (choice == 3) {
            withdrawMoney();
        } else if (choice == 4) {
            System.out.println("Exit");
        } else {
            System.out.println("Enter a valid choice ");
        }
    }

    public void checkBalance() {
        System.out.println("Available Balance is " + Balance);
        menu();
    }

    void depositeMoney() {
        System.out.println("Enter the Amount");
        Scanner Sc = new Scanner(System.in);
        double amount = Sc.nextDouble();
        Balance =Balance+amount;
        System.out.println("Money Deposited Successfully");
        System.out.println("Available is Balance "+Balance);
        menu();
    }

    public void withdrawMoney() {
        System.out.println("Enter the Amount");
        Scanner Sc = new Scanner(System.in);
        double amount = Sc.nextDouble();

        if (amount > Balance) {
            System.out.println("Insufficient Balance");
        }
        else {
            Balance = Balance - amount;
            System.out.println("Withdrawl Successfully");
            System.out.println("Available balance is "+Balance);
        }
        menu();
    }

}

public class AtmInterface{
    public static void main(String[] args) {
        Atm a=new Atm();
        a.checkPin();
    }
}
