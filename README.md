# freeRTOS
freeRTOS development 

# Code
Since the code for the communication and matrix tasks are already given so its modifications are added in the main file attached and commented on the code but not shown here. The priorityset_task() task is used to change the priority of the communicationtask based on the execution time of the task.


# Priorityset task function

		/* In this condition the priority of the communication task is set to
		*  4 if the execution time if the greater than 1000 millisecond
		*/

		/* In this condition the priority of the communication task is set to
		*  2 if the execution time if the less than 200 millisecond
		*/


# Main code additions
/* Three tasks are created and each task are initially assigned a priority statically.*/


# Question and answers
•	Why is "matrixtask" using most of the CPU utilization?
The matrix task takes more computation than the other tasks thus having a higher CPU utilization.
•	Why must the priority of "communicationtask" increase in order for it to work properly
The communication task blocks the matrix task from executing so the priority of the communication task must be increased else the matrix task will take a longer time to execute. Lowering the priority of the matrix task makes it pre-empt the communication task.
•	What happens to the completion time of "matrixtask" when the priority of "communicationtask" is increased?
Communication task priority increase doesn’t have much effect on the matrix task due to the low execution time of the communication task.
•	How many seconds is the period of "matrixtask"? (Hint: look at vApplicationTickHook() to measure it)
/*	The block of code below this is used to calculate the time needed to execute
*	the matric task and set the matrix_time variable based on the calculated
*	time for further analysis.
*/

This part of the code calculates the time period the matrix task takes and prints the output. It is estimated that the period of the matrix task is 1165ms from my execution over a long time execution. Changes in the priority of the task will affect the period.

