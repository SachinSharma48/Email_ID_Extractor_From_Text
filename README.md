# Email_ID_Extractor_From_Text
The Email_ID_Extractor_From_Text project is designed to scan a given text for email addresses and extract them. It utilizes regular expressions to identify and extract valid email addresses from the text. Regular expressions are patterns used to match strings in a powerful and flexible way.

Gathering email addresses from large texts manually can be time-consuming and error-prone.
This is where the Email_ID_Extractor_From_Text project comes in. 
This Python project automates the process of extracting email addresses from text, making it efficient and accurate.


import csv
import re
def extract_emails(file_path):
    with open(file_path, 'r', encoding='utf-8') as file:
        text = file.read()

    email_regex = r'\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}\b'
    emails = re.findall(email_regex, text)

    return emails
file_path = r"C:\Users\sachin\Desktop\test.txt"
result = extract_emails(file_path)
output_file_path = r"C:\Users\sachin\Desktop\results.csv"
with open(output_file_path, 'w', newline='', encoding='utf-8') as file:
    writer = csv.writer(file)
    writer.writerow(['Email'])

    for email in result:
        writer.writerow([email])
