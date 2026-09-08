# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"
```
mkdir asgar
```
<img width="466" height="38" alt="image" src="https://github.com/user-attachments/assets/1dc82ed0-387a-4e2e-a6d4-7c862eb72c31" />





## COMMAND AND OUTPUT

Remove the directory "my-folder"
```
rmdir asgar
```
<img width="468" height="30" alt="image" src="https://github.com/user-attachments/assets/34c333d6-2283-42cc-badf-8a5c96c34e1a" />


## COMMAND AND OUTPUT


Create the file Rose.txt
```
type nul > rose.txt
```
<img width="557" height="31" alt="image" src="https://github.com/user-attachments/assets/3e9e68c7-81d1-4156-a9a2-fe80015532d4" />


## COMMAND AND OUTPUT


Create the file hello.txt using echo and redirection
```
echo Hello World > hello.txt
```
<img width="662" height="37" alt="image" src="https://github.com/user-attachments/assets/f8a91816-a6fd-471e-9f7f-b8310665f239" />


## COMMAND AND OUTPUT

Copy the file hello.txt into the file hello1.txt
```
copy hello.txt hello1.txt
```
<img width="642" height="52" alt="image" src="https://github.com/user-attachments/assets/c9c7f71c-15c6-4a7c-9b7a-594644c95783" />


## COMMAND AND OUTPUT

Remove the file hello1.txt
```
del hello1.txt
```
<img width="502" height="31" alt="image" src="https://github.com/user-attachments/assets/192966d6-c08f-46b1-baee-96bed1f8cfc6" />


## COMMAND AND OUTPUT

List out the file hello1.txt in the current directory
```
dir hello1.txt
```
<img width="533" height="167" alt="image" src="https://github.com/user-attachments/assets/b3cb1329-6fe0-4a9a-b82e-e0d54b7a6dca" />


## COMMAND AND OUTPUT

List out all the associated file extensions 
```
assoc
```
<img width="562" height="690" alt="image" src="https://github.com/user-attachments/assets/ce4d47f0-673a-4cd3-9e41-15c61e086561" />


## COMMAND AND OUTPUT


Compare the file hello.txt and rose.txt
```
fc hello.txt rose.txt
```
<img width="627" height="138" alt="image" src="https://github.com/user-attachments/assets/75822298-3287-4a3b-bc59-64bb825aebe1" />


## COMMAND AND OUTPUT

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".
```
@echo off
set name=John
echo Hello, %name%
pause
```





## OUTPUT
<img width="1298" height="345" alt="image" src="https://github.com/user-attachments/assets/9ac9b7cb-b44c-4331-9676-fc2390e06e41" />




Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.

## CODE
```
@echo off
:START
set /p num=Enter a number: 

set /a rem=%num% %% 2

if %rem%==1 (
    echo The number %num% is ODD
) else (
    echo The number %num% is NOT ODD
)

:CHOICE
set /p choice=Do you want to check another number? (Y/N): 

if /I "%choice%"=="Y" goto START
if /I "%choice%"=="N" goto END

echo Invalid choice. Please enter Y or N.
goto CHOICE
:END
echo Thank you!
pause
```



## OUTPUT
<img width="1476" height="471" alt="image" src="https://github.com/user-attachments/assets/e78dbd7b-c75a-4d45-a6f0-3ea37d28ee16" />





Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

## CODE
```
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause
```




## OUTPUT
<img width="1472" height="397" alt="image" src="https://github.com/user-attachments/assets/cdbce1c2-26a8-43d4-87a3-25a09e4644d9" />





Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):
## CODE
```
@echo off
if exist sample.txt (
    echo sample.txt exists
) else (
    echo sample.txt does not exist
)
pause
```

## OUTPUT
<img width="1702" height="60" alt="image" src="https://github.com/user-attachments/assets/4d8ab710-f357-460a-bdc3-972a1a6ad560" />



Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.
## CODE
```
@echo off
:MENU
cls
echo ===== MENU =====
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
echo =================
set /p choice=Enter your choice: 

if "%choice%"=="1" goto HELLO
if "%choice%"=="2" goto CREATE
if "%choice%"=="3" goto EXIT

echo Invalid choice!
pause
goto MENU

:HELLO
echo Hello, World!
pause
goto MENU

:CREATE
echo This is a new file > newfile.txt
echo File created successfully!
pause
goto MENU
:EXIT
echo Goodbye!
pause
exit
```


## OUTPUT 1
<img width="1919" height="212" alt="image" src="https://github.com/user-attachments/assets/b569fe05-5828-4c31-ae09-85515d21f85b" />


## OUTPUT 2
<img width="1919" height="231" alt="image" src="https://github.com/user-attachments/assets/118fbcb9-289b-4ad5-b8b5-85dd9996c940" />


## OUTPUT 3
<img width="1919" height="213" alt="image" src="https://github.com/user-attachments/assets/be6dd2db-13f5-41c7-a712-f50c75d79775" />





# RESULT:
The commands/batch files are executed successfully.

