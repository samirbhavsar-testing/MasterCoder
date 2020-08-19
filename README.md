# MasterCoderfrom tkinter import *
import tkinter as tk
import calendar
import random

time = 2000

global lower
global upper
true_number = random.randrange(1, 50)

def status():
    root.destroy()


def call():
    # lblTitle1.config(text="Please wait! Returning your Card")
    # lblTitle2.config(text="")
    root.after(time, status)


class Win:
    def __init__(self, root):
        """Define window for the app"""
        self.root = root
        self.root.geometry("1200x750+0+0")
        self.root.resizable(0, 0)
        self.root.title("Master Coder")
        self.show_widgets()

    def show_widgets(self):
        var2 = DoubleVar()
        Tops = Frame(root, width=1200, height=50, bd=8, relief=FLAT)
        Tops.pack(side=TOP)
        lblTitle = Label(Tops, text="      Master Coder     ", padx=16, pady=2, bd=8,
                         fg="white", font=('arial', 40, 'bold'), bg="#3b5998",
                         relief=RAISED, width=80, height=1)
        lblTitle.pack()
        f1 = Frame(root, width=600, height=750, bd=8, bg="#dfe3ee", relief=GROOVE)
        f1.pack(side=LEFT)
        f1a = Frame(f1, width=180, height=750, bd=6, bg="#dfe3ee", relief=FLAT)
        f1a.pack(side=TOP)

        buttonbal = Button(f1a, padx=36, pady=10, text="Balance", fg="green", height=2, relief='ridge',
                           font=('arial', 10, 'bold'))
        buttonbal.place(x=20, y=320)
        buttpnpin = Button(f1a, padx=38, pady=10, text="PIN Service", fg="green", width=6, height=2, relief='ridge',
                           font=('arial', 10, 'bold'))
        buttpnpin.place(x=20, y=400)
        buttondepo = Button(f1a, padx=30, pady=10, text="Deposit", fg="green", width=8, height=2, relief='ridge',
                            font=('arial', 10, 'bold'))
        buttondepo.place(x=20, y=480)
        buttona = Button(f1a, padx=30, pady=10, text="Guess Game", fg="green", width=8, height=2, relief='ridge',
                         font=('arial', 10, 'bold'), command=lambda: self.new_window(Win5))
        buttona.place(x=20, y=560)

        f2 = Frame(root, width=600, height=750, bd=8, bg="#dfe3ee", relief=GROOVE)
        f2.pack(side=RIGHT)
        f1b = Frame(f2, width=180, height=750, bd=8, bg="#dfe3ee", relief=FLAT)
        f1b.pack(side=TOP)
        buttonclr = Button(f1b, padx=28, pady=10, text="Area of Circle", fg="green", height=2, relief='ridge',
                           font=('arial', 10, 'bold'), command=lambda: self.new_window(Win4))
        buttonclr.place(x=1, y=320)
        self.buttoncal = Button(f1b, padx=42, pady=10, text="Calendar", fg="green", height=2, relief='ridge',
                                font=('arial', 10, 'bold'), command=lambda: self.new_window(Win3))
        self.buttoncal.place(x=0, y=400)
        self.button_rename = tk.Button(f1b, text="Arm Strong",
                                       command=lambda: self.new_window(Win2), padx=35, pady=10, fg="green", height=2,
                                       relief='ridge',
                                       font=('arial', 10, 'bold'))
        self.button_rename.place(x=0, y=480)
        self.buttonq = Button(f1b, padx=20, pady=10, text="Quit Application", fg="green", height=2, relief='ridge',
                              font=('arial', 10, 'bold'), command=lambda: call())
        self.buttonq.place(x=0, y=560)

        f3 = Frame(root, width=800, height=750, bd=8, bg="#8b9dc3", relief=GROOVE)
        f3.pack(side=TOP)

        f3c = Frame(f3, width=800, height=200, bd=8, bg="#dfe3ee", relief=SUNKEN)
        f3c.pack(side=TOP)
        lblTitle1 = Label(f3c, padx=1, pady=5, bd=4, fg="black", font=('arial', 10, 'bold'), bg="#dfe3ee",
                          relief=SUNKEN, width=131, height=9)
        lblTitle1.pack()
        lblTitle2 = Label(f3c, padx=1, pady=5, bd=4, fg="black", font=('arial', 10, 'bold'), bg="#dfe3ee",
                          relief=SUNKEN, width=131, height=9)
        lblTitle2.pack()

        var2.set("")

        f3a = Frame(f3, width=460, height=500, bd=8, bg="#8b9dc3", relief=FLAT)
        f3a.pack(side=LEFT)

        f3b = Frame(f3, width=460, height=500, bd=8, bg="#8b9dc3", relief=FLAT)
        f3b.pack(side=RIGHT)

    def new_window(self, _class):
        try:
            if self.new.state() == "normal":
                self.new.focus()
        except:
            self.new = tk.Toplevel(self.root)
            _class(self.new)


class Win2(Win):
    def __init__(self, root):
        print(app.new.state())
        self.root = root
        windowWidth = self.root.winfo_reqwidth()
        windowHeight = self.root.winfo_reqheight()
        positionRight = int(self.root.winfo_screenwidth() / 2 - windowWidth / 2)
        positionDown = int(self.root.winfo_screenheight() / 2 - windowHeight / 2)
        self.root.geometry("300x250+{}+{}".format(positionRight, positionDown))
        self.root.resizable(0, 0)
        self.root["bg"] = "yellow"
        self.root.title("Arm Strong")
        self.show_widgets()
        self.onoff()

    def arm(self):
        self.txtheight.delete(0.0, 'end')
        var2 = DoubleVar()
        num = int(self.txt2.get())
        sum = 0
        temp = num
        while temp > 0:
            digit = temp % 10
            sum += digit ** 3
            temp = temp // 10
        if num == sum:
            self.txtheight.insert(0.0, "Number is ARMSTRONG")
            print("Number is ARMSTRONG")
        else:
            self.txtheight.insert(0.0, "Number is not ARMSTRONG")
            print("Number is not ARMSTRONG")

    def onoff(self):
        root.withdraw()

    def show_widgets(self):
        self.buttonq1 = Button(self.root, padx=28, pady=1, text="Quit Application", fg="green", height=2,
                               relief='ridge',
                               font=('arial', 10, 'bold'), command=lambda: self.close_window())
        self.buttonq1.place(x=80, y=200)
        self.buttonq3 = Button(self.root, padx=105, pady=1, text="Calculate", fg="green", height=2,
                               relief='ridge',
                               font=('arial', 10, 'bold'), command=lambda: self.arm())
        self.buttonq3.place(x=10, y=90)
        self.txtheight = Text(self.root, font=('arial', 10, 'bold'), bd=4, width=38, wrap=WORD)
        self.txtheight.place(x=10, y=140, height=50)
        self.txt2 = Entry(self.root, font=('arial', 16, 'bold'), bd=4, width=23)
        self.txt2.place(x=10, y=40, height=40)
        self.lblTitle3 = Label(self.root, padx=1, pady=5, bd=2, fg="black", font=('arial', 8, 'bold'), bg="#dfe3ee",
                               relief=FLAT, width=42, height=2,
                               text="Enter Number to Check if it is an ArmStrong Number")
        self.lblTitle3.grid(row=1)

    def close_window(self):
        self.root.destroy()
        root.deiconify()


class Win3(Win):
    def __init__(self, root):
        print(app.new.state())
        self.root = root
        windowWidth = self.root.winfo_reqwidth()
        windowHeight = self.root.winfo_reqheight()
        positionRight = int(self.root.winfo_screenwidth() / 2 - windowWidth / 2)
        positionDown = int(self.root.winfo_screenheight() / 2 - windowHeight / 2)
        self.root.geometry("300x300+{}+{}".format(positionRight, positionDown))
        self.root.resizable(0, 0)
        self.root["bg"] = "yellow"
        self.root.title("Calendar")
        self.show_widgets()
        self.onoff()

    def calendar(self):
        y = int(self.txt2.get())
        m = int(self.txt3.get())
        print(calendar.month(y, m))
        self.txtheight.insert(0.0, calendar.month(y, m))

    def onoff(self):
        root.withdraw()

    def show_widgets(self):
        self.frame = tk.Frame(self.root, bg="green")
        self.buttonq2 = Button(self.root, padx=93, pady=5, text="Quit Application", fg="green", height=1,
                               relief='ridge',
                               font=('arial', 10, 'bold'), command=lambda: self.close_window())
        self.buttonq2.place(x=1, y=265)
        self.buttonq3 = Button(self.root, padx=98, pady=10, text="Print Calendar", fg="green", height=1,
                               relief='ridge',
                               font=('arial', 10, 'bold'), command=lambda: self.calendar())
        self.buttonq3.place(x=1, y=80)
        self.txtheight = Text(self.root, font=('arial', 10, 'bold'), bd=2, width=41)
        self.txtheight.place(x=2, y=125, height=140)
        self.txt2 = Entry(self.root, font=('arial', 16, 'bold'), bd=4, width=13)
        self.txt2.place(x=130, y=1, height=40)
        self.txt3 = Entry(self.root, font=('arial', 16, 'bold'), bd=4, width=13)
        self.txt3.place(x=130, y=40, height=40)
        self.lblTitle3 = Label(self.root, padx=1, pady=6, bd=4, fg="black", font=('arial', 10, 'bold'), bg="#dfe3ee",
                               relief=FLAT, width=15, height=1,
                               text="Enter Year(YYYY)")
        self.lblTitle3.grid(row=1)
        self.lblTitle2 = Label(self.root, padx=1, pady=10, bd=4, fg="black", font=('arial', 10, 'bold'), bg="#dfe3ee",
                               relief=FLAT, width=15, height=1,
                               text="Enter Month(MM)")
        self.lblTitle2.grid(row=2)
        self.frame.pack()

    def close_window(self):
        self.root.destroy()
        root.deiconify()


class Win4(Win):
    def __init__(self, root):
        print(app.new.state())
        self.root = root
        windowWidth = self.root.winfo_reqwidth()
        windowHeight = self.root.winfo_reqheight()
        positionRight = int(self.root.winfo_screenwidth() / 2 - windowWidth / 2)
        positionDown = int(self.root.winfo_screenheight() / 2 - windowHeight / 2)
        self.root.geometry("300x250+{}+{}".format(positionRight, positionDown))
        self.root.resizable(0, 0)
        self.root["bg"] = "yellow"
        self.root.title("Area of Circle")
        self.show_widgets()
        self.onoff()

    def area(self):
        self.txtheight.delete(0.0, 'end')
        var2 = DoubleVar()
        radius = float(self.txt2.get())
        area = 3.1416 * radius * radius
        print(area)
        self.txtheight.insert(0.0, area)

    def onoff(self):
        root.withdraw()

    def show_widgets(self):
        self.buttonq1 = Button(self.root, padx=90, pady=6, text="Quit Application", fg="green", height=1,
                               relief='ridge',
                               font=('arial', 10, 'bold'), command=lambda: self.close_window())
        self.buttonq1.place(x=5, y=205)
        self.buttonq3 = Button(self.root, padx=110, pady=6, text="Calculate", fg="green", height=1,
                               relief='ridge',
                               font=('arial', 10, 'bold'), command=lambda: self.area())
        self.buttonq3.place(x=5, y=90)
        self.txtheight = Text(self.root, font=('arial', 16, 'bold'), bd=4, width=24, wrap=WORD)
        self.txtheight.place(x=1, y=160, height=40)
        self.txt2 = Entry(self.root, font=('arial', 16, 'bold'), bd=4, width=24)
        self.txt2.place(x=1, y=40, height=40)
        self.lblTitle3 = Label(self.root, padx=2, pady=5, bd=2, fg="black", font=('arial', 10, 'bold'), bg="#dfe3ee",
                               relief=FLAT, width=36, height=1,
                               text="Enter Radius of Circle")
        self.lblTitle3.place(x=1, y=1)
        self.lblTitle4 = Label(self.root, padx=2, pady=5, bd=2, fg="black", font=('arial', 10, 'bold'), bg="#dfe3ee",
                               relief=FLAT, width=36, height=1, text="Area of Circle")
        self.lblTitle4.place(x=1, y=130)

    def close_window(self):
        self.root.destroy()
        root.deiconify()


class Win5(Win):
    def __init__(self, root):
        print(app.new.state())
        self.root = root
        windowWidth = self.root.winfo_reqwidth()
        windowHeight = self.root.winfo_reqheight()
        positionRight = int(self.root.winfo_screenwidth() / 2 - windowWidth / 2)
        positionDown = int(self.root.winfo_screenheight() / 2 - windowHeight / 2)
        self.root.geometry("300x250+{}+{}".format(positionRight, positionDown))
        self.root.resizable(0, 0)
        self.root["bg"] = "yellow"
        self.root.title("Guess Game")
        self.show_widgets()
        self.onoff()

    def guess(self):
        self.txtheight.delete(0.0, 'end')
        guess_number = int(self.txt2.get())
        if guess_number == true_number:
            self.txtheight.insert(0.0, "You are RIGHT! Good JOB!")
        elif guess_number < true_number:
            self.txtheight.insert(0.0, "Your GUESS IS LOW, TRY AGAIN")
        else:
            self.txtheight.insert(0.0, "Your GUESS IS HIGH, TRY AGAIN")


    def onoff(self):
        root.withdraw()

    def show_widgets(self):
        self.buttonq1 = Button(self.root, padx=68, pady=10, text="Quit Application", fg="green", height=1,
                               relief='ridge',
                               font=('arial', 10, 'bold'), command=lambda: self.close_window())
        self.buttonq1.place(x=30, y=200)
        self.buttonq3 = Button(self.root, padx=102, pady=10, text="Enter", fg="green", height=1,
                               relief='ridge',
                               font=('arial', 10, 'bold'), command=lambda: self.guess())
        self.buttonq3.place(x=30, y=90)
        self.txtheight = Text(self.root, font=('arial', 10, 'bold'), bd=4, width=34, wrap=WORD)
        self.txtheight.place(x=30, y=140, height=40)
        self.txt2 = Entry(self.root, font=('arial', 16, 'bold'), bd=4, width=20)
        self.txt2.place(x=30, y=40, height=40)
        self.lblTitle3 = Label(self.root, padx=1, pady=5, bd=4, fg="black", font=('arial', 10, 'bold'), bg="#dfe3ee",
                               relief=FLAT, width=30, height=1,
                               text="Guess The Number between 1 and 50")
        self.lblTitle3.place(x=30, y=1)

    def close_window(self):
        self.root.destroy()
        root.deiconify()


if __name__ == "__main__":
    root = tk.Tk()
    app = Win(root)
    app.root.title("Master Coder")
    root.mainloop()
