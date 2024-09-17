# PA-4 Data Wrangling & Data Visualization
Welcome to Rafa's repository! In this repository, we will use functions to make our data clean and visually appealing.

## Table of Contents
- Intended Leaning Outcome
- Instructions
- Problems
- Codeblocks and Outputs
- Version History


## Intended Learning outcome
1. identify the codes and functions needed in cleaning and visualizing data
2. Apply and use different codes and functions in creating a python program what will be used in Data Wrangling and Visualization


## Instructions
1. Download the ECE Board Exam 2 Dataset.
2. Write Python code in Jupyter Notebook to do the given problems.


## Problems
1. Create a data frame based on the format provided

1A. Filename: Instru = [“Name”, “GEAS”, “Electronics >70”]; where track is constant as
Instrumentation and hometown Luzon

1B. Filename: Mindy = [ “Name”, “Track”, “Electronics”, “Average >=55”]; where hometown is
constant as Mindanao and gender Female

2. Create a visualization that shows how the different features contributes to average grade. Does
chosen track in college, gender, or hometown contributes to a higher average score


## Codeblocks and Outputs
### Solution for 1A
```python
board = pd.read_excel('board2.xlsx') #reads the excel file
Instru = board[(board['Track'] == 'Instrumentation') &  #checks the track column for Instrumentation
            (board['Hometown'] == 'Luzon') &  #checks the hometown column for Luzon
            (board['Electronics']>70)][['Name','GEAS','Electronics']] #checks the electronics column for >70
                                                                    #prints the name, geas, and electronics
print(Instru)#Prints output
```
### Output
![image](https://github.com/user-attachments/assets/c647768b-b01c-4662-a92b-169a5b1aaee5)


### Solution for 1B
```
board['Average'] = board[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis=1) #gets the means of Math, Electronics, GEAS, and Communication
Mindy = board[(board['Hometown'] == 'Mindanao') &  #checks column for Mindanao
            (board['Gender'] == 'Female') &  #checks column for Female 
            (board['Average'] >= 55)][['Name', 'Track', 'Electronics']] #checks column for average>=55, stores name, track, and electronics
print(Mindy) #prints output
```
### Ouput

![image](https://github.com/user-attachments/assets/27cff38b-59ca-4dc6-8bb3-65d6b49baa3d)

### Solution for 2

```
sns.boxplot(x ='Track', y ='Average', hue ='Gender', data = board)
#Makes use of a boxplot to show the track, average, gender, and data
plt.show() # prints the boxplot
```
### Output
![image](https://github.com/user-attachments/assets/78fe0d1b-61a6-4607-9e15-fea61abec7df)

```
sns.boxplot(x ='Hometown', y ='Average', hue = 'Hometown', data = board)
#Creates a boxplot that compares the average by Hometown
plt.show()
```

### Output
![image](https://github.com/user-attachments/assets/7dfd83f4-be32-451d-ac2a-16515c942435)













## Version History

V1 . . . Initial Repository

V2 . . . Inputting Codeblocks and Solutions
