# 📄 Infrastructure-as-Code Resume

[![CircleCI](https://circleci.com/gh/minhnguyen1908/latex_cv.svg?style=shield)](https://circleci.com/gh/minhnguyen1908/latex_cv)
![Docker](https://img.shields.io/badge/container-ubuntu%3Ajammy-blue)
![License](https://img.shields.io/badge/license-CC%20BY--SA%204.0-lightgrey)

> **"I don't just write code; I code my own documents."**

This repository contains the source code for my professional resume, written in **LaTeX**. It treats the document lifecycle exactly like a software product: version-controlled, modular, and built automatically via a **CI/CD pipeline**.

## 🏗 Architecture & Tools

* **Typesetting Engine:** LuaLaTeX (via `latexmk`)
* **Environment:** Docker (`ubuntu:jammy` with TexLive)
* **Secret Management:** PII (Personally Identifiable Information) is decoupled from the codebase using a `personal.tex` file.
* **CI/CD:** CircleCI (Compiles a fresh PDF on every commit).

## 🔒 Privacy & Security Strategy

If you view the source code or preview images, you will see generic phone numbers (`+84 000...`) or redacted emails. **This is a feature, not a bug.**

To follow **DevOps Security best practices**, I do not commit sensitive personal data to public repositories.

* **Public Repo:** Uses `example/personal_dummy.tex` (Sanitized data).
* **Private Build:** My local machine injects `example/personal.tex` (Real data).
* **.gitignore:** Ensures the real data file never leaks to GitHub.

## 🚀 How to Build

### Option A: The "DevOps" Way (CI/CD)
You don't need to build it. **The robot already did.**
1. Click the **CircleCI** badge at the top.
2. Go to the **Artifacts** tab of the latest build.
3. Download `example/cv.pdf`.

### Option B: The "Local" Way (Manual)
If you want to compile it yourself, you need a LaTeX distribution (like TeX Live).

```bash
# 1. Clone the repo
git clone [https://github.com/minhnguyen1908/latex_cv.git](https://github.com/minhnguyen1908/latex_cv.git)
cd latex_cv

# 2. Build using latexmk
cd example
latexmk -cd -f -lualatex -interaction=nonstopmode -synctex=1 cv.tex

# 3. Output
# The 'cv.pdf' will be generated in the 'example/' folder.
````

## 🤝 Credits & Template

This project is built upon the excellent [YAAC Another Awesome CV](https://github.com/darwiin/yaac-another-awesome-cv) template by **Christophe Roger (Darwiin)**.

  * **Original License:** [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)
  * **Modifications:** \* Refactored for `docker` based builds.
      * Added `personal.tex` separation for PII security.
      * Configured for CircleCI automation.

-----

**Author:** Minh Nguyen
