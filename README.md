# Basic-Calculator-Code-Using-Tkinter
pretty self self explanatory, i havent explained it with #'s but ill do it in the near future


import tkinter as tk
root  = tk.Tk()

root.geometry("200x350")
root.title("Calc.")
root.configure(bg="lightblue")
root.resizable(False, False)

entery = tk.Entry(root, width=30)
entery.grid(row=0, column=1, columnspan=3, padx=10, pady=10)

button1 = tk.Button(root, text="1", width=5, height=2, command = lambda: entery.insert(tk.END,"1"))
button1.grid(row=1, column=1, padx=5, pady=5)

button2 = tk.Button(root, text="2", width=5, height=2, command = lambda: entery.insert(tk.END,"2"))
button2.grid(row=1, column=2, padx=5, pady=5)

button3 = tk.Button(root, text="3", width=5, height=2, command = lambda: entery.insert(tk.END,"3"))
button3.grid(row=1, column=3, padx=5, pady=5)

button4 = tk.Button(root, text="4", width=5, height=2, command = lambda: entery.insert(tk.END,"4"))
button4.grid(row=2  , column=1, padx=5, pady=5)

button5 = tk.Button(root, text="5", width=5, height=2, command = lambda: entery.insert(tk.END,"5"))
button5.grid(row=2, column=2, padx=5, pady=5)

button6 = tk.Button(root, text="6", width=5, height=2, command = lambda: entery.insert(tk.END,"6"))
button6.grid(row=2, column=3, padx=5, pady=5)

button7 = tk.Button(root, text="7", width=5, height=2, command = lambda: entery.insert(tk.END,"7"))
button7.grid(row=3, column=1, padx=5, pady=5)

button8 = tk.Button(root, text="8", width=5, height=2, command = lambda: entery.insert(tk.END,"8"))
button8.grid(row=3, column=2, padx=5, pady=5)   

button9 = tk.Button(root, text="9", width=5, height=2, command = lambda: entery.insert(tk.END,"9"))
button9.grid(row=3, column=3, padx=5, pady=5)   
    
button0 = tk.Button(root, text="0", width=5, height=2, command = lambda: entery.insert(tk.END,"0"))
button0.grid(row=4, column=2, padx=5, pady=5)   

buttonPLUS = tk.Button(root, text="+", width= 5, height=2, command = lambda: entery.insert(tk.END, "+"))
buttonPLUS.grid(row=5, column=1, padx =5, pady=5)

buttonMINUS = tk.Button(root, text = "-", width = 5, height = 2, command = lambda: entery.insert(tk.END, "-"))
buttonMINUS.grid(row=5, column=2, padx =5, pady=5)

buttonMULTI = tk.Button(root, text = "*", width = 5 , height = 2, command = lambda: entery.insert(tk.END, "*"))
buttonMULTI.grid(row=5, column=3, padx =5, pady=5)

buttonDIV = tk.Button(root, text = "//", width = 5, height = 2, command = lambda: entery.insert(tk.END, "//"))
buttonDIV.grid(row=6, column=1, padx =5, pady=5)

buttonEQUALS = tk.Button(root, text = "=", width = 5, height = 2)
buttonEQUALS.grid(row=6, column=2, padx =5, pady=5)

buttonCLEAR = tk.Button(root, text = "C", width = 5, height = 2, command = lambda: entery.delete(0, tk.END))
buttonCLEAR.grid(row=6, column=3, padx =5, pady=5)


def calculate():
    try:
        result = eval(entery.get())
        entery.delete(0, tk.END)
        entery.insert(tk.END, str(result))
    except:
        entery.delete(0, tk.END)
        entery.insert(tk.END, "Error")

buttonEQUALS.config(command=calculate)

root.mainloop()
