# Installing Python 3.12.0 and Creating a Virtual Environment (Windows – PowerShell Guide)

This guide explains how to install **Python 3.12.0 from python.org** on a Windows system using **PowerShell**, and then create a **virtual environment** for your projects. The guide is written in a beginner‑friendly style so even if you are installing Python for the first time, you can follow it step by step without confusion.

Python is one of the most widely used programming languages for **data science, machine learning, web development, automation, and backend systems**. Installing it correctly and using isolated environments will help you manage your projects more professionally and avoid dependency conflicts.

---

# Overview

The official Python distribution is provided through **python.org**. When you install Python from python.org, it includes the **pip package manager** and built‑in tools that allow you to create isolated environments.

Instead of using tools like Conda, Python provides a built‑in module called **venv (virtual environment)**. A virtual environment creates a separate workspace for each project so that the libraries used in one project do not interfere with another.

In this guide you will learn how to:

1. Download the Python installer using PowerShell
2. Install Python 3.12.0 on your Windows system
3. Verify that Python and pip are working correctly
4. Create an isolated virtual environment
5. Activate and use that environment for your projects

By the end of this tutorial you will have a clean Python setup ready for development.

---

# Prerequisites

Before starting the installation process, make sure the following requirements are satisfied:

* You are using a **Windows operating system**
* **PowerShell** is available on your system
* You have a **stable internet connection** to download the installer
* You have permission to install software on your computer

These are the only requirements needed to complete the setup.

---

# Step 1: Open PowerShell

PowerShell is a command line interface that allows you to run commands and manage your system.

To open PowerShell:

1. Press the **Windows key** on your keyboard
2. Type **PowerShell** in the search bar
3. Click **Windows PowerShell** from the results

A terminal window will open where you can run commands.

---

# Step 2: Download the Python 3.12.0 Installer

Instead of manually downloading Python through the browser, you can download it directly using PowerShell.

Run the following command:

```powershell
Invoke-WebRequest https://www.python.org/ftp/python/3.12.0/python-3.12.0-amd64.exe -OutFile "$env:USERPROFILE\Downloads\python3120.exe"
```

Explanation of the command:

* **Invoke-WebRequest** → downloads a file from the internet
* The URL points to the official **Python 3.12.0 installer**
* The file will be saved as **python3120.exe** inside your **Downloads folder**

The download may take a minute depending on your internet speed.

---

# Step 3: Run the Installer

After the installer has been downloaded, you need to run it.

Navigate to the Downloads folder and execute the installer:

```powershell
cd $env:USERPROFILE\Downloads
.\python3120.exe
```

This will launch the Python installation window.

Important step:

Before clicking install, make sure you enable:

**Add Python to PATH**

This option allows you to run Python commands from any terminal window.

Now follow these steps:

1. Click **Install Now**
2. Wait for the installation process to complete
3. Click **Close** when finished

The installation typically takes less than a minute.

---

# Step 4: Verify the Installation

After installing Python, close the current PowerShell window and open a **new PowerShell window**.

Run the following command:

```powershell
python --version
```

Expected output:

```
Python 3.12.0
```

This confirms that Python has been installed successfully.

Next verify that **pip**, the Python package manager, is available:

```powershell
pip --version
```

Pip allows you to install external libraries such as Flask, NumPy, Pandas, and many others.

---

# Step 5: Create a Virtual Environment

A virtual environment allows you to create a **separate Python workspace for each project**.

This prevents dependency conflicts when different projects require different library versions.

To create a virtual environment run:

```powershell
python -m venv py312
```

Explanation:

* **python -m venv** → runs the virtual environment module
* **py312** → name of the environment folder

A new folder called **py312** will be created in your current directory.

---

# Step 6: Activate the Environment

Before installing packages, you must activate the environment.

Run the following command:

```powershell
.\py312\Scripts\Activate
```

Once activated, your terminal will change and look similar to this:

```
(py312) PS C:\Users\YourName>
```

The `(py312)` prefix indicates that the virtual environment is active.

Any Python packages you install now will be installed **only inside this environment**.

---

# Step 7: Upgrade pip

It is recommended to upgrade pip to the latest version before installing packages.

Run:

```powershell
python -m pip install --upgrade pip
```

Updating pip ensures compatibility with the newest packages.

---

# Step 8: Install Packages

Now you can install packages required for your project.

For example:

```powershell
pip install flask pandas numpy scikit-learn
```

These packages are commonly used for:

* **Flask** → building web applications and APIs
* **Pandas** → data manipulation and analysis
* **NumPy** → numerical computing
* **Scikit‑learn** → machine learning algorithms

Because the virtual environment is active, these packages will only be installed inside the **py312 environment**.

---

# Step 9: Verify Python Version Inside the Environment

You can verify that the environment is using the correct Python version.

Run:

```powershell
python --version
```

Output:

```
Python 3.12.0
```

This confirms that your environment is running Python 3.12.0.

---

# Step 10: Deactivate the Environment

When you finish working on the project, you can deactivate the environment.

Run:

```powershell
deactivate
```

Your terminal will return to the normal system environment.

---

# Why Virtual Environments Are Important

Virtual environments are an essential practice in professional Python development because they:

* Prevent library conflicts between projects
* Keep your system Python installation clean
* Allow reproducible development environments
* Make deployment easier when sharing projects

For example, one project might require **Flask 2.x**, while another project requires **Flask 3.x**. Virtual environments allow both projects to coexist without issues.

---

# Troubleshooting

## Python Not Recognized

If you see an error like:

```
python is not recognized as an internal or external command
```

Possible solutions:

* Reinstall Python and ensure **Add Python to PATH** is selected
* Restart PowerShell

---

## Execution Policy Error When Activating

Sometimes Windows blocks script execution for security reasons.

If activation fails, run:

```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```

Then activate the environment again.

---

# Conclusion

You have successfully completed the Python setup process. In this guide you learned how to:

* Download Python 3.12.0 using PowerShell
* Install Python on Windows
* Verify the Python installation
* Create and activate a virtual environment
* Install packages inside the environment

Your system is now ready for Python development, whether you are building **data science projects, machine learning models, or web applications using frameworks like Flask or FastAPI**.

You can now start building and managing Python projects using isolated and professional development environments.
