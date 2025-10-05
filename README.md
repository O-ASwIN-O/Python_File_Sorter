# 🗂️ File Sorter Script  

## 📌 Project Description  
A simple **Python automation script** that organizes files in a folder into subfolders based on file type.  
This helps keep your workspace clean by automatically moving images, data files, and text files into separate folders.  

---

## 💻 Technologies Used  
- Python 3  
- OS module  
- Shutil module  

---

## 🧠 How It Works  
1. Checks for existing folders:  
   - `Images`  
   - `Datas`  
   - `Text files`  

2. If they don’t exist, the script creates them.  
3. Then it scans the directory for files and moves them into the correct folder based on their extension:  
   - `.png`, `.jpg` → **Images**  
   - `.xlsx` → **Datas**  
   - `.txt` → **Text files**  

---

## 🧩 Code Explanation  
```python
import os, shutil

# Folder path
path = r"C:/Users/ASWIN/file_sort/"  #ADD YOUR PATH!

# List all files in the directory
files_avaliable = os.listdir(path)

# Folder names to create
folder_names = ['Images', 'Datas', 'Text files'] #ADD MORE IF YOU WANT!

# Create folders if not present
for i in range(0, 3):
    if not os.path.exists(path + folder_names[i]):
        os.makedirs(path + folder_names[i])

# Move files based on extension
for file in files_avaliable:
    if ".xlsx" in file and not os.path.exists(path + "Datas/" + file):
        shutil.move(path + file, path + "Datas/" + file)
    elif (".png" in file or ".jpg" in file) and not os.path.exists(path + "Images/" + file):
        shutil.move(path + file, path + "Images/" + file)
    elif ".txt" in file and not os.path.exists(path + "Text files/" + file):
        shutil.move(path + file, path + "Text files/" + file)
#ONLY MENTIONED FILE EXTNSION ARE GONA WORK..
