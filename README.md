# Welcome to the Fund Flow Optimizer System README !!

This system minimizes the number of transactions among multiple banks in the different corners of the world that use different modes of payment. There is one world bank (with all payment modes) to act as an intermediary between banks that have no common mode of payment.


## Getting Started

Let's take an example. say we have the following banks:
1. Bank_Of_America (World Bank)
2. Wells_Fargo
3. Royal_Bank_of_Canada
4. Westpac
5. National_Australia_Bank
6. Goldman_Sachs

Following are the payments to be done:

1. Goldman_Sachs              Bank_of_America             Rs 100
2. Goldman_Sachs              Wells_Fargo                 Rs 300
3. Goldman_Sachs              Royal_Bank_of_Canada        Rs 100
4. Goldman_Sachs              Westpac                     Rs 100
5. National_Australia_Bank    Bank_of_America             Rs 300
6. National_Australia_Bank    Royal_Bank_of_Canada        Rs 100
7. Bank_of_America            Wells_Fargo                 Rs 400  
8. Wells_Fargo                Royal_Bank_of_Canada        Rs 200 
9. Royal_Bank_of_Canada       Westpac                     Rs 500

But there's a catch!! Each Bank only supports a set of modes of payments and can make or receive payments only via those. Only World Bank suppports all modes of payments. In our current example we have only three payment modes :
1. Google_Pay
2. AliPay
3. Paytm


Following is the list of Banks and their supported payment modes :

1. Bank_of_America          -   Google_Pay, AliPay, Paytm
2. Wells_Fargo              -   Google_Pay, AliPay
3. Royal_Bank_of_Canada     -   AliPay
4. Westpac                  -   Google_Pay, Paytm
5. Goldman_Sachs            -   Paytm
6. National_Australia_Bank   -   AliPay, Paytm

To pick the first Bank, we calculate the net amount for every Bank by using the below formula and store them in list:

net amount = [Sum of all credits(amounts to be received)] - [Sum of all debits(amounts to pay)]

Now the idea is that we are finding the bank which has minimum net amount(max debtor) (say Bank X, net amount x) and then finding the bank which has the maximum net amount( max creditor) (say Bank Y, net amount y) and also has a common payment mode (say M1) with the former bank. Then we find minimum of absolute value of x and y, lets call it z.
Now X pays the amount z to Y. Then 3 cases may arrived:

1. If (magnitude of x) < y => X is completely settled and so removed from the list.
2. If (magnitude of x) > y => Y is completely settled and so removed from the list.
3. If (magnitude of x) = y => X and Y both are completely settled and so both are removed from the list.

The same process is repeated for the remaining banks.




## How To USe

This system is completely menu-driven. So when you will run the C++ Application, it will guide you and show you the final output.
