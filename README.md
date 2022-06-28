# Airline-Reservation
try:
    from msilib.schema import ComboBox
    from tkinter import *
    from tkinter import messagebox
    from turtle import width

    def save_info():
        firstname_info = firstname.get()
        lastname_info = lastname.get()
        age_info = age.get()
        gender_info= gender.get()
        phone_info= phone.get()
        country_info=country.get()
        city_info=city.get()

        fileText = ""
        file = open("user.txt","w")
    
        fileText += "First Name :  " + firstname_info
        fileText += "\n"
    
        fileText += "Last Name :  " + lastname_info
        fileText += "\n"
    
        fileText += "Age :  " + str(age_info)
        fileText += "\n"
   
    
        fileText += "Gender :  " + gender_info
        fileText += "\n"
    
        fileText += "Phone Number :  " + str(phone_info)
        fileText += "\n"

        fileText += "Country Name :  " + str(country_info)
        fileText += "\n"

        fileText += "City Name :  " + str(city_info)
        fileText += "\n"

        fileText += "Flight Class :  " + flight_class.get()
        fileText += "\n"  
        fileText += "Seat Number :  " + seat_num.get()
        fileText += "\n"
        fileText += "Timing :  " + tim_ing.get()
        fileText += "\n"

        file.write(fileText)
        file.close()
        messagebox.showinfo("Ticket Details", fileText)
    def readfile():
        def generate():
                def information():
                        info= open("user.txt","r")
                        me=info.read()
                        mytext.insert(END,me)
                information()
        app = Tk()
        app.geometry("500x500")
        app.title("Python File Handling in Forms")
        button4 = Button(app,text="Generate Ticket",command=generate,width="30",height="2",bg="grey")
        button4.place(x=15,y=100)
        mytext=Text(app,width='40',height='15')
        mytext.pack()
    app = Tk()
    app.geometry("700x500")
    app.title("Python File Handling in Forms")

    heading = Label(text="Hello! And Welcome To The Air-Line Reservation",fg="black",bg="yellow",width="500",height="3",font="10")
    heading.pack()
    firstname_text = Label(text="First Name :")
    lastname_text = Label(text="Last Name :")
    age_text = Label(text="Age :")
    gender_text=Label(text="Gender :")
    phone_text=Label(text="Phone Number :")
    country_text=Label(text="Country Name :")
    city_text=Label(text="City Name :")
    class_text=Label(text="Select Flight Class :")

    firstname_text.place(x=15,y=70)
    lastname_text.place(x=15,y=140)
    age_text.place(x=15,y=210)
    gender_text.place(x=15,y=280)
    phone_text.place(x=250,y=70)
    country_text.place(x=250,y=140)
    city_text.place(x=250,y=210)
    class_text.place(x=250,y=280)

    firstname = StringVar()
    lastname = StringVar()
    age = IntVar()
    gender=StringVar()
    phone=StringVar()
    country=StringVar()
    city=StringVar()
    flight_class = StringVar()
    flight_class.set("Choose Your Class")
    seat_num = StringVar()
    seat_num.set("1234")
    tim_ing = StringVar()
    tim_ing.set("11:30 AM")

    first_name_entry = Entry(textvariable=firstname,width="30")
    last_name_entry = Entry(textvariable=lastname,width="30")
    age_entry = Entry(textvariable=age,width="30")
    gender1_entry = Entry(textvariable=gender,width="30")
    phone_num_entry = Entry(textvariable=phone,width="30")
    country_entry = Entry(textvariable=country,width="30")
    city_entry = Entry(textvariable=city,width="30")
    flight_class_menu = OptionMenu(app, flight_class, "Buisness Class", "Economy Class")
    flight_class_menu.config(width="30")
    first_name_entry.place(x=15,y=100)
    last_name_entry.place(x=15,y=170)
    age_entry.place(x=15,y=240)
    gender1_entry.place(x=15,y=310)
    phone_num_entry.place(x=250,y=100)
    country_entry.place(x=250,y=170)
    city_entry.place(x=250,y=240)
    flight_class_menu.place(x=250, y=310)

    button = Button(app,text="Submit Data",command=save_info,width="30",height="2",bg="grey")
    button.place(x=35,y=450)
    button1=Button(app,text=" Ticket",command=readfile,width="30",height="2",bg="grey")
    button1.place(x=300,y=450)
    mainloop()




except Exception as err:
    print(err)
else:
    print("Successfully Computed ")


             

