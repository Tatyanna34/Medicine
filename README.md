# Medicine# BMI Calculator

def calculate_bmi(weight, height):
    """
    Calculate BMI using weight (in kilograms) and height (in meters).
    BMI = weight / (height^2)
    """
    try:
        bmi = weight / (height ** 2)
        return bmi
    except ZeroDivisionError:
        return "Height cannot be zero."
    except Exception as e:
        return f"An error occurred: {e}"

def get_user_input():
    """
    Get weight and height from the user and return them as floats.
    """
    try:
        weight = float(input("Enter weight in kilograms: "))
        height = float(input("Enter height in meters: "))
        return weight, height
    except ValueError:
        print("Invalid input. Please enter numeric values.")
        return None, None

def main():
    """
    Main function to run the BMI calculator.
    """
    print("Welcome to the BMI Calculator!")
    weight, height = get_user_input()
    if weight and height:
        bmi = calculate_bmi(weight, height)
        if isinstance(bmi, str):
            print(bmi)
        else:
            print(f"Your BMI is: {bmi:.2f}")

if __name__ == "__main__":
    main()
