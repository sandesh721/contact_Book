import csv

try:
    f = open("new.csv")
except FileNotFoundError:
    with open('new.csv', 'w',newline='') as csvfile:
        csvreader = csv.DictReader(csvfile)
def addContact():

        with open('new.csv', 'a',newline='') as newfile:
            #fielnames = ['Name', 'phoneNumber']
            csvWrite = csv.writer(newfile)
            name = input("Enter the name:")
            phone = int(input("ENter the phone number:"))
            add = [name, phone]
            csvWrite.writerow(add)
            print("Contact has been added successfully")

def search():
   with open('new.csv', 'r',newline='') as newfile:
       csv_reader = csv.DictReader(newfile, ('name', 'number'))
       src = input("Enter the name whose contact details shold be searched:")
       found = 0
       for name in csv_reader:
           if src == name['name']:
                user = name['name']
                num = name['number']
                print(f"\nName:{user}\nPhone Number:{num}")
                found = 1
                break
       if found == 0:
           print("Contact details not found")


def display():
    with open('new.csv', 'r', newline="") as newfile:
        csv_reader = csv.DictReader(newfile, ('name', 'number'))
        print("Contact Details:")
        print("________________")
        for details in csv_reader:

            user = details['name']
            num = details['number']
            print(f"Name:{user}\nPhone Number:{num}\n")


def delete():
    with open('new.csv', 'r',newline='') as newfile:
        csv_reader = csv.reader(newfile)
        updateBook = []
        deleted = input("Enter the name of contact to be deleted:")

        found = 0
        for name in csv_reader:

            if deleted == name[0]:
                found = 1
            else:
                updateBook.append(name)

        if found==0:
            print("Name not found")
        else:

            with open("new.csv", "w", newline="") as f:
                Writer = csv.writer(f)
                contact_book = dict(updateBook)

                Writer.writerows(updateBook)
                print(f"\nContact details of {deleted} is deleted\n")

while 1:
    print("\n**************")
    print("1.Add contact\n2.Search Contact\n3.Display All Contact\n4.Delete contact\n5.Exit")
    choice = int(input("Enter your choice:"))
    if choice == 1:
       addContact()
    elif choice == 2:
        search()
    elif choice == 3:
        display()
    elif choice == 4:
        delete()
    elif choice == 5:
        break

