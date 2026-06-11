---
name: update-github-info
description: Draft website updates for Mona's GitHub Info site from official GitHub sources.
on:
  workflow_dispatch:
  schedule:
    - cron: '17 9 * * *'
safe-outputs:
  create-pull-request:
    title-prefix: "[mona] "
    draft: true
    fallback-as-issue: false
tools:
  edit:
  web-fetch:
network:
  allowed:
    - github.com
    - github.blog
---

# Update Mona's GitHub Info website

Read notes/mona-notes.md before making any changes.

Use these sources:
- notes/mona-notes.md
- GitHub Blog: https://github.blog/latest/
- GitHub Changelog: https://github.blog/changelog/

Update site/content/github-info.md with concise, practical updates for readers.
When a change comes from the GitHub Blog or GitHub Changelog, mention the source clearly.

Use edit access to update the content file, then open a pull request for Mona to review.
Do not write directly to main. Rely on safe-outputs with create-pull-request so the workflow can propose changes safely through a pull request.