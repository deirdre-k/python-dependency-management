# Exercise 2: Managing Dependencies with `requirements.txt`

## Objective

Learn how to use a `requirements.txt` file to install dependencies.

## Instructions

### Using a `requirements.txt`

1. Navigate to the `sample_project` directory.

   ```bash
   cd sample_project
   ```

2. Create and activate a virtual environment:

   ```bash
   python -m venv venv

   source venv/bin/activate  # Mac/Linux
   # OR
   venv\Scripts\activate  # Windows
   ```

3. Check installed packages:

   ```bash
   pip list
   ```

4. Install dependencies from `requirements.txt`:

   ```bash
   pip install -r requirements.txt
   ```

5. Check installed packages again:

   ```bash
   pip list
   ```

6. Try installing dependencies:

   ```bash
   pip install -r requirements.txt
   ```

   * You can see that the second time running this, packages are already installed so this step goes much more quickly. 

7. Run the script:

   ```bash
   python main.py
   ```
  
    If the script runs successfully, you have correctly set up your environment!

8. Deactivate:

   ```bash
   deactivate
   ```

9. Run the script again:

   ```bash
   python main.py
   ```

    The script should no longer run, as your base Python version shouldn't have the required libraries installed.
    
    If it does run, you may have these libraries installed by coincidence. Try running `pip list` to see what's installed.

### Creating a `requirements.txt`

1. Reactivate your virtual environment

   ```bash
   source venv/bin/activate  # Mac/Linux
   # OR
   venv\Scripts\activate  # Windows
   ```

2. Delete your `requirements.txt` file

3. Generate a new `requirements.txt` from the packages installed in your environment:

   ```bash
   pip freeze > requirements.txt
   ```

   You now have a recreated `requirements.txt`. Check it out to see how it looks!