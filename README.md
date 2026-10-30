# ModuLatex Resume

## What is it?

The **ModuLatex resume** is a component-based Latex template optimized for people who need multiple versions of resumes.

Some advantages over your run-of-the-mill template include:

- Easily make multiple versions of your resume by important different components.
- A sleek design with pretty emojis. 😌
- Adjustable, compact structure lets you pack as much content as your heart desires.
- Sections are customizable to your needs. Add your own custom "volunteering" or "interests" section.
- Links to your social medias and external sites.
- ATS-friendly formatting will save you time from manually fixing errors.

## How do I use it?

Be sure to use **LuaLaTeX** if you plan on using the emojis. Otherwise, you can take them out and use any Latex typesetting system. To set it up for yourself, add your background, skills, experiences, projects, education, and awards to separate `.tex` files in the `components` folder. Make a folder for your resume in the root directory and compile! If you move around the main file, be sure to update the file paths.

## Resume PDF

View or download the [latest committed resume PDF](resume/PriyanshChoudhary_Resume.pdf).

The [Build resume PDF workflow](.github/workflows/resume-pdf.yml) runs when resume
sources change on `master`, or manually from the repository's Actions tab. It:

- Compiles with LuaLaTeX and the template's required fonts.
- Fails if the resume exceeds one page.
- Attaches the PDF as the `resume-pdf` workflow artifact, retained for 90 days.
- Commits the updated PDF back to the triggering branch.

PDF-only commits do not trigger another build. Repository rules must permit
GitHub Actions to push to the target branch; if branch protection blocks the
commit, the workflow reports the failure and the PDF remains available as an
artifact on the workflow run.

To build locally with the required LaTeX packages and Twemoji Mozilla font installed:

```powershell
Set-Location resume
latexmk -lualatex -interaction=nonstopmode -halt-on-error PriyanshChoudhary_Resume.tex
```
