# Exercise 4: Using `pyproject.toml` with Poetry

## Objective

Learn how to use Poetry to manage dependencies.

## Instructions

1. Install Poetry:

   ```bash
   pip install poetry
   ```

2. Create a Poetry project:

   ```bash
   poetry init
   ```

3. Install dependencies:

   ```bash
   poetry add requests pytest
   ```

4. Activate the virtual environment:

   ```bash
   poetry shell
   ```

5. Check Your Success

   ```bash
   poetry show pytest
   ```

   - If `pytest` appears with its version, your setup is correct.
