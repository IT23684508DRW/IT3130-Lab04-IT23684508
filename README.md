# IT3130 Lab 04 — Version Control / Git Workflows

This repository contains the practical work for IT3130 Lab Sheet 4 (Version Control / Git Workflows).

Structure
- `profile.html` — sample student profile page added on a feature branch.
- `lab-submission.md` — evidence checklist and answers prepared for submission.

Workflow
- Feature branches follow the naming convention: `feature/<student-id>/<short-feature-name>`.
- Work is isolated in feature branches, pushed to the remote, reviewed via pull requests, and merged into `main`.

How to reproduce
1. Clone the repository:
	```bash
	git clone https://github.com/IT23684508DRW/IT3130-Lab04-IT23684508.git
	cd IT3130-Lab04
	```
2. Create and switch to a feature branch:
	```bash
	git switch -c feature/IT23684508/profile-page
	```
3. Make changes, commit, and push:
	```bash
	git add .
	git commit -m "Describe change"
	git push -u origin feature/IT23684508/profile-page
	```

Replace `IT23684508` with your student ID and follow the lab sheet instructions for pull requests and reviews.
