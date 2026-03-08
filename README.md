# Installing Anaconda and Creating a Python 3.12 Environment (Windows – PowerShell Guide)

This guide explains how to install **Anaconda** on a Windows system using **PowerShell** and then create a **Python 3.12 environment**. It is written in a beginner-friendly way so you can follow along even if you have never installed Python before.

---

## Overview

Anaconda is a popular Python distribution used for data science, machine learning, and general Python development. It includes the **conda** package manager, which allows you to create isolated environments with different Python versions.

In this guide you will:

1. Download the Anaconda installer using PowerShell
2. Install Anaconda on your system
3. Verify that Anaconda works
4. Create a Python 3.12 environment
5. Activate and test the environment

---

## Prerequisites

Before starting, make sure:

* You are using **Windows**
* You have **PowerShell** available
* You have an **internet connection**
* You have permission to install software on your computer

---

# Step 1: Open PowerShell

1. Press **Windows Key**
2. Type **PowerShell**
3. Click **Windows PowerShell**

You should see a terminal window open.

---

# Step 2: Download the Anaconda Installer

In PowerShell, run the following command:

```
Invoke-WebRequest https://repo.anaconda.com/archive/Anaconda3-2024.10-1-Windows-x86_64.exe -OutFile "$env:USERPROFILE\Downloads\Anaconda.exe"
```

What this command does:

* Downloads the latest **Anaconda installer**
* Saves it as **Anaconda.exe** in your current folder

The download may take a few minutes because the installer is large (around 600MB–1GB).

---

# Step 3: Run the Installer

After the download finishes, run:

```
.\Anaconda.exe
```

This will launch the installer.

Follow the installer steps:

1. Click **Next**
2. Click **I Agree**
3. Choose **Just Me (Recommended)**
4. Select the installation location (default is fine)
5. Click **Install**

Installation may take a few minutes.

---

# Step 4: Verify the Installation

After installation completes:

1. Open the **Start Menu**
2. Search for **Anaconda Prompt**
3. Open it

Now type:

```
conda --version
```

If everything worked correctly, you should see something like:

```
conda 23.x.x
```

This means Anaconda is installed correctly.

---

# Step 5: Create a Python 3.12 Environment

Now we will create a new environment with Python 3.12.0

Run the following command:

```
conda create -n py312 python=3.12.0
```

Explanation:

* **conda create** → creates a new environment
* **-n py312** → names the environment "py312"
* **python=3.12** → installs Python version 3.12

You will see a list of packages that will be installed.

Type:

```
y
```

and press **Enter**.

---

# Step 6: Activate the Environment

Once installation finishes, activate the environment:

```
conda activate py312
```

If successful, your terminal will change to something like:

```
(py312) C:\Users\YourName>
```

This means the environment is active.

---

# Step 7: Check the Python Version

Now verify the Python version:

```
python --version
```

Expected output:

```
Python 3.12.x
```

This confirms that Python 3.12 is running inside your environment.

---

# Step 8: Deactivate the Environment (Optional)

If you want to leave the environment, run:

```
conda deactivate
```

This returns you to the base environment.

---

# Why Use Anaconda Environments?

Using environments has several advantages:

* Different projects can use different Python versions
* Package conflicts are avoided
* Your system Python installation remains unchanged
* Easy to manage dependencies


---

# Troubleshooting

## Command not found: conda

If you see:

```
conda : The term 'conda' is not recognized
```

Try:

* Restarting your computer
* Opening **Anaconda Prompt** instead of PowerShell

---

## Slow Download

The Anaconda installer is large. If the download is slow, consider installing **Miniconda** instead, which is a smaller version of Anaconda.

---

# Conclusion

You have successfully:

* Downloaded Anaconda using PowerShell
* Installed Anaconda on Windows
* Created a Python 3.12 environment
* Activated and verified the installation

You are now ready to start developing Python applications using Anaconda.

---
