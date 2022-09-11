import math


# type of formula
type = float(input("\n if you want a general formula type 1, if you want a compound formula type 2, if you want a continuous formula type 3: "))


#inital amount (p or a)
init = float(input("\n The Inital Amount: "))


# Growth rate (r)
rate = float(input("\n The Growth Rate: "))


# Time in years (t)
time = float(input("\n The Time: "))


#compound period (n)
if type == 2:
    period = float(input("\n The Compound Period: "))


# round bool
roundY = float(input("\n if you would like your result rounded type 1, if not type 2: "))


#Product (y or A)
Y = 0 

def GeneralFormula(Y, a, r, t):  

    Y = a * math.pow((1 + r), t) # formula

    if roundY == 1:
        return round(Y)
    else:
        return Y

def CompoundFormula(Y, a, r, t, n): 

    Y = a * math.pow((1 + (r/n)), n * t) # formula
    
    if roundY == 1:
        return round(Y)
    else:
        return Y

def ContinuousFormula(Y, a, r, t): 

    Y  = a * math.pow(math.e, r * t)

    if roundY == 1:
        return round(Y)
    else:
        return Y





if type == 1:
    print("\n\n General Formula: Y =", GeneralFormula(Y, init, rate, time))
elif type == 2:
    print("\n\n Compound Formula: Y =",CompoundFormula(Y, init, rate, time, period))
elif type == 3:
    print("\n\n Continuous Formula: Y =",ContinuousFormula(Y, init, rate, time))
