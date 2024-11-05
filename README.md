# Smart WhatsApp Bot with Python

This guide shows how to build a smart WhatsApp bot using Meta’s Cloud API, Python, and Flask. The bot can respond to messages in real-time with AI-generated responses using OpenAI.

## Prerequisites

1. **Meta Developer Account**: [Sign up here](https://developers.facebook.com/).
2. **WhatsApp Business App**: Learn to create one [here](https://developers.facebook.com/docs/development/create-an-app/).
3. **Basic Python Knowledge**: Familiarity with Python and Flask is helpful.

## Setup Steps

### 1. Configure Your Phone Number

- **Get a Test Number**: You’ll start with a test number to send messages to up to 5 contacts.
- **Verify**: Enter your WhatsApp number, and verify it using the code you receive.

### 2. Send Messages with the API

1. **Get Access Token**: Obtain a 24-hour access token in the API settings.
2. **Send a Message**: Use this token to send a “Hello World” message using the API. You can use `curl` or Python’s `requests` library.

### 3. Set Up Flask and Webhooks

1. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

## Run the Flask App

```bash
python run.py

## Expose Localhost with ngrok

1. Sign up and install ngrok.
2. Run `ngrok http 8000` to get a public URL for your Flask app.

## Configure Webhooks in Meta App Dashboard

1. Set the **Callback URL** to your ngrok URL (e.g., `https://your-ngrok-url/webhook`).
2. Enter a **verification token** (a string you choose) and add it to your environment variables.

## Testing the Bot

1. **Send a Message**: Use WhatsApp to send a message to your bot.
2. **Verify**: Check that your app receives the message and responds back.

## Adding AI with OpenAI

### Set Up OpenAI

1. Create an OpenAI account and get an API key.
2. Add `OPENAI_API_KEY` to your environment variables.

### Generate AI Responses

1. Write a `generate_response()` function in `whatsapp_utils.py` to call OpenAI’s API for generating replies.

### Integrate AI in Your Bot

1. Update `process_whatsapp_message()` to use the `generate_response()` function.

## Deploying Your Bot

1. **Run Locally**: Start the bot with `python run.py` and expose it with ngrok for testing.
2. **Deploy**: For production, consider using cloud services to host the bot.

## Tips for Adding a Dedicated Phone Number

When ready for production, consider options for a dedicated WhatsApp number, such as:

- Virtual numbers
- Dual SIM devices
- Separate devices for testing

## Resources

For more help, visit Meta’s [WhatsApp Cloud API documentation](https://developers.facebook.com/docs/whatsapp/cloud-api).
```
