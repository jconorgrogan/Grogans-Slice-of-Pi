## Theorem
Let \( R = 2^n \) for some positive integer \( n \). Consider a circle of radius \( R \) centered at the origin. Divide the circle into \( 2R \) equal slices. The \( y \)-coordinate of the first slice's intersection point above the \( x \)-axis approaches \( \pi \) as \( n \rightarrow \infty \).

### Definitions and Assumptions
1. Define \( R = 2^n \) where \( n \) is a positive integer.
2. Consider a circle of radius \( R \) centered at the origin.
3. Divide the circle into \( 2R \) equal slices.
4. The angle for each slice is \( \theta = \frac{2\pi}{2R} = \frac{\pi}{R} \).

### Y-Coordinate Expression
The \( y \)-coordinate for the first slice's intersection point above the \( x \)-axis in Cartesian coordinates is \( y = R \sin(\theta) \). Substituting \( \theta = \frac{\pi}{R} \) and \( R = 2^n \), we get \( y = 2^n \sin\left(\frac{\pi}{2^n}\right) \).

### Limit Calculation
We want to find \( \lim_{n \to \infty} 2^n \sin\left(\frac{\pi}{2^n}\right) \).

Substitute \( u = \frac{\pi}{2^n} \) and \( 2^n = \frac{\pi}{u} \), so \( u \to 0 \) as \( n \to \infty \).

The limit becomes \( \lim_{u \to 0} \frac{\pi}{u} \sin(u) \).

Utilizing the limit identity \( \lim_{u \to 0} \frac{\sin(u)}{u} = 1 \), the limit is \( \pi \).


### Code to demonstrate

import numpy as np
import matplotlib.pyplot as plt
import math

def f(n):
    return 2**n * math.sin(math.pi / 2**n)

n_values = range(1, 100)
y_values = [f(n) for n in n_values]

plt.plot(n_values, y_values, label='$2^n \\sin(\\frac{\\pi}{2^n})$')
plt.axhline(y=math.pi, color='r', linestyle='--', label='$\\pi$')
plt.xlabel('n')
plt.ylabel('y-coordinate')
plt.legend()
plt.show()

approaches_pi = math.isclose(y_values[-1], math.pi, rel_tol=1e-6)

approaches_pi, y_values[-1]

![image](https://github.com/jconorgrogan/Grogans-Slice-of-Pi/assets/130090573/bed128bf-b7ac-45d1-9fc7-805c611892bd)


4. **Conclusion**:
    - Therefore, the \( y \)-coordinate of the first slice's intersection point above the \( x \)-axis approaches \( \pi \) as \( n \rightarrow \infty \).

5. **Additional Commentary**:
Each of these horizontal lines approaches a multiple of pi as R goes to infinity
![image](https://github.com/jconorgrogan/Grogans-Slice-of-Pi/assets/130090573/2a204d04-0238-44ed-a5f4-a91fe5c68617)


As R increases, each 2nd node y coordinate moves towards 2pi, 3rd node 3pi, etc. 
How each point converges to these multiples of pi creates some extremely interesting fractals which are worthy of future research

The infinite prime ladder, and the Grogan Rollercoaster 
![image](https://github.com/jconorgrogan/Grogans-Slice-of-Pi/assets/130090573/f45b1293-16f1-41fd-abdf-ead3df0f4284)

