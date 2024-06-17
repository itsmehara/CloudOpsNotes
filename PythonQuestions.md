
```
notes






































```

<br>

Below are 10 questions for each section focusing on Pandas, NumPy, list/collection slicing, data transformations, queries on Pandas, joins in Pandas, and matplotlib/other similar libraries.

### Pandas Knowledge

| No | Question | Answer |
|----|----------|--------|
| 1 | How do you create a DataFrame in Pandas? | Use `pd.DataFrame()` with data as a dictionary, list of lists, or another DataFrame. |
| 2 | How can you read a CSV file into a Pandas DataFrame? | Use `pd.read_csv('filename.csv')`. |
| 3 | How do you select a specific column from a DataFrame? | Use `df['column_name']` or `df.column_name`. |
| 4 | How do you filter rows in a DataFrame based on a condition? | Use `df[df['column_name'] > value]`. |
| 5 | What method would you use to check for missing values in a DataFrame? | Use `df.isnull()` and `df.isna()`. |
| 6 | How can you fill missing values in a DataFrame? | Use `df.fillna(value)` or `df.fillna(method='ffill'/'bfill')`. |
| 7 | How do you remove duplicates from a DataFrame? | Use `df.drop_duplicates()`. |
| 8 | How do you group data in a DataFrame by a specific column? | Use `df.groupby('column_name')`. |
| 9 | How can you apply a function to each element in a DataFrame column? | Use `df['column_name'].apply(function)`. |
| 10 | How do you merge two DataFrames? | Use `pd.merge(df1, df2, on='common_column')`. |


### NumPy Knowledge

| No | Question | Answer |
|----|----------|--------|
| 1 | How do you create a NumPy array? | Use `np.array([1, 2, 3])`. |
| 2 | How do you generate an array of zeros in NumPy? | Use `np.zeros(shape)`. |
| 3 | What function do you use to generate an array of random numbers? | Use `np.random.random(size)` or `np.random.rand(d0, d1, ..., dn)`. |
| 4 | How do you find the shape of a NumPy array? | Use `array.shape`. |
| 5 | How do you reshape a NumPy array? | Use `array.reshape(new_shape)`. |
| 6 | How do you find the mean of elements in a NumPy array? | Use `np.mean(array)`. |
| 7 | How do you concatenate two NumPy arrays? | Use `np.concatenate((array1, array2), axis=0/1)`. |
| 8 | How can you perform element-wise addition of two arrays? | Use `array1 + array2`. |
| 9 | How do you find the maximum value in a NumPy array? | Use `np.max(array)`. |
| 10 | How do you save a NumPy array to a file? | Use `np.save('filename.npy', array)` and load with `np.load('filename.npy')`. |


### List/Collection Slicing Knowledge

| No | Question | Answer |
|----|----------|--------|
| 1 | How do you access the first element of a list? | Use `list[0]`. |
| 2 | How do you access the last element of a list? | Use `list[-1]`. |
| 3 | How do you slice a list to get the first three elements? | Use `list[:3]`. |
| 4 | How do you reverse a list using slicing? | Use `list[::-1]`. |
| 5 | How do you access every second element in a list? | Use `list[::2]`. |
| 6 | How do you slice a list to exclude the first element? | Use `list[1:]`. |
| 7 | How do you slice a list to exclude the last element? | Use `list[:-1]`. |
| 8 | How do you create a sublist from index 3 to 7? | Use `list[3:8]`. |
| 9 | How do you access the elements from index 2 to the end of the list? | Use `list[2:]`. |
| 10 | How do you slice a list to get elements from the end, excluding the last three? | Use `list[:-3]`. |


### Data Transformations Knowledge

| No | Question | Answer |
|----|----------|--------|
| 1 | How do you rename columns in a DataFrame? | Use `df.rename(columns={'old_name': 'new_name'})`. |
| 2 | How can you convert a DataFrame column to a different data type? | Use `df['column_name'].astype(new_type)`. |
| 3 | How do you apply a function to each row in a DataFrame? | Use `df.apply(function, axis=1)`. |
| 4 | How can you normalize the values in a DataFrame column? | Use `(df['column_name'] - df['column_name'].min()) / (df['column_name'].max() - df['column_name'].min())`. |
| 5 | How do you pivot a DataFrame? | Use `df.pivot(index='index_column', columns='column_to_pivot', values='values_column')`. |
| 6 | How do you melt a DataFrame? | Use `pd.melt(df, id_vars=['id_columns'], value_vars=['value_columns'])`. |
| 7 | How do you concatenate DataFrames vertically? | Use `pd.concat([df1, df2], axis=0)`. |
| 8 | How can you replace values in a DataFrame? | Use `df.replace(to_replace, value)`. |
| 9 | How do you filter rows based on multiple conditions in a DataFrame? | Use `df[(df['column1'] > value1) & (df['column2'] < value2)]`. |
| 10 | How do you add a new column to a DataFrame? | Use `df['new_column'] = values`. |


### Queries on Pandas Knowledge

| No | Question | Answer |
|----|----------|--------|
| 1 | How do you select rows where a column value is equal to a specific value? | Use `df[df['column_name'] == value]`. |
| 2 | How do you select rows based on multiple column conditions? | Use `df[(df['column1'] == value1) & (df['column2'] > value2)]`. |
| 3 | How do you select rows based on a list of values for a column? | Use `df[df['column_name'].isin([value1, value2, value3])]`. |
| 4 | How do you query rows using the `query` method? | Use `df.query('column_name > value')`. |
| 5 | How do you select rows where a column value is not null? | Use `df[df['column_name'].notnull()]`. |
| 6 | How do you select rows where a column value contains a substring? | Use `df[df['column_name'].str.contains('substring')]`. |
| 7 | How do you select the top N rows in a DataFrame? | Use `df.head(N)`. |
| 8 | How do you select rows based on a datetime range? | Use `df[(df['date_column'] >= 'start_date') & (df['date_column'] <= 'end_date')]`. |
| 9 | How do you select rows where a column value is between two values? | Use `df[df['column_name'].between(start_value, end_value)]`. |
| 10 | How do you select unique rows in a DataFrame? | Use `df.drop_duplicates()`. |


### Joins Knowledge

| No | Question | Answer |
|----|----------|--------|
| 1 | How do you perform an inner join in Pandas? | Use `pd.merge(df1, df2, on='common_column', how='inner')`. |
| 2 | How do you perform a left join in Pandas? | Use `pd.merge(df1, df2, on='common_column', how='left')`. |
| 3 | How do you perform a right join in Pandas? | Use `pd.merge(df1, df2, on='common_column', how='right')`. |
| 4 | How do you perform an outer join in Pandas? | Use `pd.merge(df1, df2, on='common_column', how='outer')`. |
| 5 | How do you join DataFrames on multiple columns? | Use `pd.merge(df1, df2, on=['column1', 'column2'], how='join_type')`. |
| 6 | How do you concatenate DataFrames horizontally? | Use `pd.concat([df1, df2], axis=1)`. |
| 7 | How do you join DataFrames using the `join` method? | Use `df1.join(df2, on='common_column', how='join_type')`. |
| 8 | How do you avoid duplicated column names after a join? | Use `pd.merge(df1, df2, on='common_column', suffixes=('_left', '_right'))`. |
| 9 | How do you perform a cross join in Pandas? | Use `df1.assign(key=1).merge(df2.assign(key=1), on='key').drop('key', axis=1)`. |
| 10 | How do you merge DataFrames with different column names? | Use `pd.merge(df1, df2, left_on='df1_column', right_on='df2_column')`. |

### Matplotlib and Similar Libraries Knowledge

| No | Question | Answer |
|----|----------|--------|
| 1 | How do you create a simple line plot in Matplotlib? | Use `plt.plot(x, y)` followed by `plt.show()`. |
| 2 | How do you add a title and labels to a plot in Matplotlib? | Use `plt.title('Title')`, `plt.xlabel('X-axis Label')`, and `plt.ylabel('Y-axis Label')`. |
| 3 | How do you create a scatter plot in Matplotlib? | Use `plt.scatter(x, y)` followed by `plt.show()`. |
| 4 | How do you create a histogram in Matplotlib? | Use `plt.hist(data, bins=number_of_bins)` followed by `plt.show()`. |
| 5 | How do you create a bar chart in Matplotlib? | Use `plt.bar(x, height)` followed by `plt.show()`. |
| 6 | How do you customize the color and style of a plot in Matplotlib? | Use parameters like `color`, `linestyle`, `marker` in `plt.plot()`. |
| 7 | How do you create subplots in Matplotlib? | Use `plt.subplot(nrows, ncols, index)` and `plt.subplots(nrows, ncols)`. |
| 8 | How do you add a legend to a plot in Matplotlib? | Use `plt.legend()`. |
| 9 | How do you save a plot as an image file in Matplotlib? | Use `plt.savefig('filename.png')`. |
| 10 | How do you create a heatmap in Seaborn? | Use `sns.heatmap(data, annot=True)` followed by `plt.show()`. |


Feel free to use these questions to assess the depth of knowledge of candidates in these specific areas.


Here is a comprehensive table with questions and answers covering various aspects of Python knowledge, Data Science, and Machine Learning, categorized by the different areas of expertise.

### Data Science Knowledge

| No | Question | Answer |
|----|----------|--------|
| 1 | What is the difference between supervised and unsupervised learning? | Supervised learning uses labeled data to train models, while unsupervised learning uses unlabeled data to find patterns. |
| 2 | What is a confusion matrix? | A confusion matrix is a table used to evaluate the performance of a classification algorithm by comparing predicted and actual values. |
| 3 | Explain the concept of cross-validation. | Cross-validation is a technique to assess the performance of a model by dividing the data into training and testing sets multiple times. |
| 4 | What is overfitting? | Overfitting occurs when a model learns the training data too well, capturing noise and performing poorly on new data. |
| 5 | What is underfitting? | Underfitting occurs when a model is too simple to capture the underlying patterns in the data, resulting in poor performance on both training and testing data. |
| 6 | Describe the bias-variance tradeoff. | Bias-variance tradeoff is the balance between a model's ability to minimize bias (error due to assumptions) and variance (error due to complexity). |
| 7 | What is regularization? | Regularization techniques, such as L1 and L2, add a penalty to the loss function to prevent overfitting by discouraging large coefficients. |
| 8 | What is PCA (Principal Component Analysis)? | PCA is a dimensionality reduction technique that transforms data into a set of linearly uncorrelated components. |
| 9 | Explain the difference between bagging and boosting. | Bagging involves training multiple models independently and averaging their predictions, while boosting trains models sequentially, correcting errors of previous models. |
| 10 | What is feature engineering? | Feature engineering involves creating new features or modifying existing ones to improve model performance. |
| 11 | What is the purpose of the train-test split? | The train-test split is used to evaluate a model's performance on unseen data by splitting the dataset into training and testing subsets. |
| 12 | What is a ROC curve? | A ROC curve plots the true positive rate against the false positive rate, used to evaluate the performance of a binary classifier. |
| 13 | What is a random forest? | A random forest is an ensemble learning method that combines multiple decision trees to improve accuracy and reduce overfitting. |
| 14 | Explain the concept of k-means clustering. | K-means clustering partitions data into k clusters by minimizing the within-cluster sum of squares. |
| 15 | What is a neural network? | A neural network is a computational model inspired by the human brain, consisting of layers of interconnected nodes (neurons) that process data. |
| 16 | What is gradient descent? | Gradient descent is an optimization algorithm used to minimize a loss function by iteratively adjusting model parameters in the direction of the steepest descent. |
| 17 | Explain the difference between precision and recall. | Precision is the ratio of true positives to the total predicted positives, while recall is the ratio of true positives to the total actual positives. |
| 18 | What is the F1 score? | The F1 score is the harmonic mean of precision and recall, providing a balanced measure of a model's performance. |
| 19 | What is a decision tree? | A decision tree is a non-parametric model that splits data into subsets based on feature values, creating a tree-like structure of decisions. |
| 20 | Explain the concept of ensemble learning. | Ensemble learning combines multiple models to improve overall performance, using techniques like bagging, boosting, and stacking. |

### Machine Learning Knowledge

| No | Question | Answer |
|----|----------|--------|
| 1 | What is the difference between classification and regression? | Classification predicts discrete labels, while regression predicts continuous values. |
| 2 | Explain the concept of a support vector machine (SVM). | SVM is a supervised learning algorithm that finds the optimal hyperplane to separate data points of different classes. |
| 3 | What is a kernel trick in SVM? | The kernel trick allows SVMs to transform data into higher dimensions, making it possible to find a linear separator in non-linear data. |
| 4 | What is a learning rate in machine learning? | The learning rate determines the step size for updating model parameters during training. |
| 5 | Explain the concept of a hyperparameter. | Hyperparameters are configuration settings for machine learning algorithms that are set before training and cannot be learned from the data. |
| 6 | What is the purpose of a validation set? | A validation set is used to tune hyperparameters and evaluate model performance during training, distinct from the training and test sets. |
| 7 | What is a loss function? | A loss function measures the difference between the predicted and actual values, guiding the optimization process. |
| 8 | Explain the difference between batch and stochastic gradient descent. | Batch gradient descent updates model parameters using the entire training dataset, while stochastic gradient descent updates parameters for each training example. |
| 9 | What is a convolutional neural network (CNN)? | A CNN is a type of neural network designed for processing structured grid data, such as images, using convolutional layers. |
| 10 | Explain the concept of dropout in neural networks. | Dropout is a regularization technique that randomly drops neurons during training to prevent overfitting. |
| 11 | What is an autoencoder? | An autoencoder is a type of neural network that learns to encode data into a lower-dimensional representation and then decode it back to the original input. |
| 12 | Explain the difference between supervised and semi-supervised learning. | Supervised learning uses labeled data, while semi-supervised learning uses both labeled and unlabeled data to improve model performance. |
| 13 | What is transfer learning? | Transfer learning leverages pre-trained models on a new task, reducing training time and improving performance, especially with limited data. |
| 14 | What is a generative adversarial network (GAN)? | A GAN is a type of neural network consisting of a generator and a discriminator that compete to generate realistic data. |
| 15 | What is reinforcement learning? | Reinforcement learning is a type of machine learning where an agent learns to make decisions by receiving rewards or penalties based on its actions. |
| 16 | Explain the concept of a Markov decision process (MDP). | An MDP is a mathematical framework for modeling decision-making in situations where outcomes are partly random and partly under the control of a decision-maker. |
| 17 | What is a Long Short-Term Memory (LSTM) network? | LSTM is a type of recurrent neural network (RNN) designed to capture long-term dependencies and handle the vanishing gradient problem. |
| 18 | What is a Boltzmann machine? | A Boltzmann machine is a type of stochastic neural network that learns a probability distribution over its input data. |
| 19 | Explain the concept of feature scaling. | Feature scaling standardizes the range of independent variables to improve the performance and convergence of machine learning algorithms. |
| 20 | What is the purpose of one-hot encoding? | One-hot encoding transforms categorical variables into binary vectors, allowing them to be used in machine learning algorithms. |

### Python Basic Knowledge

| No | Question | Answer |
|----|----------|--------|
| 1 | What is a Python decorator? | A decorator is a function that modifies the behavior of another function or method. |
| 2 | Explain the difference between `__init__` and `__new__` in Python. | `__init__` initializes an instance of a class, while `__new__` creates the instance. |
| 3 | What are Python comprehensions? | Python comprehensions provide a concise way to create lists, dictionaries, and sets using a single line of code. |
| 4 | How does the `self` keyword work in Python? | `self` represents the instance of a class and is used to access its attributes and methods. |
| 5 | What is the purpose of `lambda` functions in Python? | `lambda` functions create small anonymous functions inline. |
| 6 | How do you handle exceptions in Python? | Exceptions are handled using `try`, `except`, `finally`, and `else` blocks. |
| 7 | What is the difference between a list and a tuple? | Lists are mutable, while tuples are immutable. |
| 8 | Explain the use of the `with` statement in Python. | The `with` statement simplifies exception handling by encapsulating common setup and cleanup tasks. |
| 9 | What is a Python generator? | A generator is a function that yields items one at a time, allowing iteration over large datasets without consuming excessive memory. |
| 10 | How do you create a virtual environment in Python? | Use `venv` module: `python -m venv myenv`. |
| 11 | What is the purpose of the `__name__ == '__main__'` construct? | It allows code to run only when the module is executed directly, not when imported. |
| 12 | How does Python's garbage collection work? | Python uses reference counting and a cyclic garbage collector to manage memory. |
| 13 | What are Python's built-in data types? | Common built-in data types include `int`, `float`, `str`, `list`, `tuple`, `dict`, `set`, and `bool`. |
| 14 | Explain the difference between shallow and deep copy. | A shallow copy copies the object but not the nested objects, while a deep copy copies both the object and nested objects. |
| 15 | How do you read and write files in Python? | Use `open()` with appropriate modes (`'r'`, `'w'`, `'a'`, etc.) for reading and writing files. |
| 16 | What is the Global Interpreter Lock (GIL) in Python? | The GIL is a mutex that protects access to Python objects, preventing multiple threads from executing Python bytecode simultaneously. |
| 17 | What is a Python module? | A module is a file containing Python code that can be imported and used in other Python scripts. |
| 18 | How do you handle missing values in a dataset using Python? | Use libraries like `pandas` to fill, drop, or interpolate missing values. |
| 19 | What is the purpose of the `pass` statement in Python? | The `pass` statement is a no-operation statement used as a placeholder in code. |
| 20 | How do you perform unit testing in Python? | Use the `unittest` module to write and run tests. |

### Python Comprehensions, Generators, Decorators Knowledge

| No | Question | Answer |
|----|----------|--------|
| 1 | What is a list comprehension in Python? | A list comprehension is a concise way to create lists using a single line of code. |
| 2 | How do you create a generator in Python? | Use the `yield` keyword within a function to create a generator. |
| 3 | What is a dictionary comprehension? | A dictionary comprehension creates dictionaries in a single line of code using a similar syntax to list comprehensions. |
| 4 | Explain the purpose of the `itertools` module. | `itertools` provides functions for efficient looping and combinatorial generation. |
| 5 | What is the use of the `functools.wraps` decorator? | `functools.wraps` is used to preserve the original function's metadata when applying a decorator. |
| 6 | How do you create a set comprehension? | Use curly braces `{}` with a comprehension syntax to create a set comprehension. |
| 7 | What is the difference between `map` and a list comprehension? | `map` applies a function to all items in an iterable, while a list comprehension allows for more complex transformations and conditions. |
| 8 | How do you implement a simple decorator in Python? | Define a function that takes another function as an argument and returns a new function that wraps the original. |
| 9 | What is a generator expression? | A generator expression creates a generator in a single line of code using a similar syntax to list comprehensions but with parentheses `()`. |
| 10 | How do you chain generators in Python? | Use the `yield from` statement or `itertools.chain` to chain multiple generators. |
| 11 | What is the `@property` decorator used for? | The `@property` decorator allows a method to be accessed like an attribute. |
| 12 | Explain the difference between `staticmethod` and `classmethod`. | `staticmethod` does not take any implicit first argument, while `classmethod` takes the class as the first argument. |
| 13 | How do you use the `filter` function in Python? | `filter` applies a function to an iterable, returning only items for which the function returns `True`. |
| 14 | What is the purpose of the `zip` function? | `zip` combines multiple iterables into a single iterator of tuples. |
| 15 | How do you handle nested comprehensions in Python? | Use multiple `for` statements within a comprehension to handle nested loops. |
| 16 | What is a closure in Python? | A closure is a function that remembers the environment in which it was created, even after the outer function has finished executing. |
| 17 | Explain the concept of lazy evaluation in Python. | Lazy evaluation delays computation until the result is needed, which is commonly used in generators. |
| 18 | How do you create an infinite iterator in Python? | Use `itertools.cycle`, `itertools.count`, or a generator function with an infinite loop. |
| 19 | What is the `partial` function in `functools` used for? | `partial` is used to fix a certain number of arguments of a function and generate a new function. |
| 20 | How do you use a decorator to time a function's execution? | Define a decorator that records the start and end time of the function execution and prints the difference. |

### Python OOP Knowledge

| No | Question | Answer |
|----|----------|--------|
| 1 | What are the main principles of OOP? | Encapsulation, inheritance, polymorphism, and abstraction. |
| 2 | How do you define a class in Python? | Use the `class` keyword followed by the class name and a colon. |
| 3 | What is inheritance in Python? | Inheritance allows a class to inherit attributes and methods from another class. |
| 4 | Explain the concept of polymorphism in Python. | Polymorphism allows different classes to be treated as instances of the same class through a common interface. |
| 5 | What is encapsulation? | Encapsulation restricts direct access to an object's data and methods, providing controlled access through public methods. |
| 6 | How do you create a constructor in Python? | Define the `__init__` method within a class to initialize its attributes. |
| 7 | What is method overriding? | Method overriding occurs when a subclass provides a specific implementation of a method already defined in its superclass. |
| 8 | What is multiple inheritance? | Multiple inheritance allows a class to inherit from more than one base class. |
| 9 | Explain the use of the `super` function. | `super` is used to call a method from a superclass in a subclass. |
| 10 | What is an abstract class? | An abstract class cannot be instantiated and is meant to be subclassed, containing one or more abstract methods. |
| 11 | How do you define an interface in Python? | Use abstract base classes (ABCs) from the `abc` module to define interfaces. |
| 12 | What is the difference between a class and an object? | A class is a blueprint for creating objects, while an object is an instance of a class. |
| 13 | Explain the concept of class variables and instance variables. | Class variables are shared across all instances of a class, while instance variables are unique to each instance. |
| 14 | What is method overloading? | Method overloading allows a class to have multiple methods with the same name but different parameters. |
| 15 | How do you achieve data hiding in Python? | Use double underscores `__` to prefix an attribute or method name to make it private. |
| 16 | What is a mixin? | A mixin is a class that provides methods to other classes through inheritance, without being intended for standalone use. |
| 17 | How do you implement a singleton pattern in Python? | Use a class with a method that ensures only one instance of the class is created. |
| 18 | What is the purpose of the `__str__` and `__repr__` methods? | `__str__` provides a readable string representation, while `__repr__` provides an unambiguous string representation for debugging. |
| 19 | How do you define a property in Python? | Use the `@property` decorator to define getter, setter, and deleter methods for an attribute. |
| 20 | Explain the difference between composition and inheritance. | Composition involves building complex objects by combining simpler ones, while inheritance creates a new class based on an existing class. |

Feel free to use these questions and answers to assess the depth of knowledge of a Python developer with experience in Data Science, Machine Learning, and various Python concepts.

Here is the table with the questions and their answers:

| No | Question | Answer |
|----|----------|--------|
| 1 | How does Django work (workflow)? | Django follows the MVT (Model-View-Template) architecture. The user makes a request, the view processes it, interacts with the model, and returns a response using templates. |
| 2 | What is `__init__.py` inside the application folder? | It is an empty file that indicates the directory is a Python package. |
| 3 | What is the use of `manage.py`? | It is a command-line utility for administrative tasks like starting the server, migrating databases, etc. |
| 4 | How will you add extra function/feature in the admin part? | By customizing the admin.py file and using ModelAdmin classes. |
| 5 | Have you customized admin style? | Yes, by overriding admin templates and using custom CSS. |
| 6 | What middleware have you used and what's the purpose of it? | Common middleware include `AuthenticationMiddleware` for handling user sessions and `CsrfViewMiddleware` for CSRF protection. |
| 7 | How have you used session? How can we handle session expire time? | Sessions are used for storing user data across requests. Session expiration can be set using `SESSION_COOKIE_AGE` in settings. |
| 8 | How will you write a complex Django query? | Using Django’s ORM with Q objects and F expressions for complex lookups. |
| 9 | Django `group_by` query | Use the `annotate()` function with `values()` to group by fields. |
| 10 | What are signals and how to use them? What are two important parameters in signals? | Signals allow decoupled applications to get notified when certain actions occur. Important parameters are `sender` and `receiver`. |
| 11 | Have you written template tags? What's the use of it? | Yes, template tags are used to create custom template syntax for rendering dynamic content. |
| 12 | Form inheritance | Form inheritance allows you to create a base form and extend it in other forms. |
| 13 | Model inheritance | Django supports abstract base classes, multi-table inheritance, and proxy models for model inheritance. |
| 14 | How to get all logged-in user list or count? | Use `User.objects.filter(is_authenticated=True)` to get the list of logged-in users. |
| 15 | What reusable applications have you used in a Django project? | Common reusable apps include `django-allauth` for authentication, `django-rest-framework` for APIs, etc. |
| 16 | How to save dynamic data without using DB/file? | Using in-memory storage like Django's cache framework or Redis. |
| 17 | How are you requesting AJAX in Django? How does it work? | By using JavaScript (e.g., jQuery) to make AJAX requests to Django views that return JSON responses. |
| 18 | How do you access a particular block in child HTML? | By using Django template inheritance with `{% block %}` and `{% extends %}` tags. |
| 19 | How are you debugging the application? | Using `print` statements, `pdb`, and Django Debug Toolbar. |
| 20 | Have you used the logging module? | Yes, for recording errors, info, and debug messages in log files. |
| 21 | What is the message framework and explain it | Django’s messages framework allows storing and retrieving temporary messages to display to users. |
| 22 | What are modules in Django? | Modules in Django refer to reusable code segments like apps and libraries. |
| 23 | What is serialization and why are we using it? | Serialization converts complex data types to JSON or XML for easy storage and transmission. |
| 24 | How are you testing your application? | Using Django’s built-in test framework with unit tests and integration tests. |
| 25 | How are you deploying the application with Apache? | By configuring Apache with mod_wsgi to serve the Django application. |
| 26 | What's the difference between `mod_python` & `mod_wsgi`? | `mod_wsgi` is a newer, more efficient module for serving Python applications, while `mod_python` is older and less performant. |
| 27 | What are all new features in Django's latest version? | Check the official Django release notes for the latest features. |
| 28 | What's the major advantage in Django 1.2? | Introduction of multi-database support. |
| 29 | Which function won't run in Django 1.2 which runs in Django 1.0? | Specific deprecated features like certain old-style middleware. |
| 30 | If a Django-powered application is a high-traffic site, how will you reduce the traffic? | Using caching, database optimization, and load balancing. |
| 31 | How to modify a model without affecting data? | By using Django’s migration system to apply changes incrementally. |
| 32 | What things should we consider while designing models? | Consider normalization, relationships, indexing, and future scalability. |
| 33 | What is a datatype? | A datatype defines the type of data that a variable can hold (e.g., integer, string, etc.). |
| 34 | List, tuple, dict differences | Lists are mutable, tuples are immutable, and dictionaries are key-value pairs. |
| 35 | List sorting without using a generic function | Use a custom sorting algorithm like bubble sort or selection sort. |
| 36 | Can we use a list as a key in dict? | No, because lists are mutable and not hashable. |
| 37 | Dict sorting both key and value sorting | Use the `sorted()` function with custom key functions. |
| 38 | What is list comprehension and where do you use it? | List comprehension provides a concise way to create lists. Used for readability and performance. |
| 39 | What is an iterator, generator? | An iterator is an object that can be iterated upon. A generator is a function that returns an iterator. |
| 40 | How to get a traceback? Explain | Use the `traceback` module to print the stack trace of an exception. |
| 41 | How to write a class? | Define a class using the `class` keyword followed by the class name and methods. |
| 42 | What is `__init__`? | It is a constructor method in Python classes used for initializing objects. |
| 43 | What is `self`? | `self` represents the instance of the class and is used to access class attributes and methods. |
| 44 | What is a constructor? | A constructor is a special method that is called when an object is instantiated. |
| 45 | What is a decorator? How does it work? How to write a custom decorator? | A decorator is a function that modifies the behavior of another function. Custom decorators are defined using the `@decorator` syntax. |
| 46 | What is `__init__` and `__new__`? Explain the syntax of these two functions. What are the args by default these functions can have? | `__init__` initializes an instance, while `__new__` creates it. Both can take `self` and other initialization parameters. |
| 47 | What is the `super` function in Python and where do you use it? | `super` is used to call methods from a parent class in a subclass. |
| 48 | Have you used `set()`? If so, where? | Yes, sets are used for storing unique items and performing set operations. |
| 49 | Single linked list? | A data structure where each element points to the next element. |
| 50 | Which version are you using? | Varies, but commonly used versions are 3.x for Python and the latest stable version for Django. |
| 51 | Deprecation in Python latest version or version which you are working | Check the Python release notes for deprecated features. |
| 52 | What data model does Django follow? | Django follows the Model-View-Template (MVT) pattern. |
| 53 | Describe how Django is MVT? | Model handles the data, View processes the logic, and Template renders the HTML. |
| 54 | What are the named URL patterns? What is the URL template tag and what is its usefulness? | Named URL patterns allow referencing URLs by name. `{% url %}` template tag generates URLs dynamically. |
| 55 | Tell me about a templating system in Django. What is template inheritance? How do you get contents of a parent block? | Django uses its own templating system. Template inheritance allows extending base templates using `{% block %}` tags. Use `{% block.super %}` to include parent block content. |
| 56 | What is a template tag? What is an inclusion template tag? How do you create a template tag? | Template tags are special syntax for logic in templates. Inclusion tags include another template. Create custom tags using `library.simple_tag`. |
| 57 | What is ORM? Why is it useful? How does Django accomplish such functionality? What is model inheritance? What types of model inheritance are there in Django? | ORM (Object-Relational Mapping) converts data between incompatible systems. Django's ORM handles database operations. Model inheritance types are abstract base classes, multi-table inheritance, and proxy models. |
| 58 | In table inheritance, how are the two tables related? | They are related through foreign key relationships, with one table extending the other. |
| 59 | How do you extend a user profile in Django? | By creating a OneToOneField linking to the User model. |
| 60 | Describe signals in Django? What is their usefulness? What design pattern do they remind you of? How would you implement the above-mentioned design pattern? | Signals allow decoupled communication between components, similar to the Observer pattern. Implement by defining signal handlers and connecting them to signals. |

Let me know if you need further details on any of the questions.




Sure! Here are the answers to the questions in table format:

### Slots

| No | Question | Answer |
|----|----------|--------|
| 1 | What are `__slots__` in Python? | `__slots__` is a mechanism that prevents the creation of a default `__dict__` for instance attributes, saving memory by allocating space for a fixed set of attributes. |
| 2 | Write sample code using `__slots__`. | refer below code |
```python
class MyClass:
    __slots__ = ['attr1', 'attr2']
    
    def __init__(self, attr1, attr2):
        self.attr1 = attr1
        self.attr2 = attr2

obj = MyClass(10, 20)
print(obj.attr1, obj.attr2)
``` 


### Global Interpreter Lock (GIL)

| No | Question | Answer |
|----|----------|--------|
| 3 | What is the GIL in Python? | The Global Interpreter Lock (GIL) is a mutex that protects access to Python objects, preventing multiple threads from executing Python bytecodes simultaneously. This ensures that only one thread executes in the Python interpreter at once, making Python thread-safe but limiting the execution of multi-threaded programs. |



```python
print("")






print("")
```


### Method Resolution Order (MRO)

| No | Question | Answer |
|----|----------|--------|
| 4 | What is the MRO in Python? | Method Resolution Order (MRO) is the order in which Python looks for a method in a hierarchy of classes. It is determined using the C3 linearization algorithm, ensuring a consistent order in class hierarchies, especially with multiple inheritance. |
| 5 | Explain MRO in detail. | The MRO ensures that each class is considered before its superclass. It is computed by the C3 linearization algorithm, which merges the MROs of the parents while preserving their order and ensuring that a class appears before any of its subclasses. This is crucial for consistent method resolution and avoiding potential conflicts in multiple inheritance. |
| 6 | How can you view the MRO of a class? | Use the `ClassName.__mro__` attribute or the `ClassName.mro()` method. |
| 7 | Example of viewing MRO. | refer below code |

```python
class A: pass
class B(A): pass
class C(A): pass
class D(B, C): pass

print(D.__mro__)

# Output: (<class '__main__.D'>, <class '__main__.B'>, <class '__main__.C'>, <class '__main__.A'>, <class 'object'>)
``` 

### Metaclass

| No | Question | Answer |
|----|----------|--------|
| 8 | What is a metaclass in Python? | A metaclass is a class of a class that defines how a class behaves. A class is an instance of a metaclass. In Python, `type` is the default metaclass, but custom metaclasses can be created by inheriting from `type`. |
| 9 | Explain metaclass in detail. | Metaclasses are powerful tools that allow customization of class creation and behavior. When a class is defined, Python uses its metaclass to create it. The metaclass can modify the class definition, add or modify methods, and control class inheritance. This allows for advanced patterns like singleton classes, auto-registering classes, and more. |
| 10 | Write sample code using a metaclass. | refer below code |

```python
class MyMeta(type):
    def __new__(cls, name, bases, dct):
        dct['greet'] = lambda self: f"Hello from {self.__class__.__name__}"
        return super().__new__(cls, name, bases, dct
class MyClass(metaclass=MyMeta):
    pass
obj = MyClass()
print(obj.greet())  # Output: Hello from MyClass
``` 

### Context Manager

| No | Question | Answer |
|----|----------|--------|
| 11 | Explain context manager in Python. | A context manager in Python is a construct that allows setup and teardown actions to be performed around a block of code. It is commonly used with `with` statements to ensure resources are properly managed, such as opening and closing files. |
| 12 | How to write a context manager? | You can write a context manager using a class with `__enter__` and `__exit__` methods, or using the `contextlib` module's `contextmanager` decorator. |
| 13 | Write sample code for a context manager using a class. | refer below code |

```python
class MyContextManager:
    def __enter__(self):
        print("Entering the context")
        return self

    def __exit__(self, exc_type, exc_value, traceback):
        print("Exiting the context")

with MyContextManager():
    print("Inside the context")
# Output:
# Entering the context
# Inside the context
# Exiting the context
```

| No | Question | Answer |
|----|----------|--------|
| 14 | Write sample code for a context manager using `contextlib`. | refer below code | 

```python
from contextlib import contextmanager

@contextmanager
def my_context():
    print("Entering the context")
    yield
    print("Exiting the context")

with my_context():
    print("Inside the context")
# Output:
# Entering the context
# Inside the context
# Exiting the context
``` 

These tables provide a detailed overview and examples of each concept, helping you to test the depth of knowledge of the candidates in these advanced Python topics.
