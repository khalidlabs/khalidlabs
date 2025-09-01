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


git add content/posts/project-adaptive-control.md

## 🔍 **Why the First Post Appears Differently**

### **First Post (`project-adaptive-control.md`):**
- ✅ Has `featured: true` - This makes it appear as a featured post
- ✅ Has `imageUrl` - This adds a featured image
- ✅ Has `slug` - Custom URL slug
- ✅ Has `technologies` - Additional metadata

### **Other Two Posts:**
- ❌ No `featured: true` - They appear as regular posts
- ❌ No `imageUrl` - No featured image
- ❌ Different front matter structure

## ️ **How to Fix This**

You have a few options:

### **Option 1: Make all posts consistent (recommended)**
Add the same front matter to all posts:

```yaml
---
title: "Your Title"
date: 2025-XX-XX
draft: false
description: "Your description"
tags: ["tag1", "tag2"]
categories: ["category"]
featured: true  # Add this to make them all featured
---
```

### **Option 2: Remove featured status from first post**
Remove `featured: true` from the first post to make them all appear the same.

### **Option 3: Add featured images to all posts**
Add `imageUrl` to the other posts to give them featured images too.

Would you like me to help you standardize the front matter across all your posts?
