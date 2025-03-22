# Basics of Linux Terminal

## `ls` Command
The `ls` command is used to list the contents of a directory.

### **1. List files in the current directory**
```sh
$ ls
```

### **2. List files in a specific directory**
```sh
$ ls /path/to/directory/
```

### **3. Show detailed information about files**
```sh
$ ls -l
```

### **4. Show hidden files (files starting with `.`)**
```sh
$ ls -a
```

### **5. Combine options (-l for details, -a for hidden files)**
```sh
$ ls -la
$ ls -la /path/to/directory/
```

---

## `pwd` Command
The `pwd` (Print Working Directory) command shows the current directory you are in.

```sh
$ pwd
```

Example Output:
```sh
/home/user/Documents
```

---

## `cd` Command
The `cd` (Change Directory) command is used to move between directories.

### **1. Move to a specific directory**
```sh
$ cd /path/to/directory/
```

### **2. Move into a subfolder inside the current directory**
```sh
$ cd folder_name/
```

### **3. Move to the parent directory (one level up)**
```sh
$ cd ..
```

### **4. Move multiple levels up**
```sh
$ cd ../../
```

### **5. Navigate to the home directory**
```sh
$ cd ~
```

### **6. Return to the previous directory**
```sh
$ cd -
```

---

This guide is designed for absolute beginners, helping you get comfortable with basic Linux terminal commands. 🚀
