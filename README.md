# week-4-python-assignment

File Read & Write Challenge 🖋️: Create a program that reads a file and writes a modified version to a new file.
Error Handling Lab 🧪: Ask the user for a filename and handle errors if it doesn’t exist or can’t be read.
Outcomes 🎉

By the end of this module, you’ll be skilled in managing files efficiently in Python, ensuring error-free code that gracefully handles unexpected issues. Mastering files and exception handling will allow you to build strong, robust applications!


def modify_content(content):
    """
    Modify the content of the file (e.g., converting text to uppercase).
    You can replace this with any other modification logic.
    """
    return content.upper()  # Example: Convert all text to uppercase

def main():
    # Ask the user for the filename
    input_filename = input("Please enter the input filename: ")
    output_filename = input("Please enter the output filename: ")

    try:
        # Attempt to open the file for reading
        with open(input_filename, 'r') as file:
            content = file.read()  # Read the content of the file
            modified_content = modify_content(content)  # Modify the content
        
        # Write the modified content to a new file
        with open(output_filename, 'w') as file:
            file.write(modified_content)  # Write the modified content to output file

        print(f"File processed successfully. Modified content saved to {output_filename}")
    
    except FileNotFoundError:
        print(f"Error: The file '{input_filename}' was not found.")
    
    except PermissionError:
        print(f"Error: You do not have permission to read or write to one of the files.")
    
    except Exception as e:
        print(f"An error occurred: {e}")

if __name__ == "__main__":
    main()
