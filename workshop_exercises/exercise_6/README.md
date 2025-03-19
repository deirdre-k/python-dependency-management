# Exercise: Using requirements.in

## Objective

Learn how to use `requirements.in` to manage dependencies, pin versions, and generate a `requirements.txt` file for reproducible installations.

## Instructions

### 1️⃣ Install Dependencies from requirements.in

1. Navigate to the `sample_project` directory:

   ```bash
   cd sample_project
   ```

2. Create and activate a virtual environment (see exercise 1).

3. Install `pip-tools` if you haven't already:

   ```bash
   pip install pip-tools
   ```

4. Create a `requirements.in` file with some basic dependencies:

   ```bash
   echo "requests\nnumpy" > requirements.in
   ```

5. Compile the `requirements.txt` file from `requirements.in`:

   ```bash
   pip-compile requirements.in
   ```

6. Install the dependencies from the newly created `requirements.txt`:

   ```bash
   pip install -r requirements.txt
   ```

### 2️⃣ Pin a Package Version

1. Open `requirements.in` and modify it to specify a version constraint, for example:

   ```txt
   requests<2.30
   numpy
   ```

2. Recompile `requirements.txt`:

   ```bash
   pip-compile requirements.in
   ```

3. Check that the pinned version of `requests` is reflected in `requirements.txt`.

### 3️⃣ Uninstall and Reinstall Using requirements.txt

1. Uninstall all installed packages:

   ```bash
   pip uninstall -y -r requirements.txt
   ```

2. Reinstall dependencies from `requirements.txt`:

   ```bash
   pip install -r requirements.txt
   ```

3. Verify that the correct versions of packages are installed:

   ```bash
   pip list | grep requests
   ```

## Summary

- `requirements.in` is used to specify high-level dependencies.
- `pip-compile` generates a **fully pinned** `requirements.txt`.
- Pinning versions ensures reproducibility in different environments.
- Reinstalling from `requirements.txt` guarantees a known-good setup.
