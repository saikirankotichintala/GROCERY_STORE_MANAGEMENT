# GROCERY_STORE_MANAGEMENT
## OBJECTIVES OF THE PROJECT 
   The objective of this project is to let the students apply the programming knowledge into a real -world situation /problem and exposed the students how programming skills helps in developing a good software .
1.	Write program utilizing modern software tools .
2.	Apply object oriented programming principles effectively when developing small to medium sized projects.
3.	Write effective procedural code to small to medium sized problems .
4.	Students will demonstrate a breadth of knowledge  in computer science ,as exemplitied in areas of system , theory and software development .
5.	Students will demonstrate ability to conduct a research  or applied Computer Science project , requiring  writing and presentation skills which exemplify scholarly style in computer science .

## PROPOSED SYSTEM

Today one cannot afford to rely on the fallible human beings of be really wants to stand against today's merciless competition where not to wise saying "to err is human" no longer valid, it's outdated to rationalize your mistake. So, to keep pace with time, to bring about the best result without malfunctioning and greater efficiency so to replace the unending heaps of flies with a much sophisticated hard disk of the computer.

One has to use the data management software. Software has been an ascent in atomization various organisations. Many software products working are now in markets, which have helped in making the organizations work easier and efficiently. Data management initially had to maintain a lot of ledgers and a lot of paper work has to be done but now software product on this organization has made their work faster and easier. Now only this software has to be loaded on the computer and work. can be done.

### The systems development life  cycle(SDLC)

This prevents a lot of time and money. The work becomes fully automated and any information regarding the organization can be obtained by clicking the button. Moreover, now it's an age of computers of and automating such an organization gives the better look
The systems development life  cycle(SDLC)

The systems development life cycle is a project management technique that divides complex projects into smaller, more easily managed segments or phases. Segmenting projects allows managers to verify the successful completion of project phases before allocating resources to subsequent phases.
Software development projects typically include initiation, planning, design, development, testing, implementation, and maintenance phases. However, the phases may be divided differently depending on the organization involved.
For example, initial project activities might be designated as request. requirements-definition, and planning phases, or initiation, concept-development, and planning phases. End users of the system under development should be involved in reviewing the output of each phase to ensure the system is being built to deliver the needed functionality.
### CODE
import mysql.connector as sql
conn = sql.connect(
    host="localhost",
    username="root",
    password="Saikiran@123456$",
    database="grocerystore"
)
if conn.is_connected():
    print("Successfully connected")
c = conn.cursor()
print("Grocery Shop Management System")
print("1. Login")
print("2. Exit")
choice = int(input("Enter your choice: "))
if choice == 1:
    user_name = input("Enter your username: ")
    password = input("Enter your password: ")
    while user_name == "abc" and password == "abc123":
        print("Connected successfully")
        print("1. Customer Details")
        print("2. Product Details")
        print("3. Worker Details")
        print("4. See All Customer Details")
        print("5. See All Product Details")
        print("6. See All Worker Details")
        print("7. See One Customer Detail")
        print("8. See One Product Detail")
        print("9. See One Worker Detail")
        print("10. Exit")
        choice = int(input("Enter your choice: "))
        if choice == 1:
            phone_no = int(input("Enter customer phone number: "))
            cust_name = input("Enter customer name: ")
            cost = float(input("Enter customer purchased cost: "))
            c.execute("INSERT INTO customer_details VALUES ('{0}', '{1}', '{2}')".format(phone_no, cust_name, cost))
            conn.commit()
            print("Data is updated")
        elif choice == 2:
            product_name = input("Enter product name: ")
            product_cost = float(input("Enter the cost: "))
            sql_insert = "INSERT INTO product_details VALUES ('{0}', '{1}')".format(product_name, product_cost)
            c.execute(sql_insert)
            conn.commit()
            print("Data is updated")
        elif choice == 3:
            worker_name = input("Enter your name: ")
            worker_work = input("Enter your work: ")
            worker_age = int(input("Enter your age: "))
            worker_salary = float(input("Enter your salary: "))
            phone_no = int(input("Enter your phone number: "))
            sql_insert = "INSERT INTO worker_details VALUES ('{0}', '{1}', '{2}', '{3}', '{4}')".format(worker_name, worker_work, worker_age, worker_salary, phone_no)
            c.execute(sql_insert)
            conn.commit()
            print("Data is updated")
        elif choice == 4:
            t = conn.cursor()
            t.execute("SELECT * FROM customer_details")
            record = t.fetchall()
            for i in record:
                print(i)
        elif choice == 5:
            t = conn.cursor()
            t.execute("SELECT * FROM product_details")
            record = t.fetchall()
            for i in record:
                print(i)
        elif choice == 6:
            t = conn.cursor()
            t.execute("SELECT * FROM worker_details")
            record = t.fetchall()
            for i in record:
                print(i)
        elif choice == 7:
            a = input("Enter your name: ")
            t = conn.cursor()
            t.execute("SELECT * FROM customer_details WHERE cust_name = '{0}'".format(a))
            record = t.fetchall()
            for i in record:
                print(i)
        elif choice == 8:
            a = input("Enter your product name: ")
            t = conn.cursor()
            t.execute("SELECT * FROM product_details WHERE product_name = '{0}'".format(a))
            record = t.fetchall()
            for i in record:
                print(i)
        elif choice == 9:
            a = input("Enter your worker name: ")
            t = conn.cursor()
            t.execute("SELECT * FROM worker_details WHERE worker_name = '{0}'".format(a))
            record = t.fetchall()
            for i in record:
                print(i)
        elif choice == 10:
            print("Exiting...")
            break
else:
    print("Exiting...")

