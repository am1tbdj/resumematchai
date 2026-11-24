# ResumeMatch AI

Compare a resume with a job description using a no-key demo or Groq AI feedback.

## Run locally

```powershell
py -m venv .venv
.venv\Scripts\python -m pip install -r requirements.txt
.venv\Scripts\python -m streamlit run app.py
```

## Use Groq

Create your own key at https://console.groq.com/keys. Select AI-powered (Groq API) and enter the key in the password field, or set GROQ_API_KEY in the server environment. Never commit keys. This version uses openai/gpt-oss-20b hosted by Groq, with low reasoning and a 45-second request timeout. The model name does not mean the app calls OpenAI.

Free-plan requests and tokens are limited by your Groq account. AI mode sends the resume and job description to Groq; remove personal information first. Demo mode makes no model API calls. Uploaded PDFs must contain selectable text.

The main prompt asks for evidence, skill gaps, a 40/30/20/10 rubric, and up to two revised bullets without invented claims. Reports can be downloaded as JSON. Scores are estimates, not validated ATS scores or hiring predictions.

## Streamlit deployment

Replace app.py and requirements.txt in the repository Streamlit runs (resumematchai), commit, and reboot the app. The README may also be replaced. Enter your Groq key in the app; the code does not bundle a shared key. The app reads GROQ_API_KEY from environment variables, not directly from Streamlit's secrets manager.

## Validation

Request construction, timeout settings, response parsing, and malformed responses are tested with a mocked Groq client. No live Groq API request has been tested without a user-owned key.
