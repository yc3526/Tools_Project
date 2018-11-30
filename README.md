![](https://github.com/yc3526/Tools_Project/raw/master/group_icon.jpg)
Sudoku Solver
=====
Group Name and Section
----
Group Name: Sudoku Experts  
Section: 001

What is it?
----
Sudoku Solver is a tool for solving Sudoku problems. Users can either upload an image of initial table or manually type numbers of the initial table into the user interface. By clicking “Solve Sudoku problem now!”, our software automatically hands back the rightful final table in the blink of eyes.

Contents?
----
**Transform the image into dataframe:**  
Remove all the frames in the image and segment all the digits into 9*9 different boxes. Then build up a K-Nearest Neighbours model to recognize each digit and convert back to a dataframe.

**Build the linear regression model:**  
After we finish image recognition process, we now have input numbers given by the initial table into our system. There are several blanks ready to be filled with number from 1 to 9. We then translate this problem into a sudoku optimization problem and apply the integer programming algorithm. By creating 729 (81 * 9) binary variables and setting up 324 (81*4) constraints, we use a Python package called Pulp and solve a maximization problem with the help of it. Then we translate the optimal results of the 729 variables into values in our Sudoku table. We can prove that the newly-generated table satisfies all the rules of the Sudoku game.

**Create GUI interface:**  
???

Run Instructions
-----
Users can first access the Sudoku solver with password 0426 (a meaningful number for one of our group member), then either upload an image of the initial table or manually type numbers of the initial table into the user interface. By clicking “Solve Sudoku problem now!”, our software automatically hands back the rightful final table in the blink of eyes.
