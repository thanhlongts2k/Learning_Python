# How to build py script to exe

## Step 1: Install cx_Freeze

- Make sure you have `cx_Freeze` installed. You can install it using pip

```
pip install cx_Freeze
```

## Step 2: Create a setup script

- Create a setup script (e.g., `setup.py`) in the same directory as Python script.
- This script will provide the configuration for `cx_Freeze`.

```python
from cx_Freeze import setup, Executable

setup(
    name="YourAppName",
    version="1.0",
    description="Your application description",
    executables=[Executable("your_script.py")],
    )
```
- Replace `YourAppName` and `Your application description` with your application’s name and description and `your_script.py` with the name of your Python script.

## Step 3: Run the setup script

- Open a terminal, navigate to the directory containing your Python script and the `setup.py` file, and run:
```
python setup.py build
```
- This will create a `build` directory containing the executable file.

## Step 4: Locate the executable

- After running the `build` command, you can find the executable in the `build` directory. It will be inside a subdirectory with the name of your operating system (e.g., `build\exe.win-amd64-3.8` for a Windows 64-bit executable).

- Now, you should have a standalone executable file that you can distribute and run on a machine without Python installed. Remember that if your script has external dependencies, you may need to include them explicitly in the `setup.py` script.

- Refer to the `cx_Freeze` documentation for more advanced configuration options
