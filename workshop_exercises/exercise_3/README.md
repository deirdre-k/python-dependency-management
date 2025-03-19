# Exercise 3: Pyproject.toml, Editable Mode, and Optional Dependencies

## Objective

Learn how to install a project using `pyproject.toml`, use editable mode, and install optional dependencies.

## Instructions

### 1️⃣ Install the Project in Static Mode

   Files like `requirements.txt` allow you to install dependencies for your project, but don't allow you to install your project as a Python package. `pyproject.toml` or `setup.py` (outdated) files do allow you to install your code as a package in your Python `site-packages`, so that it can be used by other projects. Let's try installing our own package.

1. Navigate to the `my_project` directory:

   ```bash
   cd my_project
   ```

2. Create and activate a virtual environment (see exercise 1)

3. Install the project using `pyproject.toml`:

   ```bash
   pip install .
   ```

4. Verify the installation:

   ```bash
   pip list
   ```

5. Run the script:

   ```bash
   python main.py
   ```

6. Modify `my_module.py` by changing the return value of the `greet()` function:

   ```python
   def greet():
       return "Hello, Python!"
   ```

   Save the file and rerun `main.py`. Notice that the change **does not take effect**.

### 2️⃣ Understanding How Static Installation Works

1. Check where the package was installed:

   ```bash
   pip show my_project
   ```

   - This will show the location inside `site-packages`, meaning your package **was copied** there during installation.
2. This means that every time you make changes, you would need to **uninstall and reinstall**:

   ```bash
   pip uninstall my_project -y
   pip install .
   ```

   - This is **not efficient** for active development.

### 3️⃣ Install the Project in Editable Mode

1. Uninstall the current installation:

   ```bash
   pip uninstall my_project -y
   ```

2. Reinstall in **editable mode**:

   ```bash
   pip install -e .
   ```

3. Check the installation path again:

   ```bash
   pip show my_project
   ```

   - You should see that the location now points to **your local directory** instead of `site-packages`.
4. Run `main.py` again, make a change to `my_module.py`, and rerun it. **Now the change takes effect immediately**!

### 4️⃣ Install Optional Dependencies

If you look in the pyproject.toml, you'll see:

   ```toml
   optional-dependencies = { 
      test = ["pytest"],
      dev = ["black"]
   }
   ```

   This is an example of optional dependencies. These dependencies are useful for specific cases, such as testing and development, but are **not required** for the main package. In this case, 'pytest' is needed only for running tests, and 'black' is needed only for code formatting during development. Let's try them out!

1. Try running pytest from the `sample_project` directory:

   ```bash
   pytest
   ```

   This should fail to run, as you don't have pytest installed yet.

2. Install the `test` dependencies:

   ```bash
   pip install .[test]
   ```

3. Install the `dev` dependencies:

   ```bash
   pip install .[dev]
   ```

4. Verify they are installed:

   ```bash
   pip list
   ```

5. Try running pytest again:

   ```bash
   pytest
   ```

   You should now be able to run the tests!

## Summary

- Static installation **copies** the package into `site-packages`.
- Editable mode **symlinks** the package, allowing live updates.
- Optional dependencies can be installed for special cases, such as testing and development.
