# Quick Blog Post Guide

## Add a New Post

### 1. Create Post
```bash
hugo new content posts/your-title.md
```

### 2. Edit Post
Open `content/posts/your-title.md` and update:
```yaml
---
draft: false
title: 'Your Title'
description: 'Brief description'
tags: ['tag1', 'tag2']
---
```

Add your content below using Markdown.

### 3. Preview
```bash
hugo server --buildDrafts
```
Visit `http://localhost:1313`

### 4. Publish
```bash
git add content/posts/your-title.md
git commit -m "Add post"
git push
```

Done! Post will be live at `https://khalidlabs.github.io` in 2-5 minutes.


git add . && git commit -m "Update" && git push
