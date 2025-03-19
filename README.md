# SMS Automation using Twilio

## 📌 Project Overview
This project is a simple SMS automation system using Twilio's API. It allows users to send automated messages to phone numbers, making it useful for notifications, reminders, and alerts.

## ⚙️ Features
- Send SMS messages programmatically.
- Supports multiple recipients.
- Customizable message templates.
- Secure API authentication using environment variables.

## 🛠️ Technologies Used
- **Python**
- **Twilio API**

## 🚀 Installation & Setup

### 1️⃣ Prerequisites
- Python 3.x installed
- Twilio account with a registered phone number

### 2️⃣ Clone the Repository
```sh
git clone https://github.com/yourusername/sms-automation.git
cd sms-automation
```

### 3️⃣ Install Dependencies
```sh
pip install twilio
```

### 4️⃣ Set Up Twilio Credentials
Create a `.env` file in the project folder and add your Twilio credentials:
```
TWILIO_ACCOUNT_SID=your_account_sid
TWILIO_AUTH_TOKEN=your_auth_token
TWILIO_PHONE_NUMBER=your_twilio_number
```

### 5️⃣ Run the Script
```sh
python send_sms.py
```

## 📜 Code Example
Create a `send_sms.py` file and add the following:
```python
import os
from twilio.rest import Client
from dotenv import load_dotenv

load_dotenv()

# Twilio credentials
account_sid = os.getenv("TWILIO_ACCOUNT_SID")
auth_token = os.getenv("TWILIO_AUTH_TOKEN")
twilio_number = os.getenv("TWILIO_PHONE_NUMBER")

def send_sms(to, message):
    client = Client(account_sid, auth_token)
    message = client.messages.create(
        body=message,
        from_=twilio_number,
        to=to
    )
    print(f"Message sent to {to}, SID: {message.sid}")

# Example usage
if __name__ == "__main__":
    send_sms("+1234567890", "Hello from Twilio!")
```

## 🛠️ Customization
- Modify `send_sms.py` to support bulk messaging.
- Integrate with a database to fetch dynamic messages.
- Schedule messages using `schedule` or `cron`.

## 📝 License
This project is open-source and available under the MIT License.

## 💡 Contribution
Feel free to fork the repository and submit pull requests for improvements!

---
🚀 **Start automating SMS today with Twilio!**
