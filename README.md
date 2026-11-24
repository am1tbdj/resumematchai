# ResumeMatch AI prompt comparison

Upload all four files in this folder to the repository used by Streamlit. Reboot the app.

Select AI-powered (Groq API), enter your own key, expand Milestone 2 prompt comparison, and click Run v1, v2 and v3. Then download prompt_comparison_results.json. The comparison uses the same built-in fictional sample for all three prompts; it does not transmit an uploaded resume.

The run makes three API requests and consumes quota. It can take up to roughly 135 seconds plus connection overhead if every request reaches its timeout. There are no automatic retries. Error records are real failed attempts, not successful outputs. JSON validity and field counts are structural checks, not accuracy measurements.

Send the downloaded results back to update the report with genuine observations. Do not include your key. The results file records prompts, input, model, output, timings, response identifiers and failures. Before these requests run, no live comparison result has been established.
