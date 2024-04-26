# PythonCode_Maths
# Precalculus 
# Parabola opening upwards or downwards (y-squared):
import matplotlib.pyplot as plt
import numpy as np
# Define the parabola function for y^2 = 4ax
def parabola_y_squared(x, a):
    return np.sqrt(4*a*x)
# Generate x values
x_values = np.linspace(0, 10, 400)  # x must be non-negative for the square root
# Generate y values for positive and negative branches
y_values_positive = parabola_y_squared(x_values, 1)  # a = 1 for example
y_values_negative = -parabola_y_squared(x_values, 1)
# Plot the parabola branches
plt.figure(figsize=(8, 6))
plt.plot(x_values, y_values_positive, label='y = sqrt(4ax) - Positive branch')
plt.plot(x_values, y_values_negative, label='y = -sqrt(4ax) - Negative branch')
# Label the axes
plt.xlabel('x')
plt.ylabel('y')
# Add a title
plt.title('Plot of the Parabola y^2 = 4ax')
# Add a legend
plt.legend()
# Show the plot
plt.grid(True)
plt.axhline(0, color='black', linewidth=0.5)
plt.axvline(0, color='black', linewidth=0.5)
plt.show()
# Parabola opening sideways (x-squared):
import matplotlib.pyplot as plt
import numpy as np
# Define the parabola function for x^2 = 4ay
def parabola_x_squared(y, a):
    return y**2 / (4*a)
# Generate y values
y_values = np.linspace(-10, 10, 400)
# Generate x values
x_values = parabola_x_squared(y_values, 1)  # a = 1 for example
# Plot the parabola
plt.figure(figsize=(8, 6))
plt.plot(x_values, y_values, label='x = y^2 / (4a)')
# Label the axes
plt.xlabel('x')
plt.ylabel('y')
# Add a title
plt.title('Plot of the Parabola x^2 = 4ay')
# Add a legend
plt.legend()
# Show the plot
plt.grid(True)
plt.axhline(0, color='black', linewidth=0.5)
plt.axvline(0, color='black', linewidth=0.5)
plt.show()
# Python code to plot an ellipse 
import matplotlib.pyplot as plt
import numpy as np
# Define the general form of an ellipse with horizontal and vertical shifts
# ((x-h)^2 / a^2) + ((y-k)^2 / b^2) = 1
def plot_shifted_ellipse(a, b, h, k):
 # Generate values for theta
    theta = np.linspace(0, 2 * np.pi, 100)
 # Parametric equations for the shifted ellipse
    x = a * np.cos(theta) + h
    y = b * np.sin(theta) + k  
# Calculate the distance of foci from the center (c^2 = a^2 - b^2)
    c = np.sqrt(a**2 - b**2)
  # Foci points
    foci1 = (h + c, k)
    foci2 = (h - c, k)
   # Plot the shifted ellipse.
    plt.plot(x, y, label='Ellipse')
   # Plot the foci
    plt.plot(foci1[0], foci1[1], 'ro', label='Foci 1')
    plt.plot(foci2[0], foci2[1], 'ro', label='Foci 2')
   # Set equal scaling
    plt.axis('equal')
  # Add a legend
    plt.legend()   
# Display the plot
    plt.show()
# Return the foci points
    return foci1, foci2
# Example usage: plot a shifted ellipse with a=5, b=3, h=2 (horizontal shift), and k=1 (vertical shift)
foci1, foci2 = plot_shifted_ellipse(5, 3, 2, 1)
# Print the foci points
print(f"The foci of the ellipse are located at {foci1} and {foci2}.")
