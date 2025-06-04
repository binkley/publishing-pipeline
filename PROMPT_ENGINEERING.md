> You may need to refresh to a new AI chat session when you observe it looping
> or repeating mistakes.

# Session Starter Checklist for Publishing Pipeline

This document helps anyone resuming work on this project—including future
you—quickly get up to speed in a new session or when handing off work to a
collaborator.

---

## ✅ 1. Set Context Briefly

Start by describing:
- What the project is
- What stage you're at
- What you want help with next

**Example:**
> I'm working on a GCP Cloud Function that converts Markdown to PDF using
> Pandoc.
> It's part of a demo pipeline that ingests files and stores PDFs in a bucket.
> Right now, I want help fixing a Docker build failure.

---

## ✅ 2. Paste Recent Git History (Optional but Recommended)

This helps summarize recent changes:

```bash
git log --pretty=format:'%h%n%ad%n%s%n%b%n---' --date=short --no-merges | tee log
```

(You can upload the tee'd `log` file to your session.)

---

## ✅ 3. Attach Key Files or Errors

Include:
- `Dockerfile`
- `main.py`
- Build logs (`rebuild.log`, `err`, etc.)

Label them clearly when uploading or pasting into the session.

---

## ✅ 4. Remind About Project Goals

If needed, provide:
- The GitHub repo URL
- Intended outcome (e.g., “minimal PDF publishing pipeline”)
- Audience (e.g., stakeholders, clients)

**Example:**
> GitHub: https://github.com/binkley/publishing-pipeline  
> Goal: Demo project using GCP to convert Markdown to PDF via `pandoc`  
> Audience: Team leads or clients evaluating my architecture recommendations

---

## 🔁 Rule of Three Reminder

1. **Make it work**
2. **Make it right**
3. *(Optional)* **Make it fast**

Stick to this to keep progress simple and iterative.
