# Phase 2: GitHub CI/CD Workflow

Follow these steps for every new feature or bugfix to ensure consistent quality, testing, documentation, and deployment.


1. Create & Switch to a Feature Branch

	•	Keeps main clean and prevents unfinished work from leaking into production.
	•	Use a descriptive name (e.g. feature/login-form, bugfix/typo-in-readme).


2. Implement Your Changes
	•	Write or update code in src/.
	•	Add or update Jest unit tests under __tests__/.


3. Push & Open a Pull Request to main

	•	Use the Pull Request template.


4. Automated Status Checks Run

When the PR is opened or updated, the pipeline triggers:

fmt:	Runs qlty fmt to automatically apply the auto-formatting rules to enforce a consistent styling across all files. It recommits the changes with the fixed styling.

tests:	Runs unit test using Jest:- Fails if any test errors occur.

coverage → Uploads data to Codacy, and the Dashboard shows coverage %, complexity, unused code, bad practices, etc.

✅ All checks must pass before merging.
🔒 Branch protection is enabled on main, disallowing merges until all status checks pass.

5. Code Review & Approval
	•	At least two team members must review and approve the PR.
	•	Use our Code Review Template to ensure:
	•	Functional correctness
	•	Adequate test coverage
	•	Security and performance considerations
	•	Clean commit history

6. Merge & Cleanup
	1.	Click Merge once:
	•	All checks are green.
	•	Two approvals are in place.
	2.	Delete your feature branch on GitHub:
	•	Keeps the repository tidy.
	•	Prevents naming conflicts in the future.

7. Post-Merge Automation

After merging into main:
1.	Docs Build & Deploy
-	Runs JSDoc to automatically generate API docs for every JavaScript function.
-	Developers can browse the live API reference at /docs on the GitHub Pages deplotment.

With this pipeline in place, every merge to main delivers code that is:
	1.	Formatted consistently
	2.	Fully tested (≥ 60% coverage)
	3.	Static-analyzed for complexity & quality
	4.	Peer-reviewed by at least two teammates
	5.	Documented with auto-generated JSDoc
	6.	Published to GitHub Pages

This ensures rock-solid reliability, maintainability, and visibility for all our code changes.
