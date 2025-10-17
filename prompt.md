import google.generativeai as genai

genai.configure(api_key="API_KEY")
model = genai.GenerativeModel("gemini-2.5-flash")

job_description = "Meklējam Python izstrādātāju ar pieredzi mašīnmācībā, TensorFlow, un AWS. Nepieciešami vismaz 5 gadi pieredzes."
candidate_resume = "Juris strādā par Python izstrādātāju 6 gadus. Viņam ir pieredze ar PyTorch, Scikit-learn un SQL. AWS zināšanas ir pamata līmenī."

prompt = generate_gemini_prompt(job_description, candidate_resume)

response = model.generate_content(prompt)
print(response.text)
