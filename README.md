# Calorie_Counter
Calorie counter python program based on weight range and gender.

# Global Constants
GAIN_WEIGHT = 1
LOSE_WEIGHT = 2
WEIGHT_PROGRAM = 0
DISPLAY_PROGRAM ='cccc'

# variables
weight = 0
daily_cal_intake = 0
keep_going = 'y'
male = 'm'
female = 'f'
unknown = 'u'
gender ='dddd'


def main():
    welcome()

    keep_going = 'y'

    while keep_going =='y':
        print('***********************************************')
        WEIGHT_PROGRAM = float(input('Enter 1 for weight gain program, enter 2 for weight loss program: '))

        if WEIGHT_PROGRAM == 1:
            add_weight()

        elif WEIGHT_PROGRAM == 2:
            shed_weight()

        else:
            print('Please enter a valid option to begin the program.')
        print( )
        keep_going = input('Would you like to select a new program? Enter y for yes or 0 to end program: ')



# Weight Gain program
def add_weight():

# User inputs weight, and program calculates daily calorie intake
    keep_going = 'y'

    while keep_going == 'y':

        try:
            print( )
            weight = int(input('Please enter current weight: '))
            print( )

            if weight<0:
                print('You cant weigh less than 0lbs.')
                print( )

            elif weight > 300:
                print('I am not sure if I can legally promote this, please contact a medical professional for advice.')
                print( )

            else:
                daily_cal_intake = weight * 20
                print('***********************************************')
                print('Your new daily calorie intake should be',format(daily_cal_intake, '5,d'))
                print( )

            keep_going = input('Would you like to calculate an additional weight gain program?' +
                            ' (Enter y for yes): ')

        except ValueError:
                print('ERROR: weight must be a valid number')
                print( )



#Weight Loss Program
def shed_weight():

# User inputs weight, gender, and program calculates daily calorie intake
    keep_going = 'y'

    while keep_going == 'y':

        try:
            print( )
            weight = int(input('Please enter current weight: '))
            print( )

            if weight<95:
                print('I am not sure if I can legally promote this, please contact a medical professional for advice.')
                print( )

            gender = str(input( 'Enter m for male, f for female, or u for unknown: '))

            if gender == male:
                daily_cal_intake = 2600 - 500
                print('Your new daily calorie intake should be',format(daily_cal_intake, '5,d'))
                print( )
                print('***********************************************')

            elif gender == female:
                daily_cal_intake = 2000 - 500
                print('Your new daily calorie intake should be',format(daily_cal_intake, '5,d'))
                print( )
                print('***********************************************')

            elif gender == unknown:
                daily_cal_intake = 2300 - 500
                print('Your new daily calorie intake should be',format(daily_cal_intake, '5,d'))
                print( )
                print('***********************************************')
            else:
                print('Not a vaild option for gender.')
                print( )
            keep_going = input('Would you like to calculate an additional weight loss program?' +
                        ' (Enter y for yes): ')
            print('***********************************************')

        except:
            print('***********************************************')
            print('ERROR OCCURED')
            print( )


#Welcome message
def welcome():
    print('Hello, welcome to Get Fit Calorie Calculator')
    print('Please follow the instrucitons below.')
    print('***********************************************')
    DISPLAY_PROGRAM = ('Gain Weight or, Lose Weight')
    print ('Here are the programs we offer -' ,DISPLAY_PROGRAM)
    print('***********************************************')


main()
