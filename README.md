#validate.py 
#We will prompts the user to enter a password. Check whether the password is safe to use or not and output a
#message stating either GOOD PASSWORD or BAD PASSWORD and use accessesing files to do that and at th end print the percentage of bad passwords. 

def main():
    file_name = input("Enter file to process: ")
    
    try:
        with open(file_name, 'r') as file:
            passwords = file.readlines()
    except FileNotFoundError:
        print(f"{file_name} does not exist.")
        return
    
    bad_passwords, good_passwords = categorize_passwords(passwords)
    
    print("Bad Passwords")
    for password in bad_passwords:
        print(password)
    print()
    print("Good Passwords")
    for password in good_passwords:
        print(password)
    
    total_passwords = len(bad_passwords) + len(good_passwords)
    percent_bad = (len(bad_passwords) / total_passwords) * 100 if total_passwords > 0 else 0
    
    print(f"\n{percent_bad:.2f}% of passwords were bad.")

def categorize_passwords(passwords):
    bad_passwords = []
    good_passwords = []
    
    for password in passwords:
        password = password.strip()
        if is_good_password(password):
            good_passwords.append(password)
        else:
            bad_passwords.append(password)
    
    return bad_passwords, good_passwords

def is_good_password(password):
    if len(password) < 9:
        return False
    if sum(1 for c in password if c.isupper()) < 3:
        return False
    if sum(1 for c in password if c.isdigit()) < 3:
        return False
    if ' ' in password:
        return False
    return True

if __name__ == "__main__":
    main()




