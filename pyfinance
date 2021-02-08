import numpy as np # Importar numpy
import pandas as pd # Importar pandas
import matplotlib as mpl
import scipy
import importlib
import matplotlib.pyplot as plt
from scipy.stats import skew,kurtosis,chi2


'''
Goal: create a normality test: Jarque Bera
step 1: generate random variables
step 2: visualize histogram
step 3: what is Jarque Bera

'''

#Generate a random variable
x_size = 10**6           # Tamaño
degrees_freedom = 500   # Grados de libertad
type_random_variable = 'student'# Normal exponencial student

if type_random_variable == 'normal':
    x = np.random.standard_normal(size=x_size)
    x_str = type_random_variable
elif type_random_variable == 'exponencial':
    x = np.random.standard_exponencial(size=x_size)
    x_str = type_random_variable
elif type_random_variable == 'student': # Los grados de libertad solo aplica para "Student"
    x = np.random.standard_t(size=x_size,df = degrees_freedom)
    x_str = type_random_variable + ' df = '+str(degrees_freedom)
    
# Compute Risk Metrics
x_mean = np.mean(x)
x_stdev = np.std(x)
x_skew = skew(x)
x_kurt = kurtosis(x)
x_median = np.percentile(x,0.5)
# Print Metrics

print(x_str)
print('Mean'+str(x_mean))
print('Std'+str(x_stdev))
print('Skewness'+str(x_skew))
print('Kurtosis'+str(x_kurt))

# Plot Histogram

plt.figure()
plt.hist(x,bins=10)
plt.title('Histogram '+x_str)
plt.show()
