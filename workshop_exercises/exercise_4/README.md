# Exercise 4: Setting Up a Conda Environment with `environment.yml`

## Objective

Learn how to create a Conda environment using `environment.yml`, manually set up a Conda environment with a specific Python version, and understand the difference between `pip install` and `conda install`.

## Prerequisites

* Install [Conda](https://www.anaconda.com/docs/getting-started/miniconda/install#quickstart-install-instructions)

## Instructions

### 1️⃣ Manually Create a Conda Environment

1. Create a Conda environment with a specific Python version:

   ```bash
   conda create --name manual_env python=3.10
   ```

2. Activate the environment:

   ```bash
   conda activate manual_env
   ```

3. Install dependencies manually:

   ```bash
   conda install numpy pandas
   ```

4. Check installed packages:

   ```bash
   conda list
   ```

5. Deactivate the environment:

   ```bash
   conda deactivate
   ```

6. Remove the manually created environment:

   ```bash
   conda remove --name manual_env --all
   ```

### 2️⃣ Create an Environment Using `environment.yml`

1. Create an `environment.yml` file:

   ```yaml
   name: my_project_env
   dependencies:
     - python=3.10    # Or whatever version you have
     - numpy
     - pandas
   ```

2. Set up the environment:

   ```bash
   conda env create -f environment.yml
   ```

3. Activate the environment:

   ```bash
   conda activate my_project_env
   ```

4. Verify installation:

   ```bash
   conda list
   ```

   * If `pandas` appears in the output, your environment is correctly set up.

### 3️⃣ Understanding `pip install` vs `conda install`

Unlinke most tools, conda doesn't use pip under the hood, which means that using conda can create discrepancies between pip and conda. Sometimes, interactions between these will end up causing you trouble, so keep in mind which tool you're using.

1. Inside the activated Conda environment, try installing a package using `pip`:

   ```bash
   pip install scipy
   ```

2. Check where the package was installed:

   ```bash
   conda list
   ```

   * This will show that `scipy` was installed via `pip` rather than Conda.
3. Now, install `scipy` using Conda:

   ```bash
   conda install scipy
   ```

4. Check again:

   ```bash
   conda list
   ```

   * Now, `scipy` appears as a Conda-installed package.

### 4️⃣ Deactivate and Remove the Environment

1. Deactivate the environment:

   ```bash
   conda deactivate
   ```

2. Remove the environment:

   ```bash
   conda remove --name my_project_env --all
   ```

## Summary

* Manually creating a Conda environment allows for step-by-step installation.
* `environment.yml` automates environment creation for reproducibility.
* `pip install` installs packages from PyPI, while `conda install` uses the Conda package manager, ensuring compatibility with system dependencies.
* Removing an environment cleans up dependencies effectively.
