# Vinicius Rodrigues Silva - Curriculum Vitae (LaTeX)

![LaTeX](https://img.shields.io/badge/LaTeX-XeTeX-blue.svg?style=for-the-badge&logo=latex&logoColor=white)
![PDF](https://img.shields.io/badge/PDF-Single%20Page%20(1%2F1)-brightgreen?style=for-the-badge&logo=adobeacrobatreader&logoColor=red)
![GitHub Actions](https://github.com/rsvinicius/resume/actions/workflows/compile-latex-to-pdf.yml/badge.svg)

This repository maintains my professional resume written in **LaTeX (XeTeX)** following the classic Harvard / Jake's Resume standard. Whenever changes are pushed to `main`, a **GitHub Actions CI/CD workflow** automatically compiles both **English** and **Portuguese (PT-BR)** versions to clean, single-page, ATS-compliant PDFs.

---

## 📄 Download Latest PDFs

* 🇺🇸 **English Version (1 page):** [`pdf/Vinicius_Silva_CV_EN.pdf`](pdf/Vinicius_Silva_CV_EN.pdf)
* 🇧🇷 **Versão em Português (1 página):** [`pdf/Vinicius_Silva_CV_PT.pdf`](pdf/Vinicius_Silva_CV_PT.pdf)
* 🌐 **Web Portfolio:** [rsvinicius.github.io/portfolio](https://rsvinicius.github.io/portfolio/)

---

## 📁 Repository Structure

```text
resume/
├── .github/workflows/
│   └── compile-latex-to-pdf.yml  # Automated CI/CD pipeline
├── Fonts/                        # Local Charter & FontAwesome typefaces
├── Images/                       # Icons and logos
├── pdf/                          # Compiled production PDFs (EN & PT-BR)
│   ├── Vinicius_Silva_CV_EN.pdf
│   ├── Vinicius_Silva_CV_PT.pdf
│   └── Vinicius_Silva_Senior_Software_Engineer_CV.pdf
├── sections/
│   ├── en/                       # English sections (Skills, Experience, Education, Projects)
│   └── pt/                       # Portuguese sections (Habilidades, Experiência, etc.)
├── main_en.tex                   # Root document for English CV
├── main_pt.tex                   # Root document for Portuguese CV
├── main.tex                      # Default root document (XeLaTeX)
└── README.md
```

---

## ⚙️ Automated Compilation (CI/CD)

The GitHub Actions workflow defined in [`.github/workflows/compile-latex-to-pdf.yml`](.github/workflows/compile-latex-to-pdf.yml) automatically executes on any push modifying `.tex` files or assets:

1. **Compilation Engine:** Runs `xelatex` using `xu-cheng/latex-action@v3`.
2. **Dual-Language Build:** Compiles `main_en.tex` and `main_pt.tex`.
3. **Artifact Persistence:** Copies the outputs to `pdf/` (both canonical and timestamped).
4. **Git Auto-Commit:** Commits and pushes the updated PDFs with `[skip ci]`.

---

## 🛠️ Local Compilation (Docker / XeLaTeX)

To compile locally using Docker without installing full TeX Live on your host:

```bash
# English
docker run --rm -v $(pwd):/work -w /work texlive/texlive:latest xelatex -interaction=nonstopmode main_en.tex

# Portuguese
docker run --rm -v $(pwd):/work -w /work texlive/texlive:latest xelatex -interaction=nonstopmode main_pt.tex
```
