# Exercise 1: Setting Up a Virtual Environment

## Objective

Learn how to create and use a virtual environment in Python.

## Instructions

1. First, let's check our current Python version:

   ```bash
   python --version
   ```

2. Let's also find the location of our current Python:

   ```bash
   python -m site
   ```

3. Let's see what packages we have available:

   ```bash
   pip list
   ```

4. Next, let's try to install something:

   ```bash
   pip install requests
   ```

   You should see the **`error:externally-managed-environment`**. By default, Python prevents you from installing packages at the global level unless you *really* mean to. If it did succeed, don't worry; you can uninstall by running `pip uninstall requests`.

5. Create a virtual environment named `my_env`.

   ```bash
   python -m venv my_env
   ```

6. Activate the virtual environment:

   ```bash
   source my_env/bin/activate  # Mac/Linux
   # OR
   my_env\Scripts\activate  # Windows

7. Check the Python location again to confirm it's using the python version inside the venv:

   ```bash
   python -m site
   ```

8. Check the packages available inside the environment:

   ```bash
   pip list
   ```

9. Install `requests` inside the environment:

   ```bash
   pip install requests
   ```

10. Verify the installed packages:

   ```bash
   pip list
   ```

11. Deactivate the environment:

   ```bash
   deactivate
   ```

12. Check installed packages outside the venv:

   ```bash
   pip list
   ```

13. Reactivate the virtual environment and verify packages are still there:

   ```bash
   source my_env/bin/activate  # Mac/Linux
   # OR
   my_env\Scripts\activate  # Windows
   
   pip list
   ```

14. Deactivate, locate your virtual environment folder (commonly `venv` or `.venv`), and delete it:

   ```bash
   deactivate

   rm -rf venv  # Mac/Linux
   # OR
   rmdir /s /q venv  # Windows
   ```

15. Verify it has been removed by attempting to activate it:

   ```bash
   source venv/bin/activate  # Should fail
   ```
