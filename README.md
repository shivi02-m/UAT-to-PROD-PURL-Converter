# UAT-to-PROD-PURL-Converter
This web-based tool converts UAT PURLs (Package URLs) to PROD-ready PURLs automatically, reducing manual errors in deployment pipelines.

Folder Structure:
project/
├── app.py                # Flask backend server
├── templates/
│   └── index.html        # Main HTML file with JS logic
├── static/
│   └── servers.json      # Assignment Group JSON (no DB needed)
├── README.md             # This file with setup & usage instructions
└── requirements.txt      # (Optional) Flask dependency

What is a PURL?
PURL stands for Package URL —
It’s a structured URL automatically generated when any application is deployed to UAT (User Acceptance Testing) environment.

This URL contains:
✅ Commit ID — The code snapshot reference
✅ Branch Name — The feature or release branch
✅ Artifact Instance — The package repository location
✅ Ansible Variables — Extra deployment parameters (e.g., environment, host, playbook)

🛠 Why Do We Need This Utility?
When promoting changes from UAT to PROD, the deployment PURL must point to the correct PROD servers and parameters.

✅ Currently — Developers manually adjust UAT PURLs for PROD deployments when raising Change Requests.
❗ This leads to human error, wrong parameters, or missed host updates.
💡 This Utility Automates That Process
✅ Converts UAT PURLs into valid PROD-ready PURLs
✅ Ensures correct PROD hostnames & parameters
✅ No manual editing — easy web interface
It saves time, reduces human mistakes, and improves deployment accuracy.

Example Usage:
Input UAT PURL:
pkg:bitbucket/playbooks@12345?artifactinstance=abc&env=uat&host_name=uat@host.com

Generated PROD PURL:
pkg:bitbucket/playbooks@12345?artifactinstance=abc&env=prod&host_name=prod-server-1

⚠️ Error Handling:
❗ Missing host_key shown in bold red.
❗ Invalid URL format detected & displayed.
✅ Green for successful generated output.

Who Should Use This?
Developers submitting deployment Change Requests
Release & Deployment Engineers
DevOps Teams & Automation Engineers
QA validating deployment artifacts


🔥 Try It Yourself
1️⃣ Clone this repo
git clone https://github.com/yourrepo/uat-to-prod-purl-converter.git
cd uat-to-prod-purl-converter

2️⃣ Install dependencies
pip install flask

3️⃣ Run the app
python app.py

4️⃣ Open in Browser
http://localhost:5000

📝 Contributions
PRs and suggestions welcome! Feel free to fork and customize.
  



