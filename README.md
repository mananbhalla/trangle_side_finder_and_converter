# Input the dimensions of the triangle
l = int(input("Enter the length of the triangle: "))
B = int(input("Enter the base of the triangle: "))
H = int(input("Enter the height of the triangle: "))

def unit():
    # Ask the user for the unit of the entered data
    ask = input("Enter the unit of the following entered data (cm, m, km): ").strip().lower()
    
    if ask == "cm":
        print("Do you want to convert it into meters or kilometers?")
        ask1 = input("Type 'meter', 'kilometer', or 'no' to skip: ").strip().lower()
        if ask1 == 'meter':
            print("The new length of the triangle is", l / 100, "m")
            print("The new base of the triangle is", B / 100, "m")
            print("The new height of the triangle is", H / 100, "m")
        elif ask1 == 'kilometer':
            print("The new length of the triangle is", l / 100000, "km")
            print("The new base of the triangle is", B / 100000, "km")
            print("The new height of the triangle is", H / 100000, "km")
        else:
            print("No conversion performed.")
    
    elif ask == "m":
        print("Do you want to convert it into centimeters or kilometers?")
        ask2 = input("Type 'centimeter', 'kilometer', or 'no' to skip: ").strip().lower()
        if ask2 == 'centimeter':
            print("The new length of the triangle is", l * 100, "cm")
            print("The new base of the triangle is", B * 100, "cm")
            print("The new height of the triangle is", H * 100, "cm")
        elif ask2 == 'kilometer':
            print("The new length of the triangle is", l / 1000, "km")
            print("The new base of the triangle is", B / 1000, "km")
            print("The new height of the triangle is", H / 1000, "km")
        else:
            print("No conversion performed.")
    
    elif ask == "km":
        print("Do you want to convert it into meters or centimeters?")
        ask3 = input("Type 'meter', 'centimeter', or 'no' to skip: ").strip().lower()
        if ask3 == 'meter':
            print("The new length of the triangle is", l * 1000, "m")
            print("The new base of the triangle is", B * 1000, "m")
            print("The new height of the triangle is", H * 1000, "m")
        elif ask3 == 'centimeter':
            print("The new length of the triangle is", l * 100000, "cm")
            print("The new base of the triangle is", B * 100000, "cm")
            print("The new height of the triangle is", H * 100000, "cm")
        else:
            print("No conversion performed.")
    
    else:
        print("Invalid unit entered. Please enter 'cm', 'm', or 'km'.")

# Function to calculate L, B, or H based on area, perimeter, or volume
def calculate_missing_dimension():
    print("Do you want to calculate L, B, or H based on Area, Perimeter, or Volume?")
    ask8 = input("Type 'yes' to proceed or 'no' to skip: ").strip().lower()
    if ask8 == "yes":
        print("Please enter the type of calculation: 'A' for Area, 'P' for Perimeter, 'V' for Volume")
        ask9 = input("Enter your choice: ").strip().upper()
        if ask9 == "A":
            ask11 = input("What do you want to find out (L, B, or H)? ").strip().upper()
            if ask11 == "L":
                print("Which method do you want to use?")
                ask10 = input("Type 'herons' or 'area of triangle': ").strip().lower()
                if ask10 == "herons":
                    print("Enter the value of the perimeter:")
                    perimeter = float(input("Enter the perimeter: "))
                    print("Enter the value of the first side:")
                    side1 = float(input("Enter the first side: "))
                    print("Enter the value of the second side:")
                    side2 = float(input("Enter the second side: "))
                    # Calculate the third side using Heron's formula
                    semi_perimeter = perimeter / 2
                    side3 = semi_perimeter - side1 - side2
                    print(f"The calculated third side (L) is: {side3}")
                elif ask10 == "area of triangle":
                    print("Sorry, this method is currently not supported.")
        elif ask9 == "P":
            print("Which side do you want to find out (L, B, or H)?")
            ask12 = input("Enter the side you want to find out: ").strip().upper()
            if ask12 == "L":
                print("Enter the value of the other two sides:")
                side1 = float(input("Enter the first side: "))
                side2 = float(input("Enter the second side: "))
                perimeter = side1 + side2 + l
                print(f"The calculated perimeter is: {perimeter}")
            elif ask12 == "B":
                print("Enter the value of the other two sides:")
                side1 = float(input("Enter the first side: "))
                side2 = float(input("Enter the second side: "))
                perimeter = side1 + side2 + B
                print(f"The calculated perimeter is: {perimeter}")
            elif ask12 == "H":
                print("Enter the value of the other two sides:")
                side1 = float(input("Enter the first side: "))
                side2 = float(input("Enter the second side: "))
                perimeter = side1 + side2 + H
                print(f"The calculated perimeter is: {perimeter}")
        elif ask9 == "V":
            print("What do you want to find out (L, B, or H)?")
            ask13 = input("Enter the side you want to find out: ").strip().upper()
            if ask13 == "L":
                print("Enter the height and base to calculate the volume:")
                height = float(input("Enter the height: "))
                base = float(input("Enter the base: "))
                volume = (1 / 3) * base * height * l
                print(f"The calculated volume is: {volume}")
            elif ask13 == "B":
                print("Enter the height and base to calculate the volume:")
                height = float(input("Enter the height: "))
                base = float(input("Enter the base: "))
                volume = (1 / 3) * base * height * B
                print(f"The calculated volume is: {volume}")
            elif ask13 == "H":
                print("Enter the height and base to calculate the volume:")
                height = float(input("Enter the height: "))
                base = float(input("Enter the base: "))
                volume = (1 / 3) * base * height * H
                print(f"The calculated volume is: {volume}")
        else:
            print("Invalid choice. Please try again.")
    else:
        print("No calculation performed.")

# Run the program in a loop
while True:
    unit()
    repeat = input("Do you want to perform another conversion or calculation? (yes or no): ").strip().lower()
    if repeat != "yes":
        calculate_missing_dimension()
        print("Exiting the program. Goodbye!")
        break
