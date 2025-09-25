 Here’s a clean, step-by-step documentation of your workflow, formatted as a guide you can use or share:

---

# 🚀 EC2 + GitHub Setup & Hello World Project

This guide walks through launching an **Amazon Linux EC2 instance**, configuring **Git/GitHub**, creating a simple **Python Hello World** program, and pushing it to GitHub.

---

## 1. Launch & Connect to EC2

* Launch an EC2 instance:

  * **AMI**: Amazon Linux 2023
  * **Instance type**: `t3.micro`
  * **Key pair**: `.pem` file for SSH
  * **Security Group**: allow SSH (port 22)

* Connect via SSH:

```bash
ssh -i "key.pem" ec2-user@<ec2-public-dns>
```

---

## 2. Install Required Packages

```bash
# Update system packages
sudo yum update -y 

# Install Git
sudo yum install git -y 
git --version 

# Install Python
sudo yum install python -y
python --version
```

---

## 3. Configure Git

```bash
git config --global user.name "Atul Kamble"
git config --global user.email "atul_kamble@hotmail.com"
git config --list
```

---

## 4. Setup GitHub Repository

1. Sign in to [GitHub](https://github.com/).
2. Create a new repository named **myrepo**.

   * Add README (optional).
   * Add License (MIT recommended).

---

## 5. Clone Repository into EC2

```bash
git clone https://github.com/atulkamble/myrepo.git
ls
cd myrepo/
ls
```

---

## 6. Create & Test Python File

```bash
# Create Python file
touch helloworld.py
nano helloworld.py
```

Example code inside `helloworld.py`:

```python
print("Hello, World from EC2!")
```

Run the file:

```bash
python3 helloworld.py
```

---

## 7. Push Code to GitHub

```bash
git status
git add helloworld.py 
git status
git commit -m "added hello world python file"
```

### 🔑 GitHub Authentication

* Go to: **GitHub → Settings → Developer settings → Personal Access Tokens → Tokens (classic)**
* Generate a **token (classic)** with `repo` scope.
* Use this token instead of your password when prompted during `git push`.

Push to GitHub:

```bash
git push origin main
```

---

✅ You have successfully:

* Launched an EC2 instance
* Installed Git & Python
* Configured Git
* Created a GitHub repo
* Wrote a Hello World Python file
* Pushed it to GitHub

---

Would you like me to expand this into a **full GitHub-ready README.md** (with emojis, code blocks, and screenshots placeholders) so you can directly upload it to your repo?
