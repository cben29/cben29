```python
import tkinter as tk
from tkinter import messagebox

# Function to handle the Submit button click
def submit_question():
    question = question_entry.get()  # Get the text entered by the user
    if question.strip():  # Check if the input is not empty
        response_label.config(text=f"You asked: \"{question}\"")  # Update the label with the user's question
    else:
        messagebox.showwarning("Input Error", "Please enter a valid question.")  # Display a warning if input is empty

# Create the main application window
root = tk.Tk()
root.title("Question Input Interface")
root.geometry("400x250")  # Set window size
root.resizable(False, False)  # Prevent resizing the window

# Add a heading label
heading_label = tk.Label(root, text="Ask Your Question", font=("Arial", 16, "bold"))
heading_label.pack(pady=10)

# Add an Entry widget for the question input
question_entry = tk.Entry(root, font=("Arial", 12), width=40)
question_entry.pack(pady=10)

# Add a Submit button
submit_button = tk.Button(root, text="Submit", font=("Arial", 12), bg="#4CAF50", fg="white", command=submit_question)
submit_button.pack(pady=10)

# Add a label to display the response
response_label = tk.Label(root, text="", font=("Arial", 12), fg="#333333")
response_label.pack(pady=20)

# Run the Tkinter event loop
root.mainloop()
