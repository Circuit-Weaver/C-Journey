Here's a beginner-friendly Linux cheat sheet focused on the commands you'll use every day while learning C, Git, and working on your brother's server.

# 🐧 Linux Cheat Sheet for Beginners

> Learn the commands you actually use every day.

---

# 📂 Navigation

## Where am I?

```bash
pwd
```

Print the current working directory.

---

## List files

```bash
ls
```

Useful options:

```bash
ls -l      # Long format
ls -a      # Show hidden files
ls -la     # Long + hidden
```

---

## Change directory

```bash
cd folder
```

Go back one folder:

```bash
cd ..
```

Go to your home directory:

```bash
cd
```

Go to the previous directory:

```bash
cd -
```

Go to the root directory:

```bash
cd /
```

---

# 📁 Creating Things

Create a folder:

```bash
mkdir project
```

Create nested folders:

```bash
mkdir -p projects/c/hello
```

Create a file:

```bash
touch notes.md
```

---

# 📄 Viewing Files

Display file contents:

```bash
cat file.txt
```

View long files:

```bash
less file.txt
```

Show the first 10 lines:

```bash
head file.txt
```

Show the last 10 lines:

```bash
tail file.txt
```

Follow a growing log file:

```bash
tail -f log.txt
```

---

# ✏️ Editing Files

Nano (easy for beginners):

```bash
nano file.c
```

VS Code (if installed):

```bash
code .
```

---

# 📦 File Management

Copy a file:

```bash
cp file.txt backup.txt
```

Copy a folder:

```bash
cp -r project backup
```

Rename or move:

```bash
mv old.txt new.txt
```

Move to another folder:

```bash
mv file.txt Documents/
```

Delete a file:

```bash
rm file.txt
```

Delete a folder:

```bash
rm -r folder
```

Delete an empty folder:

```bash
rmdir folder
```

---

# 🔍 Finding Things

Find a file:

```bash
find . -name "hello.c"
```

Search for text:

```bash
grep "printf" hello.c
```

Search recursively:

```bash
grep -r "main" .
```

---

# ⚙️ Permissions

Make a script executable:

```bash
chmod +x script.sh
```

Run it:

```bash
./script.sh
```

---

# 👤 User Information

Current user:

```bash
whoami
```

Current date:

```bash
date
```

System information:

```bash
uname -a
```

---

# 📊 Disk Usage

Show disk space:

```bash
df -h
```

Show folder sizes:

```bash
du -sh *
```

---

# ⚡ Command History

Show previous commands:

```bash
history
```

Repeat the previous command:

```bash
!!
```

Search command history:

```bash
Ctrl + R
```

---

# 🔑 SSH (Remote Server)

Connect to a server:

```bash
ssh username@server-ip
```

Example:

```bash
ssh rawan@192.168.1.50
```

Exit the server:

```bash
exit
```

or press:

```text
Ctrl + D
```

---

# 📤 Copy Files with SCP

Copy a local file to the server:

```bash
scp hello.c username@server:/home/username/
```

Copy a file from the server:

```bash
scp username@server:/home/username/hello.c .
```

Copy an entire folder:

```bash
scp -r project username@server:/home/username/
```

---

# 🛠️ C Development

Compile:

```bash
gcc hello.c -o hello
```

Run:

```bash
./hello
```

Compile with warnings:

```bash
gcc -Wall hello.c -o hello
```

Compile multiple files:

```bash
gcc main.c utils.c -o app
```

---

# 🌱 Git Basics

Check status:

```bash
git status
```

Initialize a repository:

```bash
git init
```

Add files:

```bash
git add .
```

Commit changes:

```bash
git commit -m "Initial commit"
```

View commit history:

```bash
git log
```

Clone a repository:

```bash
git clone <repository-url>
```

Push changes:

```bash
git push
```

Pull changes:

```bash
git pull
```

---

# 💡 Useful Shortcuts

| Shortcut | Action                 |
| -------- | ---------------------- |
| ↑        | Previous command       |
| ↓        | Next command           |
| Tab      | Auto-complete          |
| Ctrl + C | Stop current program   |
| Ctrl + D | Exit terminal          |
| Ctrl + L | Clear screen           |
| Ctrl + R | Search command history |

---

# ⭐ Commands You'll Use Every Day

```bash
pwd
ls -la
cd
mkdir
touch
cp
mv
rm
cat
nano
find
grep
history
ssh
scp
gcc
git status
git add .
git commit -m "message"
```

---

# 📚 Learning Tip

Don't try to memorize every command.

Instead, learn them as you need them. After using a command a few times in real projects, it becomes second nature. The goal is to understand what each command does and when to use it, not to memorize a long list.
