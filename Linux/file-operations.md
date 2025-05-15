# 📁 Basics of File Operations in Linux

This guide covers basic file and directory operations using the Linux terminal — perfect for beginners!

---

## 📝 `touch` – Create Empty Files

### **1. Create a new empty file**
```sh
$ touch filename.txt
```

### **2. Create multiple files at once**
```sh
$ touch file1.txt file2.txt file3.txt
```

---

## 📄 `cp` – Copy Files and Directories

### **1. Copy a file to the same directory with a new name**
```sh
$ cp original.txt copy.txt
```

### **2. Copy a file to another directory**
```sh
$ cp file.txt /path/to/destination/
```

### **3. Copy a directory and its contents (use `-r` for recursive)**
```sh
$ cp -r dir1/ dir2/
```

---

## 📂 `mv` – Move or Rename Files and Directories

### **1. Rename a file**
```sh
$ mv oldname.txt newname.txt
```

### **2. Move a file to another directory**
```sh
$ mv file.txt /path/to/destination/
```

### **3. Move and rename in one step**
```sh
$ mv file.txt /path/to/destination/newname.txt
```

---

## 🗑️ `rm` – Remove (Delete) Files and Directories

### ⚠️ Be careful — deletion is permanent.

### **1. Delete a file**
```sh
$ rm filename.txt
```

### **2. Delete multiple files**
```sh
$ rm file1.txt file2.txt
```

### **3. Delete an empty directory**
```sh
$ rmdir empty_folder/
```

### **4. Delete a non-empty directory (recursive force)**
```sh
$ rm -rf folder_name/
```

---

## 🧠 Quick Tips

- Use `ls` before and after operations to verify changes.
- Use `-i` with `rm`, `cp`, or `mv` to prompt before overwriting:
  ```sh
  $ rm -i file.txt
  ```

- Use tab for autocompletion of file and folder names.
- Combine with `cd`, `pwd`, and `ls` for better navigation and control.

---

✅ With these commands, you're now equipped to manage files and folders confidently in the Linux terminal!

> 🚨 Always double-check paths when using `rm -rf`. There’s no undo!
