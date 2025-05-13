# WebClicker Auto Answer

A Python automation tool that automatically answers WebClicker polls with random selections.

## Features

- Automatically detects when a new poll is active
- Randomly selects an answer choice (A, B, C, D, or E)
- Works with browser in visible or headless mode
- Handles login if credentials are provided

## Installation

1. Ensure you have Python 3.7+ installed
2. Clone this repository or download the files
3. Install dependencies:

```bash
pip install -r requirements.txt
```

4. Download the appropriate ChromeDriver for your Chrome version from [ChromeDriver downloads](https://chromedriver.chromium.org/downloads) or let webdriver-manager handle it automatically.

## Usage

Run the script with the WebClicker URL:

```bash
python webclicker_auto.py --url "https://webclicker.web.app/student/yourUniqueSessionID"
```

### Command-line options

- `--url`: (Required) The URL of your WebClicker session
- `--interval`: (Optional) How often to check for new polls, in seconds (default: 5)
- `--headless`: (Optional) Run Chrome in headless mode (no visible browser)
- `--username`: (Optional) Username for login if required
- `--password`: (Optional) Password for login if required

Example with all options:

```bash
python webclicker_auto.py --url "https://webclicker.web.app/student/yourUniqueSessionID" --interval 3 --headless --username "student@example.com" --password "your_password"
```

## How It Works

1. The script opens the WebClicker URL in a Chrome browser
2. It continuously checks for active polls (looking for the absence of "No current poll" indicator)
3. When a poll is detected, it identifies the available answer choices
4. It randomly selects one option and clicks it
5. It waits for the next poll to appear

## Customization

You may need to adjust the CSS selectors in the code based on the actual structure of the WebClicker site. The key functions to modify if needed are:

- `is_poll_active()`: Detection of active polls
- `get_answer_choices()`: Finding the available answer options
- `select_random_answer()`: Clicking the selected answer

## Notes

- This tool is for educational purposes only
- Use responsibly and in accordance with your institution's academic integrity policies
- The developers are not responsible for any misuse of this tool 