# Password Generator

A small, simple password generator implemented in Python (Jupyter notebook). The repository contains a single notebook that demonstrates a basic function to create short, mixed-character passwords using lowercase, uppercase, numeric, and special characters.

## Files

- `password_generator.ipynb` — Jupyter notebook with the password generator implementation and a short demo that prints a generated password.

## Description

The generator builds a password by selecting characters from four categories:
- Lowercase letters
- Uppercase letters
- Digits
- Special characters

The current implementation constructs an 8-character password by choosing two characters from each category. It is intended as a simple example and teaching resource, not a production-ready password manager.

## Usage

Open `password_generator.ipynb` in Jupyter Notebook, JupyterLab, or Google Colab and run the cells. The notebook includes a `passwordGenerator()` function; running the demo cell prints a generated password.

If you prefer to run the generator as a short Python script, extract the function from the notebook and run it like this:

```python
import random

def passwordGenerator():
    lowerchars = list("abcdefghijklmnopqrstuvwxyz")
    upperchars = list("ABCDEFGHIJKLMNOPQRSTUVWXYZ")
    specialchars = list("!@#$%^&*()-_+=[]{}|\\;:\u003c\u003e,./?")
    numerichars = list("0123456789")

    # Build a simple 8-character password with 2 chars from each set
    password = (
        random.choice(lowerchars) + random.choice(upperchars) +
        random.choice(specialchars) + random.choice(numerichars) +
        random.choice(lowerchars) + random.choice(upperchars) +
        random.choice(specialchars) + random.choice(numerichars)
    )
    return password

if __name__ == "__main__":
    print(passwordGenerator())
```

## Notes & Improvements

- This implementation always includes exactly two characters from each category and returns an 8-character password. Consider:
  - Allowing configurable password length
  - Randomizing the order of chosen characters so the categories are not grouped
  - Ensuring stronger entropy for production use (use the `secrets` module instead of `random` for cryptographic security)
  - Adding tests and input validation

## Contributing

Contributions are welcome. Feel free to open issues or submit pull requests with improvements or feature requests.

## Author

sachindra-arch

## License

No license file is included in this repository. Add a LICENSE file if you want to make the project open source under a specific license.
