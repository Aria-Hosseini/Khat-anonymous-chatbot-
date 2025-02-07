# Khat Anonymous Chat Bot - Telegram Bot

## Overview
This is a Python-based Telegram bot that allows users to send anonymous messages to each other. The bot generates unique links for users, allowing them to receive messages from other users without revealing their identity.

## Features
- Allows users to generate anonymous chat links.
- Users can send and receive anonymous messages.
- Supports text, voice messages, images, and GIFs.
- Inline keyboard for quick responses.
- Uses encryption for secure message handling.
- Stores user data in a database.
- Implements a webhook for handling Telegram updates asynchronously.

## Prerequisites
- A Telegram bot token (Get one from [BotFather](https://t.me/BotFather)).
- A database to store user details.
- A hosting service that supports Python (e.g., Vercel, Heroku, or a dedicated server with Python and Pyodide support).

## Installation & Setup
1. Clone the repository or copy the script to your environment.
2. Replace `BOT_TOKEN` with your actual bot token.
3. Set up your database to store user data.
4. Deploy the script on a server that supports Python.
5. Set up the webhook by visiting:
   ```
   https://api.telegram.org/bot<YOUR_BOT_TOKEN>/setWebhook?url=<YOUR_SERVER_URL>/<WEBHOOK_HASH>
   ```
6. Start the bot and test it on Telegram.

## Usage
- Start the bot with `/start`.
- Generate an anonymous chat link by clicking "🔗 دریافت لینک ناشناس".
- Share the generated link with others.
- If someone sends you a message through the link, you will receive it anonymously.
- Reply to anonymous messages by clicking "پاسخ".

## Code Breakdown
### Key Functions
- `on_fetch(request, env)`: Handles incoming requests from Telegram and processes messages.
- `rndKey()`: Generates a random key for users.
- `encrypt(data) / decrypt(encrypted_data)`: Encrypts and decrypts messages securely.
- `postReq(tgMethod, payload)`: Sends API requests to the Telegram bot API.
- `hxId(id) / revHxId(hxid)`: Encodes and decodes user IDs for anonymous messaging.

### Message Flow
1. User starts the bot.
2. They receive a unique anonymous chat link.
3. Others can send messages via the link.
4. The bot forwards the message to the target user.
5. The user can respond anonymously.

## Security Considerations
- User IDs are encrypted before being stored.
- The webhook is secured using an MD5 hash of the bot token.
- Messages are processed securely without exposing user details.

## Contribution
Feel free to fork, modify, or contribute to this bot. If you find any issues, report them via GitHub.

## License
This project is open-source and available under the MIT License.

