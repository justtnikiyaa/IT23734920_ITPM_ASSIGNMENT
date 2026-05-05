# IT3040 – ITPM Assignment 1
## Transliteration Accuracy Testing – Option 1

**Student:** W.M.N Dulavin (IT23734920)  
**Module:** IT3040 – IT Project Management  
**Year:** 3 | Semester 1  
**Institution:** SLIIT (Sri Lanka Institute of Information Technology)

---

## Overview

This project automates the testing of the **Chat Sinhala transliteration** function available at [https://www.pixelssuite.com/chat-translator](https://www.pixelssuite.com/chat-translator).

The automation script uses **Playwright** to:
- Input Singlish test cases into the translator
- Capture the actual Sinhala output produced by the site
- Compare it against the expected Sinhala output
- Record the result in the Excel file automatically

---

## Project Structure

```
test_automation/
│
├── test_automation.py              # Main Playwright automation script
├── IT23734920.xlsx                 # Test cases with results
└── README.md                       # This file
```

---

## Prerequisites

Make sure the following are installed on your machine:

- **Python 3.11 or 3.12**
- **Google Chrome** (recommended) or Chromium

---

## Installation

### Step 1 – Clone the repository

```bash
git clone https://github.com/justtnikiyaa/IT23734920_ITPM_ASSIGNMENT.git
cd IT23734920_ITPM_ASSIGNMENT
cd test_automation\IT23734920
```

### Step 2 – Install dependencies

Run the following commands in your terminal:

```bash
pip install -U pip
pip install playwright openpyxl
playwright install
```

---

## Running the Tests

Run the following command from the project folder:

```bash
python test_automation.py --excel "IT23734920.xlsx" --url "https://www.pixelssuite.com/chat-translator" --wait-ms 3000 --type-delay-ms 80 --slow-mo-ms 200 --save-every 1 --keep-open
```

### Command Options

| Option | Description | Default |
|---|---|---|
| `--excel` | Path to the Excel test cases file | Auto-detected |
| `--sheet` | Excel worksheet name | ` Test cases` |
| `--header-row` | Row number containing column headers | `0` |
| `--max-header-scan-rows` | Maximum rows to scan for headers | `30` |
| `--input-col` | Name of the input column | Auto-detected |
| `--expected-col` | Name of the expected output column | Auto-detected |
| `--actual-col` | Name of the actual output column | Auto-detected |
| `--status-col` | Name of the status column | Auto-detected |
| `--url` | URL of the transliteration app | `https://www.pixelssuite.com/chat-translator` |
| `--output` | Output Excel file path | Same as input file |
| `--save-every` | Save Excel after every N rows | `0` |
| `--headless` | Run browser in headless mode | `false` |
| `--wait-ms` | Wait time after each transliteration | `5000` |
| `--retries` | Retry count for each test case | `8` |
| `--retry-wait-ms` | Wait time between retries | `1000` |
| `--type-delay-ms` | Delay between keystrokes | `30` |
| `--timeout-ms` | Browser/page timeout | `60000` |
| `--slow-mo-ms` | Playwright slow-motion delay | `0` |
| `--keep-open` | Keep browser open after tests | `false` |

---

## Notes

- Only the **Chat Sinhala** transliteration function is tested, not Standard Sinhala or backend APIs
- The script requires an active internet connection to access the transliteration site
- Press `CTRL+C` to stop the script while it is running
