# Reson-Security-Assessment-App

A full-stack web application that enables organizations to conduct structured video-based security assessments online. Users record video responses to assessment questions, and OpenAI's API automatically analyzes and scores the results. The platform includes two separate interfaces — one for end users taking the assessment, and one for clients managing and configuring it.

## Project Structure

secureassess/
├── __MACOSX/
├── backend/                                          # Python backend — User app logic & API
├── Backend Reson Application-reson-backend-api       # Python backend — Client app logic & API
├── frontend                                          # React app — User-facing assessment interface
├── Frontend Reson Application                        # React app — Client-facing management interface
└── apidb                                             # MySQL - Database Configurations

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React.js |
| Backend | Python |
| Cloud Infrastructure | AWS Elastic Beanstalk, AWS Lambda |
| AI & Transcription | OpenAI API |
| Authentication | JWT-based login |

---

## Application Overview

### User Side (`frontend-user` + `backend-user`)

The user-facing application guides candidates through a structured video assessment:

1. **Login** — Users authenticate into the platform securely
2. **Introduction Video** — Users watch a mandatory security assessment briefing video outlining all rules and regulations before proceeding
3. **Assessment** — Users go through a set of questions (typically 5–10). Each question is presented as a video, and users record and upload their video response on the same page
4. **Submission** — Once all questions are answered, users submit their assessment
5. **AI Results** — OpenAI's API processes all video responses, extracts text, and generates a structured assessment result displayed to the user

### Client Side (`frontend-client` + `backend-client`)

The client-facing application allows organizations to fully configure and manage assessments:

1. **Question Management** — Clients record and upload video questions, choosing how many questions to include (e.g. 5, 6, or 10)
2. **Introduction Video** — Clients record and upload the security assessment briefing video shown to users before the assessment begins
3. **Rules & Regulations** — Clients define and configure the terms and conditions of the assessment
4. **Assessment Oversight** — Full control over the structure and content of every assessment session

---

## Prerequisites

Make sure you have the following installed before running the project:

- Node.js v18+
- Python 3.10+
- pip
- AWS CLI (configured with appropriate credentials)
- OpenAI API Key

---

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Mohiuddin-17/Reson-Security-Assessment-App.git
cd your-repo-name
```

### 2. Environment Variables

Create a `.env` file inside each backend folder. Required variables:

**backend-user/.env**

OPENAI_API_KEY=your_openai_api_key
AWS_ACCESS_KEY_ID=your_aws_key
AWS_SECRET_ACCESS_KEY=your_aws_secret
AWS_REGION=your_region

### 3. Run the User Frontend

```bash
cd frontend-user
npm install
npm start
```

### 4. Run the Client Frontend

```bash
cd frontend-client
npm install
npm start
```

### 5. Run the User Backend

```bash
cd backend-user
pip install -r requirements.txt
python app.py
```

### 6. Run the Client Backend

```bash
cd backend-client
pip install -r requirements.txt
python app.py
```

---

## AWS Infrastructure

This application is deployed using:

- **AWS Elastic Beanstalk** — Hosts and manages the Python backend environments
- **AWS Lambda** — Handles serverless functions for video processing and AI result generation

Ensure your AWS credentials are correctly configured before deployment.

---

## License

This project was developed for a private international client. All rights reserved.
