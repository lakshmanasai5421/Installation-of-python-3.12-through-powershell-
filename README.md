# Installing Python 3.12.3 and Creating a Virtual Environment (Windows – PowerShell Guide)

This guide explains how to install **Python 3.12.3 from python.org** on a Windows system using **PowerShell**, and then create a **virtual environment** for your projects.

---

# Overview

Python.org provides the official Python distribution. Instead of conda environments, Python includes a built‑in tool called **venv** that lets you create isolated environments for different projects.

In this guide you will:

1. Download the Python installer using PowerShell
2. Install Python on your system
3. Verify that Python works
4. Create a Python virtual environment
5. Activate and test the environment

---

# Prerequisites

Before starting, make sure:

* You are using Windows
* PowerShell is available
* You have an internet connection
* You have permission to install software

---

# Step 1: Open PowerShell

1. Press **Windows Key**
2. Type **PowerShell**
3. Click **Windows PowerShell**

A terminal window will open.

---

# Step 2: Download the Python 3.12.3 Installer

Run the following command in PowerShell:

```powershell
Invoke-WebRequest https://www.python.org/ftp/python/3.12.3/python-3.12.3-amd64.exe -OutFile "$env:USERPROFILE\Downloads\python3123.exe"
```

This command downloads the Python 3.12.3 installer and saves it in your **Downloads** folder.

---

# Step 3: Run the Installer

Navigate to the Downloads folder and run the installer:

```powershell
cd $env:USERPROFILE\Downloads
.\python3123.exe
```

The Python installation window will open.

Important:

Make sure you enable:

**Add Python to PATH**

Then follow these steps:

1. Click **Install Now**
2. Wait for installation to complete
3. Click **Close**

---

# Step 4: Verify the Installation

Close PowerShell and open a new PowerShell window.

Run:

```powershell
python --version
```

Expected output:

```
Python 3.12.3
```

Also check pip:

```powershell
pip --version
```

---

# Step 5: Create a Virtual Environment

Create a new environment for your project:

```powershell
python -m venv py312
```

Explanation:

* `python -m venv` creates a virtual environment
* `py312` is the environment folder name

---

# Step 6: Activate the Environment

Activate the environment using:

```powershell
.\py312\Scripts\Activate
```

If successful, your terminal will look like this:

```
(py312) PS C:\Users\YourName>
```

---

# Step 7: Upgrade pip

It is recommended to upgrade pip after creating the environment:

```powershell
python -m pip install --upgrade pip
```

---

# Step 8: Install Packages

You can now install packages inside the environment.

Example:

```powershell
pip install flask pandas numpy scikit-learn
```

These packages will only exist inside this virtual environment.

---

# Step 9: Verify Python Version Inside Environment

Run:

```powershell
python --version
```

Output:

```
Python 3.12.3
```

---

# Step 10: Deactivate the Environment

When you finish working, deactivate the environment:

```powershell
deactivate
```

---

# Why Virtual Environments Are Important

Virtual environments allow you to:

* Use different package versions for different projects
* Avoid dependency conflicts
* Keep your main Python installation clean
* Reproduce project environments easily

---

# Troubleshooting

## Python Not Recognized

If you see an error that python is not recognized:

* Reinstall Python
* Ensure **Add Python to PATH** was checked
* Restart PowerShell

---

## Execution Policy Error When Activating

If activation fails due to security policy, run:

```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```

Then activate the environment again.

---

# Conclusion

You have successfully:

* Downloaded Python 3.12.3 from python.org
* Installed Python on Windows
* Created a virtual environment
* Activated and tested the environment

You are now ready to build Python applications using isolated environments.
