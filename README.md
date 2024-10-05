# ELECTRIC-BILL-
#include <stdio.h>

int main() {
    int customerID, unitsConsumed;
    char customerName[5];
    float chargePerUnit, totalBill, surcharge = 0;

    // the user to input
    printf("Enter Customer ID: ");
    scanf("%d", &customerID);
    printf("Enter Customer Name: ");
    scanf("%s", customerName);  
    printf("Enter Units Consumed: ");
    scanf("%d", &unitsConsumed);

  
    if (unitsConsumed <= 199) {
        chargePerUnit = 1.20;
    } else if (unitsConsumed >= 200 && unitsConsumed < 400) {
        chargePerUnit = 1.50;
    } else if (unitsConsumed >= 400 && unitsConsumed < 600) {
        chargePerUnit = 1.80;
    } else {
        chargePerUnit = 2.00;
    }

    // Calculate the total bill
    totalBill = unitsConsumed * chargePerUnit;

    // the bill exceeds Ksh 400, add a 15% surcharge
    if (totalBill > 400) {
        surcharge = totalBill * 0.15;
        totalBill += surcharge;
    }

    //  the minimum bill is Ksh 100
    if (totalBill < 100) {
        totalBill = 100;
    }

    // Display output
    printf("\nCustomer ID: %d\n", customerID);
    printf("Customer Name: %s\n", customerName);
    printf("Units Consumed: %d\n", unitsConsumed);
    printf("Charge per Unit: Ksh %f\n", chargePerUnit);
    printf("Total Amount to Pay: Ksh %f\n", totalBill);

    return 0;
}
