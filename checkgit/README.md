**`.gitattributes`** file you can drop into the root of your Node.js / Express project to normalize line endings and avoid those LF/CRLF warnings:

```gitattributes
# Enforce LF line endings in the repository
* text=auto eol=lf

# Mark specific file types as text and ensure LF endings
*.js      text eol=lf
*.ts      text eol=lf
*.json    text eol=lf
*.yml     text eol=lf
*.yaml    text eol=lf
*.md      text eol=lf
*.html    text eol=lf
*.css     text eol=lf
*.scss    text eol=lf
*.env     text eol=lf

# Binary files (never modify line endings)
*.png     binary
*.jpg     binary
*.jpeg    binary
*.gif     binary
*.ico     binary
*.pdf     binary
*.zip     binary
*.gz      binary
*.exe     binary
```

---

### ✅ Steps to apply it

1. Create a `.gitattributes` file in the root of your project with the content above.
2. Normalize existing files:

   ```bash
   git add --renormalize .
   git commit -m "Normalize line endings with .gitattributes"
   ```
3. Done — now Git will always store files with **LF** in the repo, while Windows can still check them out as CRLF if `core.autocrlf` is enabled.

---

👉 This is especially helpful when using **ESLint / Prettier**, since they often enforce `LF` and otherwise throw line-ending errors.

Do you also want me to give you a **matching Prettier + ESLint config** snippet to ensure your editor auto-fixes line endings to LF too?
