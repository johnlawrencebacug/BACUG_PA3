# PROGRAMMING ASSIGNMENT_2 
### Bacug, John Lawrence B. | 2ECE-C 
### Date submitted: September 10, 2026 
## Objectives 
Use the same cars.csv dataset supplied for Experiment 3. Write the solutions in one Jupyter Note- book and import Pandas as pd. The dataset contains the Model column together with the vehicle variables used in the original experiment. * Load the CSV file into a DataFrame named cars. * Use Pandas subsetting, slicing, indexing, and Boolean conditions. Do not manually type any requested table or answer. * Do not modify values in cars; create a new DataFrame or Series for each requested subset. * Preserve the row order of the source dataset unless stated otherwise. * Display every requested result in an executed notebook cell. 

* `import` pandas `as` pd - This defines that pandas is recognized as pd.
* `cars = pd.read_csv('cars.csv')` - Imports the file "cars.csv" to the notebook and is defined as "cars".
* `cars` - Calls the variable with the file.

## **A. POSITIONAL AND LABEL-BASED SLICING** 
`print("Cars shapes:", cars.shape)` 
* Prints a tuple containing the dimensions of the DataFrame as (rows, columns). It satisfies instruction (a) by displaying the overall shape of the dataset. 

`print(cars.columns.tolist())` 
* Extracts the column headers of the DataFrame using .columns and converts them into a standard Python list using .tolist(). This completes instruction (a) by showing all available column names. 

`cars_6_to_10 = cars.iloc[6:11]` 
* Uses positional indexing (.iloc) to slice rows 6 through 10 and stores them in a new DataFrame named cars_6_to_10. Because pandas uses 0-based indexing and the end boundary in a slice is exclusive, range 6:11 selects index positions 6, 7, 8, 9, and 10—which correspond to rows 7 through 11 in python, matching instruction (b) for 1-based rows 6 to 10.
  
`cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']]` 
* Filters the cars_6_to_10 DataFrame by passing a list of specific column names in double brackets. Fulfills instruction (c) by displaying only the Model, mpg, cyl, hp, and gear columns in that exact order.

```python
print("Cars shapes:", cars.shape)
print(cars.columns.tolist())
cars_6_to_10 = cars.iloc[6:11] cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear',]]
```

## **B. MODEL LOOKUP** 
`toyota = cars.loc[cars['Model'] == 'Toyota Corolla']` 

`cars['Model'] == 'Toyota Corolla'`
* Creates a Boolean Series (a sequence of True and False values) by checking every row in the 'Model' column to see if it equals 'Toyota Corolla'.

`cars.loc[...]` 
* Uses Pandas label-based indexing to filter the cars DataFrame, keeping only the row(s) where the condition evaluated to True. 

`toyota =` 
* Stores the resulting DataFrame (containing all columns for the Toyota Corolla row) into the variable named toyota. 

`toyota` 
* The data is then stored in toyota variable and called.

`pontiac = cars.loc[cars['Model'] == 'Pontiac Firebird', ['Model','mpg','hp','wt']]` `cars['Model'] == 'Pontiac Firebird'`
* Creates a Boolean Series checking every row in the 'Model' column for 'Pontiac Firebird'.

`['Model','mpg','hp','wt']` 
* Specifies the exact subset of columns to retrieve.

`cars.loc[rows, columns]`
* Filters the DataFrame using the Boolean condition for the rows (first argument) and selects only the four specified column labels (second argument).
  
`pontiac =` 
* Stores this filtered DataFrame into the variable named pontiac.

`pontiac` 
* Evaluates and displays the contents stored in the pontiac variable in the output.


```python
toyota = cars.loc[cars['Model'] ==  'Toyota Corolla'] toyota
pontiac = cars.loc[cars['Model'] == 'Pontiac Firebird', ['Model','mpg','hp','wt']] pontiac
```

## **C. MULTI-MODEL SUBSETTING** 
`selected_cars = cars.loc[(cars['Model'] == 'Datsun 710') | (cars['Model'] == 'Lotus Europa') | (cars['Model'] == 'Ferrari Dino'), ['Model', 'mpg', 'cyl', 'hp', 'gear']]``(cars['Model'] == 'Datsun 710') | (cars['Model'] == 'Lotus Europa') | (cars['Model'] == 'Ferrari Dino')` 

* Creates a Boolean Series by checking each row in the 'Model' column against three conditions using the OR operator (|). A row evaluates to True if its model name matches any of these three cars, and False otherwise.
  
`['Model', 'mpg', 'cyl', 'hp', 'gear']`
* Defines a list of specific column names to retain in the output. `cars.loc[rows, columns]` * Uses Pandas label-based indexing to select the matching rows (first argument) and filter for the requested subset of five columns (second argument).

`selected_cars =`
* Assigns the filtered result to a new DataFrame variable named selected_cars.

`selected_cars`
* Evaluates and displays the contents of the selected_cars DataFrame in the notebook output.

`selected_cars.shape` * Returns a tuple (3, 5) indicating the DataFrame has 3 rows and 5 columns. 

```python
selected_cars = cars.loc[(cars['Model'] == 'Datsun 710') | (cars['Model'] == 'Lotus Europa') | (cars['Model'] == 'Ferrari Dino'), ['Model', 'mpg', 'cyl', 'hp', 'gear']]
selected_cars
selected_cars.shape
```

#### Read me file update history
Date updated: 09/10/2026
