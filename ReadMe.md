---

# Discord Username Checker

This Python script is designed to check the availability of Discord usernames and save the available ones to a file. It supports both single-token and multi-token modes, and can also send a webhook notification when an available username is found.

## Features

- **Check Username Availability**: It allows you to generate random usernames and check if they are available on Discord.
- **Multi-token Support**: Can use multiple Discord tokens for rate-limited operations.
- **Webhook Notifications**: Sends a Discord webhook notification when a username is available.
- **Configurable Delay**: Adjustable delay between requests to avoid rate limiting.

## Prerequisites

- Python 3.6+.
- Dependencies:
  - `requests`
  - `colorama`
  
  You can install these using pip:

  ```bash
  pip install requests colorama
  ```

## Configuration

Before running the script, make sure to configure the settings in `config.ini` and the `tokens.txt` file.

### `config.ini` Configuration:

```ini
[sys]
TOKEN = ""                    ; Single token (Leave empty if using multiple tokens)
MULTI_TOKEN = False            ; Set to True if using multiple tokens
WEBHOOK_URL = ""               ; Webhook URL for notifications

[config]
default_delay = 1             ; Default delay between requests in seconds
string = True                 ; Allow letters in generated usernames (True/False)
digits = True                 ; Allow digits in generated usernames (True/False)
punctuation = True            ; Allow punctuation in generated usernames (True/False)
```

### `tokens.txt` Configuration (for Multi-token Mode):
- Store your Discord tokens in `tokens.txt` (one token per line).
  
Example of `tokens.txt`:

```txt
YOUR_DISCORD_TOKEN_1
YOUR_DISCORD_TOKEN_2
YOUR_DISCORD_TOKEN_3
```

## Usage

Run the script using:

```bash
python discord_username_checker.py
```

### Main Menu Options:

1. **Generate and Check Usernames**: This option generates random usernames based on your configuration and checks if they are available.
2. **Check a Specific List**: This option checks usernames from a predefined list in the `usernames.txt` file.

### Adjusting the Delay:

- You can change the default delay between requests by selecting option 1, which will prompt you to edit the delay.

### Available Usernames:

- The available usernames will be saved in a file called `available_usernames.txt`.

### Webhook Notifications:

- If you provide a valid webhook URL in the `config.ini`, a message will be sent to the webhook when a username is available.

## Example Output

```
════════════════════════════════════════════════════════════════════════════════════════════════════════════════════════
  Discord Username Checker 
  GitHub: https://github.com/dk6m                     Connected as Support#1234

  Make a choice:                             
  1-Generate names and check
  2-Check a specific list

  Discord Username checker.
════════════════════════════════════════════════════════════════════════════════════════════════════════════════════════

[+] 'example_username' available.
[+] 'another_username' available.

Done. 2 Available usernames, are saved in the following file: 'available_usernames.txt'.
Press Enter to exit.
```

## Troubleshooting

- **No token found**: Ensure you have either a valid token in `config.ini` or tokens in `tokens.txt` if using multiple tokens.
- **Rate Limit Hit**: The script will automatically handle rate limiting by waiting for the specified time. You can adjust the delay in the configuration.

## License

This script is open-source and available under the MIT License. Feel free to contribute, fork, or use it in your own projects!

---

This `README.md` provides an overview of the script, configuration instructions, usage details, and troubleshooting tips for users.
