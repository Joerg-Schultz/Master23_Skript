
### Markdown

[Syntax Guide](https://www.markdownguide.org/basic-syntax/)

### Git
[Homepage](https://git-scm.com/)

#### Übung

1. Neues 'empty porject' (click Git repository anlegen)
2. Skript zur Vorlesung; Dateien anlegen **Wichtig** Endung .md
    - Inhaltsverzeichnis
    - Vorlesung 1
    - Vorlesung 2
3. VCS -> Git repository anlegen
4. Macht Änderungen an Vorlesung 1 -> commit (!) mit sinnvollem Kommentar
5. Neuer Branch für Vorlesung 2
6. Änderungen in Vorlesung 2 file
7. Checkout master
8. Merge branch Vorlesung 2 in master

### Github

create repository

Code auf GitHub gepushed


#### Issues

- close via keyword
    - Close
    - Closes
    - Closed
    - Fix
    - Fixes
    - Fixed
    - Resolve
    - Resolves
    - Resolved

#### Pages

Setting -> Pages

Deploy from branch

Select branch, meistens master

#### Releases

Get a DOI for a release:

- https://www.youtube.com/watch?v=A9FGAU9S9Ow&ab_channel=JaanTollanderdeBalsch
- https://www.youtube.com/watch?v=gp3D4mf6MHQ&ab_channel=SerenaBonaretti


#### Actions
Convert markdown files in directory `reports` to pdf
```yaml
name: Markdown Reports to pdf

on:
  push:
   paths:
      - 'reports/**.md'
   branches: 
    master
   
jobs:
  build:
    runs-on: ubuntu-latest
    permissions:
      contents: write

    steps:
      - name: Checkout repository
        uses: actions/checkout@v3
        
      - name: Install Pandoc and LaTeX
        run: |
          sudo apt-get update
          sudo apt-get install -y pandoc texlive
        
      - name: Convert Markdown to PDF
        run: |
          cd ./reports
          find . -name '*.md' -type f -exec sh -c 'pandoc "$0" -o "${0%.md}.pdf"' {} \;

      - name: Commit and push changes
        uses: stefanzweifel/git-auto-commit-action@v4
        with:
          commit_message: Converted Markdown files to PDF
          commit_user_name: GitHub Actions
          commit_user_email: actions@github.com
          branch: master
```
