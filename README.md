# laba22
import pandas as pd     # для чтения и записи табличных файлов
import numpy as np      # для математической обработки данных
import matplotlib.pyplot as plt # для построения графиков
url ="https://drive.google.com/uc?export=download&id=1KfIzbQZwilaAL_W2vr5vcVjbVlYLQOb6"
input_df = pd.read_excel(url, header = None) 
input_df.head()
input_matrix = input_df.values # перевод таблицы в матрицу
 
print('размерность матрицы', input_matrix.shape)
print()

for i in range(1, len(input_df.columns)):
  print("{: <12} mean = {:.2f}".format(input_df.columns[i], input_matrix[ :  , i].mean()))
  generation_sum = (input_matrix[69840:70128, 1 : 2]).sum(axis = 1)
print(generation_sum)
generation_sum_1 = (input_matrix[69840:70128, 2 : 4]).sum(axis = 1)
print(generation_sum_1)
generation_sum_1+generation_sum
a=np.amax(generation_sum_1+generation_sum)
print(a)
from bokeh.plotting import figure, output_file, show
from bokeh.io import output_notebook
output_notebook()
print('Сумма двух разрезов')
p = figure(plot_width = 600, plot_height = 300)

p.line(np.arange(len(generation_sum_1+generation_sum)), generation_sum_1+generation_sum, line_width = 3)
p.circle(x=268, y=a,
           color='green', size=10, alpha=0.5)
show(p)
