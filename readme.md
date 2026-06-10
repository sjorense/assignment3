# Assignment 3, Interactive Calculator Command-Line Application

A Python command-line calculator that uses a Read-Eval-Print Loop (REPL) to
perform basic arithmetic operations. The application validates user input,
handles errors gracefully, and includes a comprehensive pytest test suite with
100% code coverage.

## Features

- Continuous REPL interface
- Addition, subtraction, multiplication, and division
- Support for integers, decimals, and negative numbers
- Clear instructions and result messages
- Input format and numeric value validation
- Helpful messages for unknown operations
- Graceful division-by-zero error handling
- Unit and integration tests using pytest
- Parameterized operation tests
- 100% statement and branch test coverage

## Project Structure

```text
assignment3/
├── app/
│   ├── calculator/
│   │   └── __init__.py       # Calculator REPL and input handling
│   ├── operations/
│   │   └── __init__.py       # Arithmetic operations
│   └── __init__.py
├── tests/
│   ├── test_calculator.py    # REPL behavior and error-handling tests
│   └── test_operations.py    # Parameterized arithmetic unit tests
├── .coveragerc               # Coverage configuration
├── main.py                   # Application entry point
├── pytest.ini                # Pytest configuration
├── requirements.txt          # Python dependencies
└── README.md
```

## Requirements

- Python 3.12 or later
- pip

## Installation

Clone the repository and move into the project directory:

```bash
git clone <repository-url>
cd assignment3
```

Create and activate a virtual environment:

```bash
python3 -m venv venv
source venv/bin/activate
```

On Windows, activate the environment with:

```powershell
venv\Scripts\activate
```

Install the project dependencies:

```bash
python -m pip install -r requirements.txt
```

## Usage

Start the calculator:

```bash
python main.py
```

Enter commands using this format:

```text
<operation> <number1> <number2>
```

Supported operations are:

| Operation | Example | Result |
| --- | --- | --- |
| `add` | `add 2 3` | `5.0` |
| `subtract` | `subtract 10 4` | `6.0` |
| `multiply` | `multiply 2.5 4` | `10.0` |
| `divide` | `divide 10 2` | `5.0` |

Type `exit` to close the calculator.

### Example Session

```text
Welcome to the calculator REPL! Type 'exit' to quit
Enter an operation (add, subtract, multiply, divide) and two numbers, or 'exit' to quit: add 5 3
Result: 8.0
Enter an operation (add, subtract, multiply, divide) and two numbers, or 'exit' to quit: divide 10 0
Division by zero is not allowed.
Enter an operation (add, subtract, multiply, divide) and two numbers, or 'exit' to quit: exit
Exiting calculator...
```

## Input Validation and Error Handling

The calculator expects exactly one supported operation followed by two valid
numbers. Invalid commands produce a helpful message, and the REPL continues
running so the user can try again.

Examples of handled errors include:

- Incorrect input format, such as `add 5`
- Nonnumeric values, such as `add five three`
- Unknown operations, such as `modulus 5 3`
- Division by zero, such as `divide 5 0`

## Testing

Run the complete test suite:

```bash
pytest
```

The tests include:

- Parameterized unit tests for every arithmetic operation
- Positive, negative, decimal, and zero-value scenarios
- Division-by-zero tests
- REPL tests for valid commands, invalid input, and unknown operations

To ensure 100% coverage:

```bash
pytest --cov=app --cov-report=term-missing --cov-fail-under=100
```

The current test suite contains 30 tests and achieves 100% statement and branch
coverage for the `app` package.

## Continuous Integration

The GitHub Actions workflow in `.github/workflows/tests.yml` runs the pytest
suite on pushes and pull requests to the `main` branch. The workflow fails when
coverage falls below 100%.

## License

This project is licensed under the terms provided in the `LICENSE` file.
