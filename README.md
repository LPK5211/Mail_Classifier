# Mail_Classifier
**Smart Mail Bot**

Automated Gmail bot that reads recruiter emails, extracts job details, and replies intelligently with resumes, forms, and documents. Built with Python, Gmail API, and Hugging Face Transformers.

**Features**

Reads JDs → extracts skills, required years, location, work mode (onsite/remote/hybrid), and locals-only.

Candidate Matching → picks the best candidate from /profiles/<slug>/ based on skills/years/location.

Automatic Replies:

Sends initial in-thread reply with resume + templated message.

Detects requests for resume, work authorization, skill matrix, forms → fills forms, ticks checkboxes, attaches requested docs.

Interview requests → alerts you via email, waits for approval file (interview_ok.json) before accepting.

Follow-up after 24h: “I am waiting for your answer.”

Dedupe Safety → won’t resend to the same recruiter or domain within 30 days.

Intent Detection → PyTorch + Transformers + regex overrides for safety.

**Technologies**

Language: Python 3

Google APIs: Gmail API (google-api-python-client, google-auth-oauthlib)

NLP: Hugging Face Transformers + PyTorch

Document Parsing: pdfminer.six, python-docx

Data Management: JSON state files, regex parsing, SHA1 JD fingerprints

Automation: Continuous loop (default 60s), automatic follow-ups
