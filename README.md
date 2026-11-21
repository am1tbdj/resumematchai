# ResumeMatch AI

ResumeMatch AI helps students compare their resume with a job description and work out what to improve before applying.

Paste both texts, or upload a resume PDF, to see which skills match, which ones are missing, and how to make your project descriptions clearer.

Built for the Prompt Engineering C9 project using Python and Streamlit.

## Run it locally

Open PowerShell in the project folder and run:

```powershell
py -m venv .venv
.venv\Scripts\python -m pip install -r requirements.txt
.venv\Scripts\python -m streamlit run app.py
```

Open `http://localhost:8501` if the app does not open automatically.

## Try the demo

The app starts in **Demo (no API key)** mode with a sample resume and job description. Click **Analyze match** to try it, or replace the samples with your own text.

The demo checks for skills from a small, predefined list. Its score shows how many skills found in the job description also appear in the resume. It can miss skills and does not understand context, so use it as a quick first check.

## Get AI feedback

Select **AI-powered (OpenAI API)** in the sidebar and enter your API key, or set the `OPENAI_API_KEY` environment variable. The default model is `gpt-4o-mini`.

This mode asks the model to review four areas:

| Area | Weight |
| --- | --- |
| Technical skills | 40% |
| Relevant experience | 30% |
| Projects | 20% |
| Education | 10% |

The prompt asks for evidence from the supplied text, practical suggestions, and up to two revised resume bullets. It also tells the model to ignore instructions inside the documents and avoid making up qualifications.

You can download the feedback as a JSON report in either mode.

## Use Gemini for AI feedback

1. Create your own key at [Google AI Studio](https://aistudio.google.com/apikey).
2. Select **AI-powered (Gemini API)** in the sidebar.
3. Enter the key in the password field, or set the `GEMINI_API_KEY` environment variable before starting the app.
4. Leave the default model as `gemini-2.5-flash`, or enter a model available to your project.
5. Click **Analyze match**.

Free-tier access depends on your account, model, and usage limits. Check your project's quota and billing settings in AI Studio.

## Things to keep in mind

- PDF uploads need selectable text. For a scanned resume, paste the text instead.
- The scores are rough guides, not validated ATS scores or predictions of getting hired.
- Check every suggestion before adding it to your resume. Only include skills, results, and experience you can support.
- AI mode sends the resume and job description to Google and may incur API charges. Remove personal details first, and keep API keys out of the repository.
- This is a prototype. It still needs testing with a wider range of resumes and job descriptions.

## Project files

- `app.py`: the Streamlit interface, PDF reader, skill matching, and AI prompt.
- `requirements.txt`: the Python packages needed to run the app.
- `README.md`: setup instructions and project notes.
