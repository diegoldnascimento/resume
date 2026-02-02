# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Diego Lopes's personal resume. LaTeX-based, single-page, one-column format. Diego is a Staff Software Engineer with 10+ years of experience, currently at Hona.

**Repository:** `gh repo clone diegoldnascimento/resume`

## Build Commands

**Build PDF locally using Docker:**
```sh
./build.sh
```

Or manually:
```sh
docker build -t sb2nov/latex .
docker run --rm -i -v "$PWD":/data sb2nov/latex pdflatex diego_lopes_resume.tex
```

**CI/CD:** GitHub Actions automatically compiles the PDF on push/PR to master using `thomasweise/docker-texlive-full` image.

## File Structure

- `diego_lopes_resume.tex` - Main resume source file
- `diego_lopes_resume.pdf` - Generated PDF output
- `Dockerfile` - Ubuntu-based image with texlive-full for local builds

## LaTeX Custom Commands

The template defines these custom commands for consistent formatting:

| Command | Purpose |
|---------|---------|
| `\resumeSubheading{title}{location}{subtitle}{dates}` | Job/education entry with 4 fields |
| `\resumeSubSubheading{title}{dates}` | Secondary subheading (role changes) |
| `\resumeItem{title}{description}` | Bullet point with bold title |
| `\resumeSubItem{title}{description}` | Sub-item variant |
| `\resumeSubHeadingListStart` / `\resumeSubHeadingListEnd` | Wrap section entries |
| `\resumeItemListStart` / `\resumeItemListEnd` | Wrap bullet points |
