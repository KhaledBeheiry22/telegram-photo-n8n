Telegram Photo → AI Caption Generator

A lightweight automated workflow built with n8n, Telegram Bot API, and OpenAI Vision.
The system receives an image from a Telegram bot, processes it through an AI Vision model, and returns a creative caption instantly.

🏗 System Architecture

Tech Stack: n8n, Telegram Bot API, OpenAI Vision (GPT-4o mini), Base64 Image Processing.

🔄 Workflow Architecture
Workflow Node Breakdown
Telegram Trigger (Image Receiver)

Role: Entry point of the pipeline.
Function: Listens for incoming images sent to the Telegram bot.
Purpose: Provides real-time event-based execution without any manual triggering.

Get File (Image Downloader)

Role: File Extraction.
Function: Retrieves the highest-resolution image from the Telegram API using the file_id.
Purpose: Converts the Telegram message into an actual image file ready for AI processing.

Analyze Image (AI Vision Model)

Role: Content Generation (LLM Vision).
Function: Sends the Base64-encoded image to the OpenAI Vision model (gpt-4o-mini).
Logic:

Generates 3 types of captions (short, medium, witty)

Returns a recommended best caption

Response enforced as clean JSON for easy parsing
Purpose: Turns raw images into rich, shareable captions.

Send Message (Delivery Layer)

Role: Content Delivery.
Function: Sends the AI-generated caption back to the user via Telegram.
Purpose: Completes the pipeline by delivering the output directly to the user.

📁 Files Included

Telegram Photo.json — full n8n workflow export

workflow.png — architecture screenshot (add yours here)

README.md — documentation file

🛠 Setup & Installation
1️⃣ Import Workflow

Open n8n

Click Import

Upload Telegram Photo.json

2️⃣ Configure Credentials

Inside n8n:

Telegram Trigger / Get File / Send Message:
Add your TELEGRAM_BOT_TOKEN

Analyze Image:
Add your OPENAI_API_KEY

3️⃣ Activate the Workflow

Send any picture to your Telegram bot — the caption returns instantly.