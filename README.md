# import matplotlib.pyplot as plt

# fig, ax = plt.subplots(nrows=2, ncols=3)

# # Choose one subplot to plot into, for example ax[0, 0]
# ax[0, 0].plot([1, 2, 3], [4, 5, 6])
# ax[0,1].plot([5,6,7],[0,5,7])
# plt.show()


# fig, ax =plt.subplots(ncols=2)

# ax[0].set_title('1st')
# ax[1].set_title('2nd')

# ax[0].set_xlabel('x')
# ax[0].set_ylabel('y')

# ax[1].set_xlabel('x')
# ax[1].set_ylabel('y')

# x1 = [0,1,2,]
# y1 = [0,1,5,]
# ax[0].plot(x1,y1)

# x2 = [0,1,2,]
# y2 = [0,1,5,] 
# ax[1].plot(x2,y2)

# fig.savefig('fig_double.png')

# plt.show()

# seaborn을 불러들여옵니다.
# import seaborn as stat_sb
# import matplotlib.pyplot as plt

# df = stat_sb.load_dataset('tips')
# df.head() #to show first 5 rows
# print(df.head())


# df = stat_sb.load_dataset('penguins') EXAMPLE
# df.head(6)
# print(df.head(6))

# stat_sb.histplot(df, x='tip')
# plt.show()

import seaborn as sb
import matplotlib.pyplot as plt

df = sb.load_dataset('penguins')
df.head(10)


filter = df[df['flipper_length_mm']> 183]

# sb.histplot(filter, x = "flipper_length_mm")


# g = sb.displot(filter, x ="flipper_length_mm", kde = True, color ='red')
#g.figure.savefig('kde_and_histo.png')

sb.histplot(filter, x ='flipper_length_mm', kde = True, color ='blue', binwidth =1)

sb.kdeplot(filter['flipper_length_mm'], color='red', linewidth=2)
plt.show()
