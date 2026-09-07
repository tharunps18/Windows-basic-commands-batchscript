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

## COMMAND AND OUTPUT
mkdir my-folder

<img width="553" height="69" alt="image" src="https://github.com/user-attachments/assets/0cf3bb8d-16bb-43db-8ba5-f399ee4994a6" />


## COMMAND AND OUTPUT
rmdir my-folder

<img width="553" height="54" alt="image" src="https://github.com/user-attachments/assets/e7cbb80b-b7fc-48b3-a068-2bfb3a1e1aff" />



## COMMAND AND OUTPUT
COPY CON Rose.txt
A clock in a office can never get stolen Too many employees watch it all the time ^Z 1 file(s) copied

dir Rose.txt


<img width="552" height="238" alt="image" src="https://github.com/user-attachments/assets/e1548ea0-a50c-4905-96c0-35c5d2f56923" />


## COMMAND AND OUTPUT
echo “hello world” > hello.txt
type hello.txt

<img width="555" height="98" alt="image" src="https://github.com/user-attachments/assets/19337564-a491-4098-83c1-06eb0d3d0c8a" />


## COMMAND AND OUTPUT
assoc | more

<img width="553" height="437" alt="image" src="https://github.com/user-attachments/assets/1345a7d2-7e5a-4d17-b98d-a539b14c6286" />


## COMMAND AND OUTPUT

fc hello.txt Rose.txt

<img width="562" height="102" alt="image" src="https://github.com/user-attachments/assets/63f61952-191b-44d9-9c53-2b9d840a12de" />


## COMMAND AND OUTPUT
    @echo off
    set name=John
    echo Hello, %name%!
    pause
    
<img width="551" height="61" alt="image" src="https://github.com/user-attachments/assets/ed46aa7d-a28a-4a72-b0fe-8ac619fcd638" />


List out all the associated file extensions 

## COMMAND AND OUTPUT

    @echo off
    :main
    set /p number=Enter a number: 
    rem Calculate remainder when divided by 2
    set /a remainder=%number% %% 2
    if %remainder%==1 (
        echo %number% is an odd number.
    ) else (
        echo %number% is not an odd number.
    )
    :choice
    set /p continue=Do you want to check another number? (Y/N): 
    if /i "%continue%"=="Y" goto main
    if /i "%continue%"=="N" goto end
    echo Invalid choice, please enter Y or N.
    goto choice
    :end
    echo Thank you for using the odd number checker!
    pause
    
<img width="556" height="157" alt="image" src="https://github.com/user-attachments/assets/194ed72c-5d79-4f18-8879-5b82e96d4c8c" />



Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".

## BATCH PROGRAM

@echo off
set name=John
echo Hello, %name%
pause


## OUTPUT

<img width="551" height="73" alt="image" src="https://github.com/user-attachments/assets/06e39581-8398-419d-888f-76ed2dfd058d" />



Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.

## BATCH PROGRAM

@echo off
:loop
set /p num=Enter a number: 
set /a rem=%num% %% 2

if %rem%==0 (
    echo %num% is Even
) else (
    echo %num% is Odd
)

:ask
set /p ans=Do you want to check another number? (Y/N): 
if /I "%ans%"=="Y" goto loop
if /I "%ans%"=="N" goto end
echo Invalid input. Please enter Y or N.
goto ask

:end
echo Thank you!
pause

## OUTPUT

<img width="558" height="152" alt="image" src="https://github.com/user-attachments/assets/2caedb67-01f9-4333-b2d6-1c4ae0fd320e" />




Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

## BATCH PROGRAM


@echo off
for /L %%i in (1,1,5) do (
    echo Number: %%i
)
pause

## OUTPUT

<img width="560" height="121" alt="Screenshot 2025-11-06 085041" src="https://github.com/user-attachments/assets/7a17d88d-be99-4866-b1dc-53103e153ae8" />




Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):

## BATCH PROGRAM

@echo off
if exist sample.txt (
    echo sample.txt exists.
) else (
    echo sample.txt does not exist.
)
pause

## OUTPUT

<img width="551" height="115" alt="image" src="https://github.com/user-attachments/assets/f9881894-52c4-4891-a109-818194922342" />



Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.

## BATCH PROGRAM

@echo off
:menu
cls
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
set /p choice=Choose an option (1-3): 

if "%choice%"=="1" goto hello
if "%choice%"=="2" goto create
if "%choice%"=="3" goto exit
echo Invalid choice.
pause
goto menu

:hello
echo Hello, World!
pause
goto menu

:create
echo This is a new file > newfile.txt
echo File newfile.txt created.
pause
goto menu

:exit
echo Goodbye!
pause
exit

## OUTPUT

<img width="404" height="164" alt="image" src="https://github.com/user-attachments/assets/c7c33d1e-d837-4637-9735-00402fb97996" />
<img width="416" height="182" alt="image" src="https://github.com/user-attachments/assets/377f91f9-f605-4da4-b36a-a2b0316141e2" />

<img width="392" height="189" alt="image" src="https://github.com/user-attachments/assets/42433858-cbec-447d-89fe-638a2d0d2000" />


# RESULT:
The commands/batch files are executed successfully.

