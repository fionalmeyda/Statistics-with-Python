3A ) pd.read_csv allows you to control delimeters, column and row names

	data_directory = '/Users/fionalmeyda/Desktop/titanic/'
	df_train = pd.read_csv(data_directory + 'train.csv')
	df_test = pd.read_csv(data_directory + 'test.csv')

3C ) one hot encoding handles categorical data by allowing you to get probabilities from real numbers. This is achieved by giving each category a column (example : Pclass was separated into columns 1, 2 and 3).

	one_hot = pd.get_dummies(df['Pclass'])
    df =df.drop(['Pclass'],axis =1)
    df =df.join(one_hot)

3D) we can impute missing data by replacing them with the median. The missing data for age and fare were replaced by its respectful median.
	
	median_age = df_train['Age'].median()
	df['Age'].fillna(median_age,inplace =True)