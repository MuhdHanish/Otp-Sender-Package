# Node OTP Sender

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![npm Version](https://img.shields.io/npm/v/node-otp-sender.svg)](https://www.npmjs.com/package/node-otp-sender)

A simple and lightweight npm package for sending one-time passwords (OTPs) via email using Nodemailer with retry functionality.

## Features

- Generate and send one-time passwords (OTPs) via email
- Retry sending OTP emails in case of temporary network or email server issues
- Simple and easy to use

## Installation

Install the package using npm:

```bash
npm install node-otp-sender
```

## Usage

```javascript

const otpSender = require('node-otp-sender');

const senderEmail = 'your-email@example.com';
const senderPassword = 'your-email-password';
const recipientEmail = 'recipient-email@example.com';
const subject = 'OTP Verification';

// Optional: Customize retry settings
const maxRetries = 3; // Number of retry attempts (default is 3)
const retryDelay = 1000; // Delay between retries in milliseconds (default is 1000 milliseconds or 1 second)

otpSender(senderEmail, senderPassword, recipientEmail, subject)
  .then((response) => {
    console.log(response);
  })
  .catch((error) => {
    console.error('Error:', error);
  });
```
## Customizing Retry Behavior

You can customize the retry behavior by adjusting the maxRetries and retryDelay parameters. maxRetries determines the maximum number of retry attempts, and retryDelay sets the delay between retry attempts.

Make sure to replace 

- your-email@example.com with your actual sender email
- your-email-password with the password of your sender email
- recipient-email@example.com with the recipient's email address
- OTP Verification with your desired subject.
