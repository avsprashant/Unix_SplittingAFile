# Unix_SplittingAFile

Keywords: Unix Shell Script, Split File, Divide

Introduction
	This UNIX shell script is used to split an input file into two equal halves. The input file will be split and two output files will be created with its original input file name and suffix as “.part1” and “.part2“ like “<filename>.part1” and “<filename>.part2”.  We need to pass the filename as an input parameter for calling the script. This script will be used to split the file with header record and for splitting the file without header this script needs a slight modification in the code.

Please find below the script flow:
1.	This script will check for the number of arguments. If number of arguments is 1, then execution will continue else the script will print the usage of the script as below and exits from execution.

             USAGE: split_file.sh <FILE>
             Example: split_file.sh file.txt

2.	The first argument value will be stored in the “file” variable and then prints the value. The script will check for the file existence and if the file is present, the script continues with the next steps else will print the message “Input file file.txt does not exist” and exits from application.

3.	The count of the lines in the input file will be stored in “filelinecount” variable and then prints the value.

4.	As the input file has header information also, “excheader” variable will be used to store the total number of lines excluding the header.

5.	 “excheader” value will be divided by 2 and stores the value to “firstpart” variable. To calculate no of lines for second half of input file, “firstpart” value will be subtracted from “filelinecount” value and then stores the value to “rempart” variable.

6.	To calculate no of lines for first half of input file, one will be added to variable “firstpart” and stores the value to “firstpart” variable. Now “firstpart” variable has count of lines for first half of input file including header lineand “rempart” variable has no of lines for second half of input file without header line count.

7.	“head” command is used with the argument “firstpart” variable to create the output file “file.txt.part1” along with header.

8.	Header from the input file will be copied and then tail command with argument as “rempart” variable will be used to create the output file “file.txt.part2”.

9.	“chmod” command will be used to give read, write and execute permissions to the output files..

-------------------------------------------------------------------------------------------------------

Here I have shown the input file content and created output file content for your understanding.

Input file(file.txt):

Name|EMP ID|CITY	---------------? header
Anand|145251|Chennai
Sam|13232|Chennai
Madhan|234233|Chennai
Rahul|234443|Maduai

Output file:

file.txt.part1

Name|EMP ID|CITY
Anand|145251|Chennai
Sam|13232|Chennai

file.txt.part2

Name|EMP ID|CITY
Madhan|234233|Chennai
Rahul|234443|Madua
