import tkinter as tk
from tkinter import font
from tkinter import *
import datetime as dt
from PIL import ImageTk, Image


# Create the main window
window = tk.Tk()
window.title("Late Chief Ayoade Alasi Family Tree")
window.geometry("600x300")



date = dt.datetime.now()
# Create Label to display the Date
label = Label(window, text=f"{date:%A, %B %d, %Y}", font="Rooney, 30", fg='black')
label.pack(pady=20)

# Create font object
label_font = font.Font(size=10)

# Create a label widget with specific font
label = tk.Label(window, text="You welcome to our cherished platform!", font=label_font, bg="white")
label.pack()

# Pack the label widget to display it

# Load the image
menu_bar = tk.Menu(window)

# Input lists for creating menus
menus_list = ['AbdulYekeen Ayoade','Sidikat', 'Sulat', 'IyaAbass', 'IyaIwo', 'Adebunmi', 'IyaWasiu', 'IyaSegun']
menu_items_list = [
    ['CHILDREN:', 'Jolaade', 'Lateef', 'Semiu', 'Late_Abass', 'Hakeem', 'Monsurat', 'Kunle', 'Remilekun','Olatunde', 'Ambali', 'Wasiu', 'Segun', 'Yinka', 'Deji','Toheeb','Iyabo', 'Toyin', 'Faruq'],
    ['Jolaade', 'Semiu', 'Hakeem', 'Kunle', 'Toheeb'],
    ['Olalere'],
    ['Abass'],
    ['Monsurat', 'Ambali'],
    ['Remilekun', 'Olatunde', 'Adeyinka', 'Iyabo', 'Ayoade'],
    ['Wasiu'],
    ['Segun', 'Deji', 'Toyin'],
]

# Iterate over all menus
for (menu_label, items) in zip(menus_list, menu_items_list):

    # Create menu
    menu = tk.Menu(menu_bar, tearoff=0)
    for item in items:
        menu.add_command(label=item, command=lambda x=item:menu_item_action(x))

    # Add the menu to the menu bar
    menu_bar.add_cascade(label=menu_label, menu=menu)

# Attach the menu bar to the main window and color the bg red
window.config(menu=menu_bar, bg='red')

text=Text(window, width = 60, height = 10, 
          wrap = WORD, padx = 10, pady = 10)
  
# pack the text-Aera in the window
text.pack()



# to make window fixed size
window.resizable(False, False)
window.attributes('-alpha', .9)

# Run the application
window.mainloop()
