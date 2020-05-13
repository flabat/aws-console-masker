# aws-console-masker

A browser script that replaces sensitive information from the AWS Console.

The script conceals details from the AWS console, useful for screen sharing, screenshots, recording a demo, etc.

## Installation

Install from https://github.com/flabat/aws-console-masker/raw/master/aws-console-masker.user.js

## Configuration

You can modify the ReplaceArry pairs in the script with a combination of text to match (you can use regular expressions) and the desired text to show in the console. For example:

```js
var replaceArry = [
        [/([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})/, 'johndoe@example.com'], // email address
        [/\d{12}/, '123456789012'], // 12 digit AWS Account #s
        [/\b\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}\b/, '10.24.34.0'], // IP Addresses
        [/\b\d{1,3}\-\d{1,3}\-\d{1,3}\-\d{1,3}\b/, '10-24-34-0'], // EC2 DNS CNAME IPs
        [/(^|[^A-Z0-9])[A-Z0-9]{20}(?![A-Z0-9])/, 'AIDACKCEVSQ6C2EXAMPLE'], // IAM Access Key ID
        // etc.
        ];
 ```

