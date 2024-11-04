
# Email Automation and Summarization with Gmail API

This project automates the retrieval, summarization, and keyword extraction of unread Gmail messages. Using the Gmail API, Python NLP tools, and Hugging Face transformers, the code fetches unread emails, cleans the content, extracts key information, and provides direct links to the emails. This tool is ideal for users who want to quickly prioritize or scan through their unread Gmail messages.

## Features

- Email Authentication: Uses OAuth2 to authenticate with Gmail via the Gmail API.
- Unread Email Retrieval: Fetches all unread emails from your Gmail inbox.
- Content Cleaning: Strips introductory headers, common email phrases, and signatures for a cleaner summary.
- Summarization: Generates concise summaries of email content using the `facebook/bart-large-cnn` model from Hugging Face.
- Keyword Extraction: Identifies the most relevant keywords from each email to aid in topic identification.
- Direct Links: Each summarized email contains a link back to the full message in Gmail for easy access.

## Getting Started

### Prerequisites

Ensure you have the following installed:
1. Python 3.7+
2. Gmail API credentials file (`client_secret.json`)
3. Dependencies listed in `requirements.txt`

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/email-automation.git
   cd email-automation
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Set up Gmail API:
   - Enable the Gmail API in [Google Cloud Console](https://console.cloud.google.com/).
   - Download `client_secret.json` and place it in the project root directory.

## Usage

1. Authenticate with Gmail:
   - On the first run, the app will ask you to authenticate and authorize access to Gmail.
   - It will save the credentials in `token.json` for future use.

2. Run the application:
   ```bash
   python app.py
   ```

3. Output:
   - The script will print each unread email’s:
     - Subject
     - Summary (processed content)
     - Extracted Keywords
     - Direct Link to the full email in Gmail

### Example Output 

```plaintext
Subject: Project Meeting Reminder
Summary: The project meeting will cover updates on deliverables, recent milestones, and goals for the next quarter...
Keywords: ['meeting', 'deliverables', 'milestones', 'project', 'quarter']
Link: https://mail.google.com/mail/u/3/#inbox/192f5e8496928362
```

## Troubleshooting

- Invalid Token: If you encounter token-related errors, delete `token.json` and rerun the application to re-authenticate.
- Gmail API Quota: The Gmail API has usage limits. If you encounter quota issues, wait for the quota to reset or consider optimizing API calls.

## Dependencies

See `requirements.txt` for a complete list of required packages, including:

- `google-auth`, `google-auth-oauthlib`, `google-auth-httplib2`
- `google-api-python-client`
- `transformers` (for Hugging Face summarization model)
- `scikit-learn`

## Acknowledgments

- [Google Gmail API](https://developers.google.com/gmail/api)
- [Hugging Face Transformers](https://huggingface.co/transformers/)
