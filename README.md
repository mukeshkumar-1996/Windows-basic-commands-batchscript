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

<img width="666" height="394" alt="566070576-12939aae-1015-40c1-88c9-41cfb85721f2" src="https://github.com/user-attachments/assets/b00e0c9f-97bb-4135-bdd4-013617e29350" />

Remove the directory "my-folder"

## COMMAND AND OUTPUT
rmdir my-folder

<img width="438" height="292" alt="566070731-a821e1cf-7c6c-4e21-9b2d-14b8a88f9db2" src="https://github.com/user-attachments/assets/476cc1c0-d89e-4b20-9960-128c6cf1cb2d" />

Create the file Rose.txt

## COMMAND AND OUTPUT
type nul > rose.txt

echo Rose flower is beautiful >> rose.txt

<img width="699" height="102" alt="566070881-f39a5a61-9339-4f11-a613-c3cd72062892" src="https://github.com/user-attachments/assets/9b4d98aa-d14d-45d2-84a5-68f8dc7b9c2f" />


Create the file hello.txt using echo and redirection

## COMMAND AND OUTPUT
echo Hello > hello.txt

type hello.txt

<img width="497" height="193" alt="566071010-d8b792dd-3423-42fd-b5bf-a31a39af6cb8" src="https://github.com/user-attachments/assets/d11af693-0692-4234-b0b0-d0d82db5ce42" />


Copy the file hello.txt into the file hello1.txt

## COMMAND AND OUTPUT
copy hello.txt hello1.txt

type hello1.txt

<img width="501" height="212" alt="566071170-37fec9ae-6ec5-4000-b9a8-8009e661c326" src="https://github.com/user-attachments/assets/89ba5c3e-1116-428c-8148-02d1a07bf04a" />

Remove the file hello1.txt

## COMMAND AND OUTPUT
del hello1.txt

<img width="508" height="313" alt="566071275-22629fbb-d9b1-4d90-8a79-cf95153ff72b" src="https://github.com/user-attachments/assets/8028927d-0133-4d82-a3fe-feb3bd736670" />

List out the file hello1.txt in the current directory

## COMMAND AND OUTPUT
dir hello1.txt

<img width="438" height="196" alt="566071353-dbd87ffb-6f59-4125-9ab6-2ad6045e3d47" src="https://github.com/user-attachments/assets/097bda50-eb52-446c-8cc3-6da0e3fe2dc6" />

List out all the associated file extensions 

## COMMAND AND OUTPUT
assoc

<img width="452" height="337" alt="566071525-f7a2435d-cf51-42c2-9b66-c5b2f63d625e" src="https://github.com/user-attachments/assets/7c674902-2173-48f4-b43f-1ef771990381" />

Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT
fc hello.txt rose.txt

<img width="482" height="262" alt="566071688-40acedbe-ef4a-435d-bae3-c7db0586e833" src="https://github.com/user-attachments/assets/0d9622d1-5368-48c5-81d3-7a18b5edccad" />


## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".

    @echo off
    set name=Saveetha
    echo Hello, %name%!
    pause




## OUTPUT
<img width="405" height="88" alt="566071999-1b58a902-987a-4979-bc94-b335a54b6185" src="https://github.com/user-attachments/assets/d1234a3d-1745-4b92-9e93-67bdd1e873e6" />



Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.

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


## OUTPUT

<img width="662" height="206" alt="566072232-2b3a5c3a-df57-4cf9-a049-47bbf4e73d10" src="https://github.com/user-attachments/assets/f1124189-51d0-4781-aadd-90ed38758fe4" />



Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

    @echo off
    for %%i in (1 2 3 4 5) do (
       echo Number: %%i
    )
    pause



## OUTPUT
<img width="424" height="185" alt="566072784-fe810554-dde3-4989-846f-90382797ee5e" src="https://github.com/user-attachments/assets/cbf43769-101c-442e-8917-6c0801f9b0de" />




Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):

    @echo off
    if exist sample.txt (
       echo sample.txt exists.
    ) else (
        echo sample.txt does not exist.
    )
    pause

## OUTPUT
<img width="394" height="149" alt="566073097-11999a2f-177a-454a-8ec7-66e995550905" src="https://github.com/user-attachments/assets/008d3817-56cf-4b4b-a71a-f94f2d8e10be" />


Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.


    @echo off
    :menu
    echo 1. Say Hello
    echo 2. Create a File
    echo 3. Exit
    set /p choice=Choose an option: 
    if "%choice%"=="1" goto hello
    if "%choice%"=="2" goto createfile
    if "%choice%"=="3" goto end

    :hello
    echo Hello, World!
    goto menu

   :createfile
   echo Creating a file...
   echo This is a new file > newfile.txt
   goto menu
   :end
   echo Goodbye!
   pause


## OUTPUT

<img width="540" height="421" alt="566073321-4344f1bf-4f77-44b0-aeec-8276490844f7" src="https://github.com/user-attachments/assets/2c4d8161-e93f-4c3c-884f-9279c58ccb63" />


# RESULT:
The commands/batch files are executed successfully.

