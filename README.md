# projects
import tkinter as tk
from tkinter import *
import pyttsx3

# Initialize the pyttsx3 engine
engine = pyttsx3.init()

# Function to handle text-to-speech
def speaknow():
    engine.say(textv.get())
    engine.runAndWait()
    engine.stop()

# Create the main application window
root = Tk()

# StringVar to hold the text input
textv = StringVar()

# Create a labeled frame for the GUI layout
obj = LabelFrame(root, text="Text to Speech", font=20, bd=1)
obj.pack(fill="both", expand="yes", padx=10, pady=10)

# Label 
lbl = Label(obj, text="Text", font=50)
lbl.pack(side=tk.LEFT, padx=5)

# Entry widget for text input
text_entry = Entry(obj, textvariable=textv, font=30, width=25, bd=5)
text_entry.pack(side=tk.LEFT, padx=10)

# Button to trigger text-to-speech
btn = Button(obj, text="Speak", font=20, bg="yellow", fg="black", command=speaknow)
btn.pack(side=tk.LEFT, padx=10, pady=10)

# Configure the main application window
root.title("Text to Speech")
root.geometry("400x200")  # Set a fixed window size to make sure the button fits
root.resizable(False, False)  # Disable resizing to prevent layout issues

# Run the main event loop
root.mainloop()
