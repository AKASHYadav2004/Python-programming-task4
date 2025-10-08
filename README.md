# Python-programming-task4
import os

def rename_files(folder_path, file_prefix):
    """
    Rename files in a folder with a naming pattern.

    Args:
        folder_path (str): Path to the folder containing files to rename.
        file_prefix (str): Prefix for the new file names.

    Returns:
        None
    """
    # Get a list of files in the folder
    files = [f for f in os.listdir(folder_path) if os.path.isfile(os.path.join(folder_path, f))]

    # Rename files with a naming pattern
    for i, file in enumerate(files):
        # Get the file extension
        file_ext = os.path.splitext(file)[1]

        # Create the new file name
        new_file_name = f"{file_prefix}_{i+1}{file_ext}"

        # Rename the file
        os.rename(os.path.join(folder_path, file), os.path.join(folder_path, new_file_name))

        print(f"Renamed {file} to {new_file_name}")

# Example usage
folder_path = "/path/to/your/folder"
file_prefix = "file"

rename_files(folder_path, file_prefix)
