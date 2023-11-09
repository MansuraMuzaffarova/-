# -
import sys
import matplotlib
matplotlib.use('Agg')

import pandas as pd
import matplotlib.pyplot as plt
from scipy import stats

cities_data = pd.read_csv("data.csv", header=0, sep=",")
x = cities_data["Population"]
y = cities_data["Median_Income"]

slope, intercept, r, p, std_err = stats.linregress(x, y)

def myfunc(x):
    return slope * x + intercept

mymodel = list(map(myfunc, x))

plt.scatter(x, y)
plt.plot(x, mymodel)
plt.xlabel("Population")
plt.ylabel("Median_Income")
plt.title("Population vs Median Income")
plt.show()
plt.savefig(sys.stdout.buffer)
sys.stdout.flush()

Array = [1000, 85, 8541, 95, 1000, 105, 110, 450, 120, 125]
print(Array)

Array = [1000, 85, 8541, 95, 1000, 105, 110, 450, 120, 125]
ModifiedArray = [x + 10 for x in Array]

print(ModifiedArray)


import pandas as pd

school_grades = {
    'Математика': [90, 85, 92, 78, 88],
    'Русский': [85, 88, 90, 92, 78],
    'Физика': [92, 87, 95, 80, 85],
    'Литература': [78, 80, 85, 90, 88],
    'Химия': [85, 92, 88, 78, 90]
}

grades_df = pd.DataFrame(data=school_grades)

print(grades_df)

import pandas as pd

# Создаем пример датасета
data = {
    'Store': ['A', 'B', 'C', 'D', 'E'],
    'Sales': [5000, 7000, 5500, 9000, 8000],
    'Expenses': [3000, 4000, 3500, 5000, 4500],
    'Profit': [2000, 3000, 2000, 4000, 3500]
}

sales_df = pd.DataFrame(data)

# Находим средний объем продаж
average_sales = sales_df['Sales'].mean()
# Находим магазин с самой высокой прибылью
most_profitable_store = sales_df.loc[sales_df['Profit'].idxmax(), 'Store']
print("Средний объем продаж:", average_sales)
print("Самый прибыльный магазин:", most_profitable_store)


import pandas as pd

library_data = pd.read_csv("data.csv", header=0, sep=",")

print(library_data.head())

