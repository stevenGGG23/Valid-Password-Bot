This program prompts the user to enter the name of a file containing a list of passwords. It reads the passwords from the file and categorizes them as either "Good Passwords" or "Bad Passwords" based on predefined safety criteria. The program then outputs the categorized lists and calculates the percentage of bad passwords from the total number of passwords processed.

Key Features:
File Input:

The program prompts the user to enter the filename to process.
It attempts to open the specified file for reading. If the file does not exist, an error message is displayed, and the program terminates gracefully.
Password Categorization:

The program reads all passwords from the file, stripping any leading or trailing whitespace.
It categorizes each password into "Good" or "Bad" based on the following criteria:
A password must be at least 9 characters long.
It must contain at least 3 uppercase letters.
It must have at least 3 digits.
It must not contain any spaces.
Output:

After processing, the program prints out the categorized lists of passwords:
"Bad Passwords": lists all passwords deemed unsafe.
"Good Passwords": lists all passwords deemed safe.
It calculates and displays the percentage of bad passwords relative to the total number of passwords processed, formatted to two decimal places.
Error Handling:

The program includes error handling to manage cases where the input file does not exist.
