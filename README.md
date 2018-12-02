![](https://github.com/yc3526/Tools_Project/raw/master/group_icon_v2.jpg)
Sudoku Solver
=====
Group Name and Section
----
Group Name: Sudoku Experts  
Section: 001
Group Member: Yingxiang Chen (yc3526), Zihan Yang(zy2331), Changqian Liu(cl3771), Yiqiang Lu(yl4025)

What is it?
----
Sudoku Solver is a tool for solving Sudoku problems. Users can either upload an image of initial table or manually type numbers of the initial table into the user interface. By clicking “where amazing happen!”, our software automatically hands back the rightful final table in the blink of eyes.

Contents?
----
**Transform the image into dataframe:**  
We actually have two versions of Image Recognition.

Version one (by KNN trainning on MNIST handwritten digit database):
Remove all the frames in the image and segment all the digits into 9*9 different boxes. Then build up a K-Nearest Neighbours model to    recognize each digit and convert back to a dataframe.Since the trainning set is handwritten numbers, the accuracy is not very high.

Version two (by existing package named Sudokuextract):
Extract number from image by simply applying the pacakge.

**Convert Sudoku Problem into Integer Programming Problem and solve it:**  
After we finish image recognition process, we now have input numbers given by the initial table into our system. There are several blanks ready to be filled with number from 1 to 9. We then translate this problem into a sudoku optimization problem and apply the integer programming algorithm. By creating 729 (81 * 9) binary variables and setting up 324 (81*4) constraints, we use a Python package called Pulp and solve a maximization problem with the help of it. Then we translate the optimal results of the 729 variables into values in our Sudoku table. We can prove that the newly-generated table satisfies all the rules of the Sudoku game.

**Create GUI interface:**  
We applied the tkinter package to create serveral windows for image import and optimal solution output.

Run Instructions
-----
We provide user with two version of products, and instrution for this two version is a little bit different.
Before running each version, please check the requirement_v1.txt or requirement_v2.txt for each version seperately.

Version one:
1) open the file named Suduku_Project_V1.ipynb and change the data_home directory in line 23 to your own directioy. This directory will be the place where MNIST handwritten digit database will be downloaded during implementing the code.
2) Run the Suduku_Project_V1.ipynb and wait until a new window open (might cost some time since we need to download the tranning set and train the KNN model). Remember to check whether the new window is already available behind the existing working window.
3) Access the service with password 0426 (a meaningful number for one of our group member).
4) Choose to import image by click on "load image" or just manually type numbers of the initial table.
5) Image recogniton might cost some time, and when recogniton result came, you can check whether recogniton is correct and correct them by hand
6) Click the "where amazing happen!" button and wait a few seconds for the final result.
7) If the result output infeasible, then then this Sudoku problem is Wrong(We promised!)

Version two:
1) Run the Suduku_Project_V2.ipynb and wait until a new window open. Remember to check whether the new window is already available behind the existing working window.
2) Access the service with password 0426 (a meaningful number for one of our group member).
3) Choose to import image by click on "load image" or just manually type numbers of the initial table.
4) Image recogniton might cost some time, and when recogniton result came, you can check whether recogniton is correct and correct them by hand
5) Click the "where amazing happen!" button and wait a few seconds for the final result.
6) If the result output infeasible, then then this Sudoku problem is Wrong(We promised!)
