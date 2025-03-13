﻿# Python3 Project
#დაწერეთ პროგრამა სადაც მომხმარებელი შემოიტანს ტექსტს "camelCase" პრინციპით, თქვენმა პროგრამამ იგივე ტექსტი უნდა დააბრუნოს "snake_case" პრინციპით
import re
def camel_snake(text):
    if not re.fullmatch(r'[a-z]+(?:[A-Z][a-z]*)*', text):
        return text
    snake_case = re.sub(r'([a-z])([A-Z])', r'\1_\2', text).lower()
    return snake_case
user_input = input("Enter camelCase text: ")
print("snake_case:", camel_to_snake(user_input)) 

#წარმოიდგინეთ აპარატის რომელიც ყიდის კოკაკოლას, კოკაკოლის ბოთლი ღირს 50 ცენტი, აპარატს შეუძლია მიიღოს მხოლოდ 25,10,5 ცენტიანი მონეტები.

#დაწერეთ პროგრამა სადაც იმიტაცია იქნება იმ პროცესის როცა აპარატში ვათავსებთ სხვადასხვა ტიპის მონეტებს და გვსურს რომ ვიყიდოთ კოკაკოლა. გაითვალისწინეთ რომ თუ 50 ცენტს გასცდა პროგრამამ დასრულებისას უნდა დააბრუნოს ის ხურდის რაოდენობა რაც ზედმეტად გადახდა მოხდა

#ასევე გაითვალისწინეთ რომ თუ მომხმარებელმა მიუთითა არარსებული მონეტა თავიდან უნდა მოხდეს კითვის დასმა

def get_valid_coin():
    while True:
        try:
            coin = int(input("Insert Coin: "))
            if coin in [25, 10, 5]:
                return coin
            else:
                print("Invalid coin. Try again.")
        except ValueError:
            print("Invalid input. Please enter a valid coin.")

          def buy_coke():
    amount_due = 50
    while amount_due > 0:
        print(f"Amount Due: {amount_due}")
        coin = get_valid_coin()
        amount_due -= coin
       if amount_due < 0:
        print(f"Change Owed: {abs(amount_due)}")
    else:
        print("Change Owed: 0")

buy_coke()
amount

#დაწერეთ პროგრამა სადაც მომხმარებელი შემოიყვანს ტექსტს, პროგრამამ უნდა დააბრუნოს იგივე ტექსტი ოღონდ ხმოვნების გარეშე. გაითვალისწინეთ რომ მომხმარებელმა შეიძლება შემოიყვანოს როგორც დაბალი ასევე მაღალი რეგისტრის ასოები.
def remove_vowels(text);
    vowels = "aeiouAEIOU"      
    return "".join(char for char in text if char not in vowels)
     user_input = input("Enter text: ")
    print("Text without vowels:", remove_vowels(user_input))

 #დაწერეთ პროგრამა სადაც მომხარებელი შემოიყვანს ტექსტს. თქვენმა პროგრამამ უნდა შეამოწმოს ეს ტექსტი და თუ აკმაყოფილებს ყველა მოთხოვნებს მაშინ გამოპრინტეთ "Valid" სხვა შემთხვევაში "Invalid".

#მოთხოვნები რომლელსაც მომხარებლის ტექსტი უნდა აკმაყოფილებდეს:

#ტექსტის სიგრძე უნდა იყოს მინიმუმ 2 მაქსიმუმ 6 სიმბოლო
#ტექსტის პირველი 2 სიმბოლო აუცილებლად უნდა იყოს ასობგერა
#ტექსტი არ უნდა შეიცავდეს არცერთ პუნქტუაციის ნიშანს
#თუ ტექსტში არის ციფრები პირველი ციფრი არ უნდა იყოს "0"
#თუ ტექსტში არის ციფრები ციფრის მერე არ უნდა იყოს ასობგერა       

def is_valid(s):
    if len(s) < 2 or len(s) > 6:
        return False
    
    if not s[0].isalpha() or not s[1].isalpha():
        return False
    
    for char in s:
        if char in string.punctuation:
            return False
    
    digit_seen = False
    for i in range(len(s)):
        if s[i].isdigit():
            if s[i] == '0' and not digit_seen:
                return False
            digit_seen = True
        elif digit_seen:
            return False
    
    return True

main()
