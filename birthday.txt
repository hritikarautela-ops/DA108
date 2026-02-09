from datetime import date
def calculate_age_and_birthday():
    # Get current date
    today = date.today()
    print("Current date is :", today)

    # 1. prompt for user input
    
    try:
        birth_year = int(input("Enter your birth year (YYYY):"))
        birth_month = int(input("Enter your birth month (1-12):"))
        birth_day = int(input("Enter your birth day (1-31):"))
        birth_date = date(birth_year, birth_month, birth_day)
    except ValueError as e:
        print("Invalid input. Please enter the valid numbers for year, month and day, Error: {e}")
        return
    
    # 2. Compute current age
    # Intial age calculation
    age = today.year - birth_date.year
    # Adjust age if bday hasn't happened this year
    if (today.month, today.day) < (birth_year, birth_day):
        age -= 1

    # 3. Determine the date of next birthday
    next_birthday_year = today.year
    if (today.month, today.day) >= (birth_year, birth_day):
        next_birthday_year += 1
    next_birthday = date(next_birthday_year, birth_month, birth_day)

    # calculate and display the countdown
    days_until_birthday = (next_birthday - today)

    print("Your current age is:",age)
    print("Your next birthday is on:", next_birthday)
    print("Days remaining for your next birthday:", days_until_birthday)

 # Run the function
calculate_age_and_birthday()   


                  
