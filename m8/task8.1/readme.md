# Task 8.1

## solv_square_equation

```
import math

def validate_param():
    check_input = 3
    while check_input > 0:
        try:
            a = int(input("Enter a: "))
            b = int(input("Enter b: "))
            c = int(input("Enter c: "))
        except ValueError:
            print("Please make sure the coefficients are real numbers and try again")
            check_input -= 1
            continue;
        else:
            return a, b, c

def discriminant(a,b,c):
    dis = b ** 2 - (4 * a * c)
    return dis

def roots(dis,a,b,c):
    if dis > 0:
        x1 = (-b + math.sqrt(dis)) / (2 * a)
        x2 = (-b - math.sqrt(dis)) / (2 * a)
        print("x1 = %.2f \nx2 = %.2f" % (x1, x2))
        return (x1, x2)
    elif dis == 0:
        x = -b / (2 * a)
        print("x = %.2f" % x)
        return x
    else:
        print("Equation has no roots")

def solv_square(a,b,c):
    dis = discriminant(a,b,c)
    root = roots(dis,a,b,c)
    print("Discriminant = ", dis)
    return root

def squere_print(a,b,c,roots):
    print("a =", a)
    print("b =", b)
    print("c =", c)
    roots

def main():
    print("Please enter values for quadratic equation: ")
    abc = validate_param()
    a = abc[0]
    b = abc[1]
    c = abc[2]
    solv_square(a,b,c)
    squere_print(a,b,c,roots)

main()
```

## Unittest
```
from unittest import TestCase

import solv_square_equation


class Test(TestCase):
    def test_discriminant(self):
        self.assertEqual(solv_square_equation.discriminant(1,-26,120), 196)

    def test_roots(self):
        self.assertEqual(solv_square_equation.roots(196,1,-26, 120), (20.00,6.00))

    def test_solv_square(self):
        self.assertEqual(solv_square_equation.solv_square(1,-26,120), (20.00,6.00))

if __name__ == '__main__':
    unittest.main()
```
