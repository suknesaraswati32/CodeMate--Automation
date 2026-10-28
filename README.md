# CodeMate AI — Automated Code Commenting & Summary via Email

**CodeMate AI** is an AI-powered email automation workflow built using **n8n, Google Gemini, and Gmail**. It automatically processes incoming emails containing code, generates meaningful code comments, creates a simple summary, converts the results into HTML format, and emails the output to the recipient.

The project helps developers and students understand code more easily without manually reviewing every line.

## ✨ Features

- **📩 Automated Email Trigger:** Checks Gmail for incoming emails from a configured sender every minute.
- **💬 AI Code Commenting:** Uses Google Gemini to add explanatory comments to existing code while instructing the AI not to modify the original code lines.
- **📝 Code Summarization:** Generates an easy-to-understand summary explaining the code's purpose and important functionality.
- **⚡ Parallel Processing:** Processes code commenting and summarization in parallel to make the workflow more efficient.
- **🎨 HTML Email Formatting:** Converts the generated results into HTML format with code blocks for better readability.
- **📤 Automated Email Delivery:** Sends the commented code and summary through Gmail without requiring manual intervention.

## 🛠️ Tech Stack

- **n8n** — Workflow automation
- **Google Gemini** — AI-powered code commenting and summarization
- **Gmail API / OAuth2** — Email triggering and delivery
- **HTML** — Formatting the generated response
- **LLM Chain Nodes** — Managing AI prompts and responses

## ⚙️ How It Works

1. **Email Monitoring:** The Gmail Trigger checks for new emails from the configured sender at one-minute intervals.
2. **Code Commenting:** Google Gemini receives the email's text and generates comments to explain the code.
3. **Code Summarization:** A separate Gemini node summarizes the code in simple language.
4. **Merging Results:** The Merge and Aggregate nodes combine the outputs from both AI processes.
5. **Preparing the Message:** The Edit Fields node organizes the commented code and summary into a single message.
6. **HTML Conversion:** An AI chain converts the message into HTML formatting suitable for email.
7. **Email Delivery:** The Gmail node sends the final response to the configured recipient.

## 🚀 Getting Started

### Prerequisites

Before running the workflow, ensure you have:

- [Node.js](https://nodejs.org/) if installing n8n through npm
- [n8n](https://n8n.io/)
- A Google account with Gmail access
- A Google Gemini API key
- Gmail OAuth2 credentials configured in n8n

### Installation and Setup

**1. Start n8n**

If you installed n8n using npm, run:

```bash
n8n
```

Open the following URL in your browser:

```text
http://localhost:5678
```

**2. Import the workflow**

1. Open your n8n dashboard.
2. Select the workflow menu and choose **Import from File**.
3. Select your exported workflow JSON file.
4. Open the imported workflow.

**3. Configure credentials**

- Connect your Gmail account to the Gmail Trigger and Send Email nodes.
- Configure your Google Gemini API credentials for the Gemini Chat Model nodes.
- Verify the sender email filter and recipient email address.
- Check that the input email's code is available in the field used by the AI prompts.

**4. Test the workflow**

1. Save the workflow.
2. Execute it manually for testing, if supported by the trigger setup.
3. Send a test email containing code from the configured sender.
4. Verify that the workflow generates both the comments and summary.
5. Check the recipient's inbox for the formatted response.

**5. Activate the workflow**

Activate the workflow in n8n so that it can automatically process matching incoming emails.

## 📧 Example Use Case

**Input:** An email containing a Python program.

```python
def add(a, b):
    return a + b

print(add(5, 3))
```

**Expected output:** The email response contains commented code explaining the function and its return statement, along with a summary explaining that the program adds two numbers and prints the result.

*The exact generated comments and summary depend on the code and AI model response.*

## 🎯 Benefits

- Reduces the time required to understand unfamiliar code.
- Helps beginners learn programming concepts.
- Automates repetitive code documentation tasks.
- Combines multiple AI operations in one workflow.
- Delivers results directly through email.
- Demonstrates practical integration of AI and workflow automation.

## 🔮 Future Enhancements

- Support for multiple programming languages, including Python, Java, C++, and JavaScript.
- Automatic detection of programming languages.
- Code debugging and error explanation.
- Code quality suggestions and optimization recommendations.
- Support for code attachments and larger code snippets.
- Improved HTML syntax highlighting and structured email templates.
- Error handling, retry mechanisms, and execution logging.

## 🔐 Security Notes

- Store API keys and OAuth credentials securely using n8n's credential manager.
- Never commit API keys, access tokens, or exported credentials to GitHub.
- Review the workflow's email filters and recipient settings before activating it.
- Avoid sending confidential source code or sensitive information to external AI services unless authorized.

## 👩‍💻 Author

**Saraswati Sukne**

- GitHub: [@suknesaraswati32](https://github.com/suknesaraswati32)
- LinkedIn: [Saraswati Sukne](https://www.linkedin.com/in/saraswati-sukne/)

---

⭐ If you find this project useful, consider giving the repository a star!

**Built with n8n + Google Gemini + Gmail to make understanding code simpler and faster.**
