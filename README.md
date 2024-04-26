# PythonCode_Maths_Precalculus 
# Parabola opening upwards or downwards (y-squared):
import matplotlib.pyplot as plt
import numpy as np
def parabola_y_squared(x, a): 
    return np.sqrt(4*a*x) # Define the parabola function for y^2 = 4ax
x_values = np.linspace(0, 10, 400)# Generate x values and x must be non-negative for the square root
y_values_positive = parabola_y_squared(x_values, 1) # Generate y values for positive and negative branches
y_values_negative = -parabola_y_squared(x_values, 1) # a = 1 for example
plt.figure(figsize=(8, 6)) # Plot the parabola branches
plt.plot(x_values, y_values_positive, label='y = sqrt(4ax) - Positive branch')
plt.plot(x_values, y_values_negative, label='y = -sqrt(4ax) - Negative branch')
plt.xlabel('x') # Label the axes
plt.ylabel('y')
plt.title('Plot of the Parabola y^2 = 4ax') #  Add a title
plt.legend() # Add a legend
plt.grid(True)# Show the plot
plt.axhline(0, color='black', linewidth=0.5)
plt.axvline(0, color='black', linewidth=0.5)
plt.show()

import matplotlib.pyplot as plt
import numpy as np # Parabola opening sideways (x-squared):

def parabola_x_squared(y, a):
    return y**2 / (4*a) # Define the parabola function for x^2 = 4ay
y_values = np.linspace(-10, 10, 400)# Generate y values
x_values = parabola_x_squared(y_values, 1)# Generate x values and a = 1 for example
plt.figure(figsize=(8, 6)) # Plot the parabola
plt.plot(x_values, y_values, label='x = y^2 / (4a)')
plt.xlabel('x') # Label the axes
plt.ylabel('y')
plt.title('Plot of the Parabola x^2 = 4ay') # Add a title
plt.legend() # Add a legend
plt.grid(True) # Show the plot
plt.axhline(0, color='black', linewidth=0.5)
plt.axvline(0, color='black', linewidth=0.5)
plt.show()

# Python code to plot an ellipse 
import matplotlib.pyplot as plt
import numpy as np
def plot_shifted_ellipse(a, b, h, k): # Define the general form of an ellipse with horizontal and vertical shiftsl # ((x-h)^2 / a^2) + ((y-k)^2 / b^2) = 1
    theta = np.linspace(0, 2 * np.pi, 100) # Generate values for theta
    x = a * np.cos(theta) + h
    y = b * np.sin(theta) + k  # Parametric equations for the shifted ellipse
    c = np.sqrt(a**2 - b**2) # Calculate the distance of foci from the center (c^2 = a^2 - b^2)
    foci1 = (h + c, k)
    foci2 = (h - c, k) # Foci p
    plt.plot(x, y, label='Ellipse') # Plot the shifted ellipse.
    plt.plot(foci1[0], foci1[1], 'ro', label='Foci 1')
    plt.plot(foci2[0], foci2[1], 'ro', label='Foci 2') # Plot the foci
    plt.axis('equal') # Set equal scaling
    plt.legend() # Add a legend  
    plt.show() # Display the plot
    return foci1, foci2 # Return the foci points

foci1, foci2 = plot_shifted_ellipse(5, 3, 2, 1) # Example usage: plot a shifted ellipse with a=5, b=3, h=2 (horizontal shift), and k=1 (vertical shift)
print(f"The foci of the ellipse are located at {foci1} and {foci2}.") # Print the foci points
