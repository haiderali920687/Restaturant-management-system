This is a Small Console Based project I made on Restaurant Management System using Python:

Features:

(1) Booking

(2) Room Info

(3) Restaurant

(4) Paymet

(5) Record


This is the project:

import random
# Global List Declaration

name = []
phno = []
add = []
checkin = []
checkout = []
room = []
price = []
rc = []
p = []
roomno = []
custid = []
day = []

# Global Vaariable Declaration

i = 0


# Home Function
def Home():
    print("\t\t\t\t\t\t WELCOME TO HOTEL ABCD\n")
    print("\n1. Booking \n2. Room Info \n3. Room Service \n4. Payment \n5. Record \n0. Exit")

    ch = int(input("Enter your Choice(1,2,3,4,5)"))

    if ch == 1:
        print(" ")
        Booking()

    elif ch == 2:
        print(" ")
        Rooms_Info()

    elif ch == 3:
        print(" ")
        restaurant()

    elif ch == 4:
        print(" ")
        Payment()

    elif ch == 5:
        print(" ")
        Record()

    else:
        exit()



# Booking fucntion
def Booking():
    # used global keyword to
    # use global variable 'i'
    global i
    print(" BOOKING ROOMS")
    print(" ")

    while 1:
        n = str(input("Name: "))
        p1 = str(input("Phone No.: "))
        a = str(input("Address: "))

        # checks if any field is not empty
        if n != "" and p1 != "" and a != "":
        
            name.append(n)
            add.append(a)
            break

        else:
            print("\tName, Phone no. & Address cannot be empty..!!")


    print("----SELECT ROOM TYPE----")
    print(" 1. Standard Non-AC")
    print(" 2. Standard AC")
    print(" 3. 3-Bed Non-AC")
    print(" 4. 3-Bed AC")
    print(("\t\tPress 0 for Room Prices"))

    ch = int(input("->"))

    # if-conditions to display alloted room
    # type and it's price
    if ch == 0:
        print(" 1. Standard Non-AC - Rs. 3500")
        print(" 2. Standard AC - Rs. 4000")
        print(" 3. 3-Bed Non-AC - Rs. 4500")
        print(" 4. 3-Bed AC - Rs. 5000")
        ch = int(input("->"))
    if ch == 1:
        room.append('Standard Non-AC')
        print("Room Type- Standard Non-AC")
        price.append(3500)
        print("Price- 3500")
    elif ch == 2:
        room.append('Standard AC')
        print("Room Type- Standard AC")
        price.append(4000)
        print("Price- 4000")
    elif ch == 3:
        room.append('3-Bed Non-AC')
        print("Room Type- 3-Bed Non-AC")
        price.append(4500)
        print("Price- 4500")
    elif ch == 4:
        room.append('3-Bed AC')
        print("Room Type- 3-Bed AC")
        price.append(5000)
        print("Price- 5000")
    else:
        print(" Wrong choice..!!")

    # randomly generating room no. and customer
    # id for customer
    rn = random.randrange(40) + 300
    cid = random.randrange(40) + 10

    # checks if alloted room no. & customer
    # id already not alloted
    while rn in roomno or cid in custid:
        rn = random.randrange(60) + 300
        cid = random.randrange(60) + 10

    rc.append(0)
    p.append(0)

    print("")
   
    print("\t\t\t***ROOM BOOKED SUCCESSFULLY***\n")
    
    print("Room No. - ", rn)
    
    print("Customer Id - ", cid)
    
    roomno.append(rn)
    
    custid.append(cid)
    i = i + 1
    n = int(input("0-BACK\n ->"))
    if n == 0:
        Home()
    else:
        exit()


# ROOMS INFO
def Rooms_Info():
    print("		 ------ HOTEL ROOMS INFO ------")
    print("")
    print("STANDARD NON-AC")
    print("---------------------------------------------------------------")
    print("Room amenities include: 1 Double Bed, Television, Telephone,")
    print("Double-Door Cupboard, 1 Coffee table with 2 sofa, Balcony and")
    print("an attached washroom with hot/cold water.\n")
    print("STANDARD NON-AC")
    print("---------------------------------------------------------------")
    print("Room amenities include: 1 Double Bed, Television, Telephone,")
    print("Double-Door Cupboard, 1 Coffee table with 2 sofa, Balcony and")
    print("an attached washroom with hot/cold water + Window/Split AC.\n")
    print("3-Bed NON-AC")
    print("---------------------------------------------------------------")
    print("Room amenities include: 1 Double Bed + 1 Single Bed, Television,")
    print("Telephone, a Triple-Door Cupboard, 1 Coffee table with 2 sofa, 1")
    print("Side table, Balcony with an Accent table with 2 Chair and an")
    print("attached washroom with hot/cold water.\n")
    print("3-Bed AC")
    print("---------------------------------------------------------------")
    print("Room amenities include: 1 Double Bed + 1 Single Bed, Television,")
    print("Telephone, a Triple-Door Cupboard, 1 Coffee table with 2 sofa, ")
    print("1 Side table, Balcony with an Accent table with 2 Chair and an")
    print("attached washroom with hot/cold water + Window/Split AC.\n\n")
    print()
    n = int(input("0-BACK"))
    if n == 0:
        Home()
    else:
        exit()


# RESTAURANT FUNCTION
def restaurant():
    ph = int(input("Customer Id: "))
    print("\t\t*****Menu*****")
    print("\n1. Breakfast \n2. Lunch \n3. Dinner")
    opt = 'y'
    bal = 0  # bal =0
    while (opt is 'y'):
        opt1 = int(input("Enter your choice(1,2,3)"))

        if opt1 == 1:
            print("Welcome to Breakfast Menu")
            print(
                "\n1. Omelette      Rs.50 \n2. Fried Egg     Rs.40 \n3. Tea           Rs.35\n4. Coffee        Rs.75\n5. Milkshake     Rs.80\n6. Paratha       Rs.40\n7. Sandwich      Rs.50")

            opt2 = int(input("Enter your choice(1,2,3,4,5,6,7)"))

            if opt2 == 1:
                print("You have selected Omlette")
                bal += 50

            elif opt2 == 2:
                print("you have selected Fried Egg")
                bal += 40
            elif opt2 == 3:
                print("you have selected Tea")
                bal += 35
            elif opt2 == 4:
                print("you have selected Coffee")
                bal += 75
            elif opt2 == 5:
                print("you have selected Milkshake")
                bal += 80
            elif opt2 == 6:
                print("you have selected Paratha")
                bal += 40
            elif opt2 == 7:
                print("you have selected Toast")
                bal += 40
            else:
                print("Invalid Input")

        elif opt1 == 2:
            print("Welcome to Lunch Menu")
            print(
                "\n1. Salad              Rs.150\n2. Boiled Rice        Rs.200\n3. Fried Daal         Rs.100\n4. Biryani            Rs.300\n5. Chicken Burger     Rs.500\n6. Chicken Roast      Rs.250\n7. Chicken Karhai     Rs300")

            opt3 = int(input("Enter your choice(1,2,3,4,5,6,7)"))

            if opt3 == 1:
                print("you have selected Salad")
                bal += 150

            elif opt3 == 2:
                print("you have selected Boiled Rice")
                bal += 200

            elif opt3 == 3:
                print("you have selected Fried Daal")
                bal += 100

            elif opt3 == 4:
                print("you have selected Biryani")
                bal += 300
            elif opt3 == 5:
                print("you have selected Chicken Burger")
                bal += 500

            elif opt3 == 6:
                print("you have selected Chicken Roast")
                bal += 250
            elif opt3 == 7:
                print("you have selected Chicken Karhai")
                bal += 300
            else:
                print("Invalid Input")

        elif opt1 == 3:
            print("Welcome to Dinner Menu")
            print(
                "\n1. Pizza                   Rs.500\n2. Mutton Karhai           Rs.450\n3. Kehwa                   Rs.80\n4. Kashmiri Tea            Rs.100\n5. Biryani                 Rs.300\n6. Chicken Tikka           Rs.300\n7. Chicken Roast           Rs.250")

            opt4 = int(input("Enter your choice(1,2,3,4,5,6,7)"))

            if opt4 == 1:
                print("you have selected Pizza")
                bal += 500
            elif opt4 == 2:
                print("you have selected Mutton Karhai")
                bal += 450
            elif opt4 == 3:
                print("you have selected Kehwa")
                bal += 80
            elif opt4 == 4:
                print("you have selected Kashmiri Tea")
                bal += 100
            elif opt4 == 5:
                print("you have selected Biryani")
                bal += 300
            elif opt4 == 6:
                print("you have selected Chicken Tikka")
                bal += 300
            elif opt4 == 7:
                print("you have selected Chicken Roast")
                bal += 250
            else:
                print("Invalid Input")

        else:
            print("Invalid Input")
        opt = input("Sir/Madam! do you want to order again(y/n)?")
        print("Sir/Madam! your Bill is", bal)
        print("Thanks for coming here")


# PAYMENT FUNCTION
def Payment():

    cid = str(input("Customer Id: "))
    global i
    f = 0

    for n in range(0, i):

        if cid == cid[n]:

            # checks if payment is
            # not already done
            if cid[n] == 0:
                f = 1
                print(" Payment")
                print(" --------------------------------")
                print(" MODE OF PAYMENT")

                print(" 1- Credit/Debit Card")
                print(" 2- Paytm/PhonePe")
                print(" 3- Using UPI")
                print(" 4- Cash")
                x = int(input("-> "))
                print("\n Amount: ", (price[n] * day[n]) + rc[n])
                print("\n		 Pay For AnCasa")
                print(" (y/n)")
                ch = str(input("->"))

                if ch == 'y' or ch == 'Y':
                    print("\n\n --------------------------------")
                    print("		 Hotel ABCD")
                    print(" --------------------------------")
                    print("			 Bill")
                    print(" --------------------------------")
                    print(" Name: ", name[n], "\t\n Phone No.: ", phno[n], "\t\n Address: ", add[n], "\t")
                    print("\n Check-In: ", checkin[n], "\t\n Check-Out: ", checkout[n], "\t")
                    print("\n Room Type: ", room[n], "\t\n Room Charges: ", price[n] * day[n], "\t")
                    print(" Restaurant Charges: \t", rc[n])
                    print(" --------------------------------")
                    print("\n Total Amount: ", (price[n] * day[n]) + rc[n], "\t")
                    print(" --------------------------------")
                    print("		 Thank You")
                    print("		 Visit Again :)")
                    print(" --------------------------------\n")
                    p.pop(n)
                    p.insert(n, 1)

                    # pops room no. and customer id from list and
                    # later assigns zero at same position
                    roomno.pop(n)
                    custid.pop(n)
                    roomno.insert(n, 0)
                    custid.insert(n, 0)

            else:

                for j in range(n + 1, i):
                    if cid == cid[j]:
                        if p[j] == 0:
                            pass

                        else:
                            f = 1
                            print("\n\tPayment has been Made :)\n\n")
    if f == 0:
        print("Invalid Customer Id")

    n = int(input("0-BACK\n ->"))
    if n == 0:
        Home()
    else:
        exit()


# RECORD FUNCTION
def Record():
    # checks if any record exists or not
    if phno != []:
        print("	 *** HOTEL RECORD ***\n")
        print("| Name	 | Phone No. | Address	 | Check-In | Check-Out	 | Room Type	 | Price	 |")
        print(
            "----------------------------------------------------------------------------------------------------------------------")

        for n in range(0, i):
            print("|", name[n], "\t |", phno[n], "\t|", add[n], "\t|", checkin[n], "\t|", checkout[n], "\t|", room[n],
                  "\t|", price[n])

        print(
            "----------------------------------------------------------------------------------------------------------------------")

    else:
        print("No Records Found")
    n = int(input("0-BACK\n ->"))
    if n == 0:
        Home()

    else:
        exit()


# Driver Code
Home()
