# Razen Programming Language beta v0.1.75 - Library Call Update & Namespace Notation

## Overview
Razen is a modern, intuitive programming language designed for clarity, performance, and ease of use. With a clean syntax inspired by Python and strong type safety, Razen offers an excellent balance between development speed and runtime performance.

Developed by Prathmesh Barot, Basai Corporation.

## Features
- **Intuitive Syntax**: Python-like syntax that's easy to read and write.
- **Fast Performance**: Built for efficiency with optimized runtime execution.
- **Built-in Debugging**: Comprehensive debugging tools including step-by-step execution.
- **Type Safety**: Strong type checking for variables with specialized declaration tokens.
- **Rich Library System**: Extensive library system with bracket notation for function calls.
- **Expressive Conditionals**: Clean if/else syntax with support for nested conditions.
- **Interactive Mode**: Built-in REPL for testing code snippets.
- **Lightweight**: Small footprint with minimal dependencies.
- **Cross-platform support**: Works on Linux, macOS, and Windows.
- **OOP Support**: Class-based object-oriented programming capabilities.
- **Colored Output**: Built-in support for colored terminal output.
- **Robust Error Handling**: Comprehensive error handling with try/catch blocks.
- **Filesystem Library**: Comprehensive filesystem operations for file and directory management.

## Changelog

Razen is under active development with regular updates. The latest version is **beta v0.1.75** which brings a major update to the library call system and namespace support.

### Latest Release: beta v0.1.75 – Library Call Update & Namespace Notation

This release introduces powerful new ways to call library functions and modernizes the Razen library experience. View the full changelog:

- [Markdown Version (beta_v0.1.75.md)](changelogs/beta_v0.1.75.md)

#### Key Improvements in v0.1.75

- **Namespace Notation (`lib::function`)**: Call library functions with the modern `namespace::function(args...)` syntax, in addition to the classic `Library[function](args...)` bracket notation.
- **Full Parity**: Both notations are fully supported and interchangeable for all libraries.
- **Improved Parser & Compiler**: Robust handling of all library call forms, including nested and chained calls.
- **Better Error Messages**: Parser errors now include precise line and column info.
- **Consistent Metadata Extraction**: Docs, examples, and changelogs auto-update with function difficulty and version badges.
- **Backward Compatibility**: All previous scripts using bracket notation continue to work without changes.

For a complete history of all version changelogs, please visit the [changelogs.mdx](changelogs/changelogs.mdx) file or browse the [changelogs](changelogs/) directory for individual version details.

## Installation

### Universal Installer (All Platforms)

Razen now provides a single universal installer that works across all major platforms:

```bash
# Using curl (Linux/macOS/Windows with Git Bash)
curl -o installer.sh "https://raw.githubusercontent.com/BasaiCorp/razen-lang/main/installer.sh" && chmod +x installer.sh && ./installer.sh
```

```bash
# Using wget (Linux)
wget -O installer.sh "https://raw.githubusercontent.com/BasaiCorp/razen-lang/main/installer.sh" && chmod +x installer.sh && ./installer.sh
```

### Windows Installation

For Windows users:
```bash
# Using Git Bash
curl -o installer.sh "https://raw.githubusercontent.com/BasaiCorp/razen-lang/main/installer.sh" && chmod +x installer.sh && ./installer.sh
```

> **Note**: Windows installation requires Git Bash, which you can download from [https://git-scm.com/downloads](https://git-scm.com/downloads)

#### Windows Installation Notes

Windows installation has been significantly improved in recent versions with better toolchain detection and automatic dependency installation. For detailed information about Windows-specific improvements, please refer to the changelogs.

#### Windows Troubleshooting

If you encounter installation issues:

**Build Tool Requirements:**
- **MSVC Toolchain**: Requires Visual Studio Build Tools or Visual Studio
- **GNU Toolchain**: Requires MinGW-w64 (automatically installed when possible)

**Step-by-Step Solutions:**

1. **For MSVC Toolchain Issues**:
   ```bash
   # Install Visual Studio Build Tools
   # Download from: https://visualstudio.microsoft.com/visual-cpp-build-tools/
   # Select "C++ build tools" workload during installation

   # Verify installation
   rustup default stable-x86_64-pc-windows-msvc
   rustc --version
   ```

2. **For GNU Toolchain Issues**:
   ```bash
   # The installer attempts automatic installation, but if it fails:

   # Via MSYS2 (recommended)
   pacman -S mingw-w64-x86_64-gcc mingw-w64-x86_64-toolchain

   # Via Chocolatey
   choco install mingw -y

   # Verify installation
   rustup default stable-x86_64-pc-windows-gnu
   rustc --version
   ```

3. **Manual Toolchain Management**:
   ```bash
   # Check available toolchains
   rustup toolchain list

   # Install specific toolchain
   rustup toolchain install stable-x86_64-pc-windows-gnu
   rustup toolchain install stable-x86_64-pc-windows-msvc

   # Switch between toolchains
   rustup default stable-x86_64-pc-windows-msvc  # For Visual Studio users
   rustup default stable-x86_64-pc-windows-gnu   # For MinGW-w64 users
   ```

4. **Common Error Solutions**:
   - **"link.exe failed"**: Install Visual Studio Build Tools or switch to GNU toolchain
   - **"gcc not found"**: Install MinGW-w64 or switch to MSVC toolchain
   - **Permission errors**: Run Git Bash as Administrator
   - **PATH issues**: Restart terminal after installing build tools
   - **Compilation failures**: Run installer again - it will automatically retry with different toolchain

**Environment Requirements:**
- Git Bash (from Git for Windows)
- Administrator privileges (recommended)
- Internet connection for downloading dependencies
- At least 2GB free disk space

### Installation Options

The installer provides additional options:

```bash
./installer.sh           # Standard installation/update
./installer.sh force     # Force a fresh installation
./installer.sh uninstall # Remove Razen from your system
```

This will download and install Razen globally on your system, making the `razen` command available from anywhere.

### Keeping Razen Updated

To update Razen to the latest version:
```bash
razen-update
```

This will automatically check for updates and install the newest version if available.

### Uninstalling Razen

To uninstall Razen:
```bash
./installer.sh uninstall
```

or

```bash
razen uninstall
```

## Usage

### Command Reference

```bash
# Core Commands
razen <filename.rzn>       # Run a Razen script
razen new <filename>       # Create a new Razen program
razen version              # Display version information
razen help                 # Show help information

# Specialized Tools
razen-debug <filename.rzn> # Debug mode with detailed output
razen-test <filename.rzn>  # Test mode for testing scripts
razen-run <filename.rzn>   # Clean mode (only shows program output)
razen-update               # Update to the latest version
razen-help                 # Display detailed help with formatting
```

### Running Scripts

```bash
razen path/to/script.rzn       # Standard execution
razen-debug path/to/script.rzn # Debug mode with detailed output
razen-test path/to/script.rzn  # Test mode for testing scripts
razen-run path/to/script.rzn   # Clean mode (only shows program output)
```

### Creating Your First Razen Program

You can create a new Razen program with a template:
```bash
razen new hello
```

This creates a new file `hello.rzn` with a Hello World template:
```razen
# New Razen program created on [current date]
# Powered by Razen Language

# Your code goes here
take message = "Hello, World!";
show message;

# Read user input
read user_input = "What's your name? ";
show "Nice to meet you, " + user_input + "!";
```

Run it with:
```bash
razen-run hello.rzn
```

## Example Code

### Basic Razen Program

```razen
# Hello World program in Razen
show "Hello, World!";

# Variables with type enforcement
let num = 42;  # Numeric variable
take name = "Alice";  # String variable
hold is_active = true;  # Boolean variable
put anything = "This can be any type";  # Any type variable

# Mathematical operations with specialized tokens
sum total = 100 + 50;  # Sum calculation
diff result = 100 - 50;  # Difference calculation
prod product = 5 * 10;  # Product calculation
div quotient = 20 / 4;  # Division calculation
mod remainder = 10 % 3;  # Modulus calculation

take message = "Hello, " + name + "!";
show message;

# Conditional statements
if (num > 40) {
    show "Number is greater than 40";
} else if (num == 40) {
    show "Number is exactly 40";
} else {
    show "Number is less than 40";
}

# Loops
let i = 0;
while (i < 5) {
    show "Loop iteration: " + i;
    i = i + 1;
}

# Using library functions
show "Current time: " + TimeLib[now]();
show "Random number: " + Random[int](1, 100);

# Colored output
show(red) "This is a red error message";
show(green) "This is a green success message";
show(yellow) "This is a yellow warning message";
show(blue) "This is a blue information message";
show(purple) "This is a purple highlight message";
show(cyan) "This is a cyan technical message";
```

### Function Definition and Usage

```razen
# Define a simple function to calculate factorial
fun factorial(n) {
    if (n <= 1) {
        return 1;
    }
    return n * factorial(n - 1);
}

# Use the function
let num = 5;
show "Factorial of " + num + " is " + factorial(num);

# Function with multiple parameters
fun greet(name, age) {
    show "Hello, " + name + "! You are " + age + " years old.";
}

greet("Alice", 30);
```

### Library System with Bracket Notation

```razen
# Import libraries
lib arrlib;   # Array library
lib strlib;   # String library
lib mathlib;  # Math library
lib random;   # Random library
lib crypto;   # Crypto library for encryption and hashing

# Using library functions with bracket notation
show "Array operations:";
show "Original array: " + [1, 2, 3];
show "After push: " + ArrLib[push]([1, 2, 3], 4);
show "Join with dash: " + ArrLib[join](["a", "b", "c"], "-");

# String operations
show "String operations:";
show "Uppercase: " + StrLib[upper]("Hello, Razen!");
show "Replace: " + StrLib[replace]("Hello, Razen!", "Razen", "World");

# Math operations
show "Math operations:";
show "Square root: " + MathLib[sqrt](16);
show "Power: " + MathLib[power](2, 3);

# Random operations
show "Random operations:";
show "Random integer (1-10): " + Random[int](1, 10);
show "Random choice: " + Random[choice](["apple", "banana", "cherry"]);

# Crypto operations
show "Crypto operations:";
show "Hash of 'Hello, Razen!': " + Crypto[hash]("Hello, Razen!");
```

Check the `examples` folder for more sample programs and tutorials.

## Command Details

### razen-update
A dedicated command to check for and install updates from the main repository. It shows the current version and latest available version, then performs the update if a newer version is available.

### razen-help
A colorful, well-formatted help command that displays comprehensive information about all available Razen commands, tools, and usage examples.

### razen new
Creates a new Razen program with a template to help you get started quickly. Automatically adds the `.rzn` extension if not provided.

### razen-debug
Runs a Razen program in debug mode with detailed output, showing each step of execution.

```bash
razen-debug my-program.rzn
```

### razen-test
Runs a Razen program in test mode, useful for testing scripts and validating functionality.

```bash
razen-test my-program.rzn
```

## File Locations

### Linux/macOS
- **Core files**: `/usr/local/lib/razen`
- **Examples**: `/usr/local/lib/razen/examples`
- **Scripts**: `/usr/local/lib/razen/scripts`
- **Library Files**: `/usr/local/lib/razen/properties/libs`

### Windows
- **Core files**: `C:\Program Files\Razen`
- **Examples**: `C:\Program Files\Razen\examples`
- **Scripts**: `C:\Program Files\Razen\scripts`
- **Executables**: `C:\Program Files\Razen\bin`

## Variable Types

Razen supports different variable types with type enforcement:

- **let**: For numeric values (integers and floats)
  ```razen
  let count = 42;
  let price = 9.99;
  ```

- **take**: For string values
  ```razen
  take name = "John";
  take message = "Hello, World!";
  ```

- **hold**: For boolean values
  ```razen
  hold is_active = true;
  hold has_permission = false;
  ```

- **put**: For any type (no type restrictions)
  ```razen
  put anything = 42;
  put anything = "Now I'm a string";
  put anything = true;
  ```

### Mathematical Variables

- **sum**, **diff**, **prod**, **div**, **mod**: For numeric operations
  ```razen
  sum total = 100 + 50;  # Sum calculation
  diff result = 100 - 50;  # Difference calculation
  prod product = 5 * 10;  # Product calculation
  div quotient = 20 / 4;  # Division calculation
  mod remainder = 10 % 3;  # Modulus calculation
  ```

### Collection Variables

- **list**, **arr**, **append**, **remove**: For array operations
  ```razen
  list dynamicList = [1, 2, 3, 4, 5];  # Dynamic array
  arr fixedArray = [10, 20, 30];  # Fixed-size array
  append newList = [1, 2, 3, 4, 5, 6];  # Array with appended element
  remove shorterList = [2, 3, 4, 5];  # Array after removal
  ```

### Dictionary/Map Variables

- **map**, **key**, **value**: For dictionary operations
  ```razen
  map userInfo = ["name", "John", "age", 30];  # Key-value storage using arrays
  key userKeys = ["name", "age"];  # Dictionary keys
  value userValues = ["John", 30];  # Dictionary values
  ```

### User-Defined Variables

- **store**, **box**, **ref**: For special variable operations
  ```razen
  store savedData = "This will be saved";  # Persistent storage
  box tempData = "Temporary data";  # Temporary storage
  ref nameRef = message;  # Reference to another variable
  ```

## Object-Oriented Programming

Razen supports class-based object-oriented programming with a clean and intuitive syntax.

### Class Declaration

```razen
class Person {
    # Constructor (implicitly called when creating new instances)
    fun init(name, age) {
        this[name] = name;
        this[age] = age;
    }

    # Method to display information
    fun display() {
        show "Name: " + this[name] + ", Age: " + this[age];
    }

    # Method to have a birthday
    fun haveBirthday() {
        this[age] = this[age] + 1;
        show this[name] + " is now " + this[age] + " years old!";
    }
}

# Create a new Person instance
put person = new Person("John", 30);

# Call methods
person:display();
person:haveBirthday();
```

### Inheritance

Razen supports class inheritance using the `extends` keyword:

```razen
class Employee extends Person {
    fun init(name, age, position) {
        super[init](name, age);
        this[position] = position;
    }

    fun display() {
        super[display]();
        show "Position: " + this[position];
    }
}
```

See the examples directory for complete object-oriented programming examples.

## License
Razen is licensed under a custom license. See the [LICENSE](./LICENSE) file for details.

Key points:
- You can use Razen for personal and commercial projects
- You can create libraries and applications using Razen
- You cannot modify, rebrand, or redistribute the core language
- You must include attribution: "Powered by Razen - © 2025 Prathmesh Barot"

## Attribution
When using Razen in your projects, please include the following attribution:

```
Powered by Razen - © 2025 Prathmesh Barot, Basai Corporation
```

## Contact
For questions, support, or feedback about Razen, please contact:
- Email: prathmeshbarot2009@gmail.com
- GitHub: [https://github.com/BasaiCorp/razen-lang](https://github.com/BasaiCorp/razen-lang)

**Official website coming soon!**
