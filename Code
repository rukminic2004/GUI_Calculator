import tkinter as tk
from tkinter import messagebox

#Colors
BG_COLOR = "#b2e0e8"         # Calculator background
DISPLAY_COLOR = "#eaf9f9"
BTN_NUM_COLOR = "#ffffff"    # Number buttons
BTN_OP_COLOR = "#d4a5d6"     # Operators: +, -, ×, ÷
BTN_EQ_COLOR = "#f7f395"     # Equal button
BTN_CLR_COLOR = "#c3e88d"    # Power button
FONT = ("Comic Sans MS", 22, "bold")

#Click Handler
def click(event):
    current = entry.get()
    value = event.widget["text"]

    if value == "=":
        try:
            result = eval(current.replace("×", "*").replace("÷", "/"))
            entry.delete(0, tk.END)
            entry.insert(0, str(result))
        except:
            messagebox.showerror("Oops!", "Invalid expression 💥")
    elif value == "C":
        entry.delete(0, tk.END)
    else:
        entry.insert(tk.END, value)

#Main window
root = tk.Tk()
root.title("CuteCalc 3000 🧁")
root.geometry("360x540")
root.configure(bg=BG_COLOR)
root.resizable(False, False)

#Display
entry = tk.Entry(root, font=FONT, justify="right", bd=10, relief="sunken", bg=DISPLAY_COLOR)
entry.pack(padx=20, pady=20, fill="x")

#Buttons layout (like image)
buttons = [
    ["7", "8", "9", "÷"],
    ["4", "5", "6", "×"],
    ["1", "2", "3", "-"],
    ["C", "0", "=", "+"],
]

#Frame for buttons
btn_frame = tk.Frame(root, bg=BG_COLOR)
btn_frame.pack()

#Generate buttons
for r, row in enumerate(buttons):
    row_frame = tk.Frame(btn_frame, bg=BG_COLOR)
    row_frame.pack(pady=5)
    for c, item in enumerate(row):
        # Pick button color
        if item in "0123456789":
            color = BTN_NUM_COLOR
        elif item == "=":
            color = BTN_EQ_COLOR
        elif item == "C":
            color = BTN_CLR_COLOR
        else:
            color = BTN_OP_COLOR

        btn = tk.Button(
            row_frame, text=item, font=FONT,
            bg=color, fg="black",
            width=4, height=2, relief="flat", bd=3
        )
        btn.pack(side="left", padx=6)
        btn.bind("<Button-1>", click)

#Launch GUI
root.mainloop()
