# Database-Assignment
def modify_content(content):
    # Sanple modification: convert text to uppercase
    return content.upper()

def main():
    try:
        # Ask user for input filename
        input_filename = input("Enter the name of the file to read: ")
        
        # Try to open and read the file
        with open(input_filename, "r") as infile:
            content = infile.read()
        
        # Modify the content
        modified_content = modify_content(content)
        
        # Ask user for output filename
        output_filename = input("Enter the name of the file to write to: ")
        
        # Write the modified content to the new file
        with open(output_filename, "w") as outfile:
            outfile.write(modified_content)
        
        print("✅ File has been successfully modified and saved as", output_filename)

    except FileNotFoundError:
        print(" Error: The file does not exist.")
    except PermissionError:
        print(" Error: You do not have permission to read/write this file.")
    except Exception as e:
        print(f" An unexpected error occurred: {e}")

if __name__ == "__main__":
    main()
