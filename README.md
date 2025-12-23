✅ GitHub Actions Setup using CMD
________________________________________
🔹 Step 1: Create Project Folder
1.	Create a folder named bsr
2.	Open Command Prompt
3.	Go to the folder:
cd C:\bsr
________________________________________
🔹 Step 2: Initialize Git (Local Repository)
git init
________________________________________
🔹 Step 3: Create Python File
Create app.py:
type nul > app.py
Open and add:
def add(a, b):
    return a + b

assert add(2, 3) == 5
print("Test passed")
Save and close.
________________________________________
🔹 Step 4: Configure Git (One Time Only)
git config --global user.email "yourmail@gmail.com"
git config --global user.name "yourusername"
________________________________________
🔹 Step 5: Create GitHub Repository
1.	Login to GitHub
2.	Create a new repository named bsr
________________________________________
🔹 Step 6: Connect Local Repo to GitHub
git remote add origin https://github.com/yourusername/bsr.git
________________________________________
🔹 Step 7: Create GitHub Actions Folder Structure
Run exactly in this order:
mkdir .github
cd .github

mkdir workflows
cd workflows
________________________________________
🔹 Step 8: Create YAML File (CMD Way)
type nul > bsr.yml
✔️ YAML file created
________________________________________
🔹 Step 9: Add YAML Content
Open bsr.yml and paste:
name: Python CI

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-python@v4
        with:
          python-version: '3.x'
      - run: python app.py
Save and close.
________________________________________
🔹 Step 10: Go Back to Project Folder
cd ..
cd ..
________________________________________
🔹 Step 11: Commit and Push Code
git branch -M main
git add .
git commit -m "Initial Commit"
git push -u origin main
________________________________________
🔹 Step 12: Verify Pipeline
1.	Open GitHub repository
2.	Click Actions
3.	Workflow runs automatically
✅ Green tick → Success
❌ Red cross → Failure


