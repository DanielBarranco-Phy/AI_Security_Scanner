# AI Security Scanner

A Python command line interface tool that leverages the Gemini AI API to scan codebases for security vulnerabilities. The application acts as an automated security expert, processing local Python files and returning structured, colour coded reports that prioritise vulnerabilities by severity.

## Key Features

* **Engineered an automated scanning pipeline:** Built a Python application that reads local files and streams the codebase directly to the Gemini API for comprehensive security analysis.
* **Developed structured AI interactions:** Applied prompt engineering techniques to force the Large Language Model into returning consistent, parseable data structures rather than conversational text.
* **Implemented visual triage systems:** Integrated the Colorama library to parse the AI output and automatically colour code vulnerabilities (Critical, High, Medium, Low) to prioritise developer workflows.
* **Identified critical vulnerabilities:** Successfully tested the architecture against files containing SQL injections, command injections, weak cryptography, and hardcoded credentials.

## Technical Stack

* **Language:** Python 3
* **AI Integration:** Google Gemini 2.5 Flash API
* **Libraries:** `google_genai`, `python_dotenv`, `colorama`, `sys`, `os`

## How It Works

The tool uses the `sys` library to accept a file path via the command line. It reads the target file and injects the raw code into a highly structured security prompt. This prompt instructs Gemini to act as a cybersecurity expert and format its response with specific severity tags. The application then intercepts the response, applies terminal colour formatting based on the severity level, and outputs an actionable security report.

## Installation and Usage

1. Clone this repository to your local machine.
2. Create a virtual environment and activate it.
3. Install the required dependencies:
   `pip install -r requirements.txt`
4. Create a `.env` file in the root directory and add your Google AI API key:
   `GOOGLE_API_KEY=your_api_key_here`
5. Run the scanner against any Python file:
   `python3 scanner.py vulnerable.py`
