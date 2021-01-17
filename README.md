# CMS-CUSTOMER-MANAGEMENT-SYSTEM-

cusId = []
cusName = []
cusAge = []
cusQualification = []


#BLL
#function for add customer
def add_cust(id,name,age,qualification):
    cusId.append(id)
    cusName.append(name)
    cusAge.append(age)
    cusQualification.append(qualification)

#function for Search customer
def search_cust(id):
    index = cusId.index(id)
    return index


#function for Delete customer
def Del_cust(id):
    index = cusId.index(id)
    cusId.pop(index)

#function for Modify customer
def modify_cust(id,name,age,qualification):
    index = cusId.index(id)
    cusName[index] = name
    cusAge[index] = age
    cusQualification[index] = qualification
#PL


while True:
    print('WELCOME TO MY CUSTOMER MANAGEMENT')
    print('1. ADD CUSTOMER \n 2. SEARCH CUSTOMER \n 3. Delete customer  \n 4. MODIFY CUSTOMER \n 5. DISPLAY CUSTOMER')
    #take input from user
    choice = input('Enter your choice: ')

    if choice == '1': #add customer
        id = int(input('enter the customer id: '))
        name = input('enter the customer name: ')
        age = int(input('enter the customer age: '))
        qualification = input('enter customer qualification: ')
        add_cust(id,name,age,qualification)
        print('Customer details is Added Successfully:')

    elif choice == '2': #search customer
        id = int(input('enter the customer id: '))
        index = search_cust(id)
        print('custId: ',id,'custName: ',cusName[index],'custAge: ',cusAge[index],
              'custQualification: ',cusQualification[index])

    elif choice == '3': #delete customer
        id = int(input('enter customer id: '))
        Del_cust(id)
        print('customer deleted successfully')

    elif choice == '4': #modify customer
        id = int(input('enter the customer id: '))

        name = input('enter the  update customer name: ')
        age = int(input('enter the update customer age: '))
        qualification = input('enter the customer  update qualification: ')
        modify_cust(id, name, age, qualification)
        print('modification successfully done')

    elif choice == '5':  #display customer
        for i in range(len(cusId)):
            print('cusId: ',cusId[i],'cusName: ',cusName[i],'cusAge: ',cusAge[i],'cusQualification: '
                  ,cusQualification[i])
