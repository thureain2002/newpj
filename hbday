import tkinter as tk
from tkinter import messagebox
import pygame  # For playing the birthday song
from PIL import Image, ImageTk  # Import Pillow for handling images
from datetime import datetime, timedelta

# Initialize Pygame mixer
pygame.mixer.init()

# Function to validate login
def validate_login():
    username = username_entry.get()
    password = password_entry.get()

    # Check if the credentials are correct
    if username == "aaaa" and password == "aaaa":
        messagebox.showinfo("Login Success", "Welcome, Ruby! You are logged in.")
        open_wish_window()  # Open the new window with buttons
    else:
        messagebox.showerror("Login Failed", "Incorrect username or password. Please try again.")

# Function to display the birthday wish
def show_wish():
    messagebox.showinfo("Birthday Wish For Ruby", "Happy Birthday, my dearest Ruby! You light up my world with your warmth, love, and endless charm. May your day be as radiant as your smile and as special as you are to me. Here’s to celebrating you today and every day! I love you endlessly. 💖🎉")

# Function to play the birthday song
def play_birthday_song():
    try:
        pygame.mixer.music.load("C:/Users/MSI PS42 Modern 8RA/Desktop/TRK/RUBY/birthday_song.mp3")
        pygame.mixer.music.play()  # Play the song
        messagebox.showinfo("Birthday Song For Ruby", "Playing Happy Birthday Song ")
    except Exception as e:
        messagebox.showerror("Error", "Couldn't play the song. Make sure the 'birthday_song.mp3' file exists.")

# Function to create a live countdown
def calculate_days():
    # Start date: November 29, 2000
    birth_date = datetime(2000, 11, 29)

    # Create a new window for the countdown
    countdown_window = tk.Toplevel(root)
    countdown_window.title("Live Countdown")
    countdown_window.geometry("400x200")

    countdown_label = tk.Label(countdown_window, text="", font=("Helvetica", 16))
    countdown_label.pack(pady=20)

    def update_countdown():
        # Get the current date and time
        now = datetime.now()

        # Calculate the difference
        delta = now - birth_date

        # Extract years, days, hours, minutes, and seconds
        years = delta.days // 365
        days = delta.days % 365
        hours, remainder = divmod(delta.seconds, 3600)
        minutes, seconds = divmod(remainder, 60)

        # Update the label with the countdown
        countdown_label.config(
            text=f"Time Since Nov 29, 2000:\n"
                 f"{years} years, {days} days\n"
                 f"{hours:02} hours, {minutes:02} minutes, {seconds:02} seconds"
        )

        # Schedule the function to update every 1000 ms (1 second)
        countdown_window.after(1000, update_countdown)

    # Start the countdown loop
    update_countdown()

# Function to display the zodiac sign
def show_zodiac_sign():
    messagebox.showinfo("Zodiac Sign", "Ruby's Zodiac Sign is : Sagittarius")
    messagebox.showinfo("About Sagittarius","Sagittarius ♐ (November 22 - December 21) is a fire sign ruled by Jupiter. Known for their adventurous, optimistic, and free-spirited nature, they love exploring new ideas, places, and experiences. Sagittarians are honest, curious, and intellectual but can be blunt, impatient, and restless. They value independence and thrive in relationships that allow personal growth and freedom. Energetic and generous, they inspire others with their enthusiasm and big-picture thinking.")

# Function to create and open the wish window
# Function to create and open the wish window
def open_wish_window():
    # Create a new window for the birthday wish and song
    wish_window = tk.Toplevel(root)
    wish_window.title("Birthday Features")
    wish_window.geometry("400x400")

    # Set background image for the window (adjust the path as needed)
    background_image = Image.open("C:/Users/MSI PS42 Modern 8RA/Desktop/TRK/RUBY/photo_2024-11-29_16-40-08.jpg")
    background_image = background_image.resize((400, 400))  # Resize image to fit window size
    background_photo = ImageTk.PhotoImage(background_image)

    # Create a Label widget to display the background image
    background_label = tk.Label(wish_window, image=background_photo)
    background_label.place(relwidth=1, relheight=1)  # Make the background cover the entire window

    # Keep a reference to the image object (required to prevent garbage collection)
    background_label.image = background_photo

    # Button to show the birthday wish
    wish_button = tk.Button(wish_window, text="Press for Birthday Wish", command=show_wish, bg="lightblue", font=("Arial", 12, "bold"))
    wish_button.place(x=100, y=50, width=200, height=40)  # Position at the top center

    # Button to play the birthday song
    song_button = tk.Button(wish_window, text="Press for Birthday Song", command=play_birthday_song, bg="lightgreen", font=("Arial", 12, "bold"))
    song_button.place(x=100, y=110, width=200, height=40)  # Below the first button

    # Button to calculate days since November 29, 2000
    countdown_button = tk.Button(wish_window, text="Live Countdown ", command=calculate_days, bg="lightyellow", font=("Arial", 12, "bold"))
    countdown_button.place(x=100, y=170, width=200, height=40)  # Below the second button

    # Button to display zodiac sign
    zodiac_button = tk.Button(wish_window, text="Zodiac Sign for Ruby", command=show_zodiac_sign, bg="pink", font=("Arial", 12, "bold"))
    zodiac_button.place(x=100, y=230, width=200, height=40)  # Below the third button

    # Bind keys to trigger the functions
    wish_window.bind('<Return>', lambda event: show_wish())  # Enter key
    wish_window.bind('<F1>', lambda event: show_wish())  # F1 key
    wish_window.bind('<F2>', lambda event: play_birthday_song())  # F2 key
    wish_window.bind('<F3>', lambda event: calculate_days())  # F3 key
    wish_window.bind('<F4>', lambda event: show_zodiac_sign())  # F4 key

    # Focus the new window to make it active
    wish_window.focus_set()


# Initialize the main (login) window
root = tk.Tk()
root.title("Login")
root.geometry("300x200")

# Set background image for the login window (adjust the path as needed)
background_image = Image.open("C:/Users/MSI PS42 Modern 8RA/Desktop/TRK/RUBY/photo_2024-11-29_16-40-06.jpg")
background_image = background_image.resize((300, 200))  # Resize image to fit window size
background_photo = ImageTk.PhotoImage(background_image)

# Create a Label widget to display the background image
background_label = tk.Label(root, image=background_photo)
background_label.place(relwidth=1, relheight=1)  # Make the background cover the entire window

# Keep a reference to the image object (required to prevent garbage collection)
background_label.image = background_photo

# Create and place labels, entries, and buttons for login
username_label = tk.Label(root, text="Username:", bg="white")
username_label.pack(pady=5)

username_entry = tk.Entry(root, width=30)
username_entry.pack(pady=5)

password_label = tk.Label(root, text="Password:", bg="white")
password_label.pack(pady=5)

password_entry = tk.Entry(root, width=30, show="*")  # show="*" hides the password
password_entry.pack(pady=5)

login_button = tk.Button(root, text="Login", command=validate_login)
login_button.pack(pady=20)

# Run the Tkinter event loop
root.mainloop()
