# savings-account
This program will calculate the balance of a savings account at the end of a period of time. It will use a for loop to accomplish this.

    import java.util.Scanner;
    public class HomeworkFour {
      public static void main(String[] arg) {

        //Ask the user for starting balance, monthly interest rate, and # of months since the account was created.
        System.out.println("This program will calculate the balance of your savings account. Please enter your starting"
                + " balance: ");
        Scanner sc = new Scanner(System.in);
        double startingBalance = sc.nextDouble();
        System.out.println("Please enter your monthly interest rate (as a whole number): ");
        double interestRate = sc.nextDouble();
        System.out.println("Please enter the number of months since the account has been established: ");
        int monthsPassed = sc.nextInt();
        //Declare the necessary variables for the for loop.
        double monthlyDeposit, monthlyWithdrawal, monthlyInterest;
        double accountBalance = startingBalance;
        double totalInterestEarned = 0, totalMoneyWithdrawn = 0, totalMoneyDeposited  = 0;

        //Begin the for loop: ask for amount deposited, amount withdrawn, and calculate the interest.
        for (int i = monthsPassed; i > 0; i--) {
            //Add the amount deposited to the account balance.
            System.out.println("Please enter the amount deposited this month: ");
            monthlyDeposit = sc.nextDouble();
            accountBalance += monthlyDeposit;

            //Subtract the amount withdrawn from the account balance.
            System.out.println("Please enter the amount withdrawn this month: ");
            monthlyWithdrawal = sc.nextDouble();
            accountBalance -= monthlyWithdrawal;

            //Calculate monthly interest by turning it into a decimal and multiplying it by the account balance.
            monthlyInterest = (interestRate / 100) * accountBalance;
            accountBalance += monthlyInterest;
            System.out.println("Your calculated monthly interest is $" + monthlyInterest + ", and your account" +
                    " balance thus far is $" + accountBalance);

            totalInterestEarned += monthlyInterest;
            totalMoneyWithdrawn += monthlyWithdrawal;
            totalMoneyDeposited += monthlyDeposit;

        }

        //Display the total amount of deposits made, total amount of withdrawals made, and total interest earned.
        System.out.println("Your total money withdrawn amounted to $" + totalMoneyWithdrawn +
                "\nYour total money deposited amounted to $" + totalMoneyDeposited +
                "\nYour total amount of interest earned is: $" + totalInterestEarned);
      }
    }
