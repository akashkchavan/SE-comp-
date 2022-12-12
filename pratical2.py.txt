# Group A - Assignment 1

print("Group A :- 'Assignment No. 1'")

def Problem_Statement():
    """
    Write a Python program to store marks scored in subject “Fundamental of Data Structure” by N students in the class. 
    Write functions to compute following: 
        a) The average score of class 
        b) Highest score and lowest score of class 
        c) Count of students who were absent for the test
        d) Display mark with highest frequency 
    """
print(Problem_Statement.__doc__)

#<********************************************************************************>

# Creating an empty list for taking input of FDS student marks. 

marks = []
def student_info():
	n = int(input("\nEnter number of students in Fundamental of Data structures: "))
	for i in range(n):
		M = int(input(f"Enter the marks for {i+1} students: (Write -1 for absent studnet)" ))
		marks.append(M)  # adding the  marks of students
	print("Original mark-list of students in FDS : " + str(marks))

#<********************************************************************************>

# Calculate Average score of class
def average_marks():
	total = 0
	cnt = 0
	for i in range(len(marks)):
		if marks[i] != -1:
			total = total + marks[i]
			cnt += 1
	print("Total is: ", total)
	print("Average Score of the class is (in integer): ",total//cnt)
	print("Average Score of the class is (in decimal): ",total/cnt)

#<********************************************************************************>

# Calculating MInimum and Maximum Score of Class
def max_min():
	temp = marks[0] 
	for i in range(len(marks)):
		if temp < marks[i]:
			temp = marks[i]
	print("Highest Marks: ", temp)
	
	temp = marks[0]
	for i in  range(len(marks)):
		if temp > marks[i]:
			temp = marks[i]
	print("Lowest Marks: ", temp)

#<********************************************************************************>

# Counting number of students who are absent for the test
def count_abs():
	cnt=0
	for i in range(len(marks)):
		if marks[i] == -1:
			cnt+=1
	print("Number of students absent for the test are: ", cnt)

#<********************************************************************************>

#Calulating Marks with Highest Frequency
def high_freq():
	freq = []
	for i in range(len(marks)):
		if marks[i] != -1:
			freq.append(marks.count(marks[i]))
	print(freq)
	k = max(freq)
	print("Highest frequency: ", k)
	print("Highest Marks: ",marks[k])

#<********************************************************************************>

#main()
if __name__ == '__main__':
	print("=____-----_____TAKE INPUT_____-----____=")
	student_info()
	while(True):
		print("\n\n1. The average score of class")
		print("2. Highest score and lowest score of class")
		print("3. Count of students who were absent for the test")
		print("4. Display mark with highest frequency")
		print("5. Exit\n\n")
		choice = int(input())
		if (choice==1):
			average_marks()
		
		if (choice==2):
			max_min()
			
		if (choice==3):
			count_abs()
			
		if (choice==4):
			high_freq()
			
		if (choice==5):
	    		exit()
	    		
#<********************************************************************************>



