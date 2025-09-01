# Blog Post Guide - KhalidLabs

This guide walks you through the complete process of adding a new blog post to your Hugo site, from initial setup to deployment.

## Prerequisites

- Hugo installed on your system
- Git configured with your GitHub credentials
- Access to the `khalidlabs.github.io` repository

## Initial Setup (One-time only)

### 1. Clone the Repository
```bash
git clone https://github.com/khalidlabs/khalidlabs.github.io.git
cd khalidlabs.github.io
```

### 2. Verify Hugo Installation
```bash
hugo version
```
You should see Hugo version information. If not installed, follow the [Hugo installation guide](https://gohugo.io/installation/).

## Adding a New Blog Post

### Step 1: Create the Post File

Use Hugo's content creation command:
```bash
hugo new content posts/your-post-title.md
```

**Examples:**
```bash
hugo new content posts/getting-started-with-hugo.md
hugo new content posts/my-project-update.md
hugo new content posts/2024-01-15-weekly-notes.md
```

### Step 2: Edit the Post Front Matter

The created file will have basic front matter. Edit it to include all necessary metadata:

```yaml
---
date: '2025-01-15T10:00:00+03:00'
draft: false
title: 'Your Post Title'
description: 'A brief description of your post for SEO and previews'
tags: ['tag1', 'tag2', 'tag3']
categories: ['category1', 'category2']
author: 'Your Name'
image: '/images/your-featured-image.jpg'  # Optional
---
```

**Front Matter Fields Explained:**
- `date`: Publication date and time
- `draft`: Set to `false` to publish, `true` to keep as draft
- `title`: The main title of your post
- `description`: Brief description for search engines and social sharing
- `tags`: Array of tags for categorization and filtering
- `categories`: Array of categories for broader organization
- `author`: Author name (optional)
- `image`: Path to featured image (optional)

### Step 3: Write Your Content

Add your content below the front matter using Markdown:

```markdown
# Main Heading

Your introduction paragraph goes here.

## Subheading

More content with **bold text**, *italic text*, and [links](https://example.com).

### Code Examples

```python
def hello_world():
    print("Hello, World!")
```

### Lists

- Item 1
- Item 2
- Item 3

### Blockquotes

> This is a blockquote for important information.

### Images

![Alt text](/images/your-image.jpg)

### Tables

| Column 1 | Column 2 | Column 3 |
|----------|----------|----------|
| Data 1   | Data 2   | Data 3   |
| Data 4   | Data 5   | Data 6   |
```

### Step 4: Preview Your Post Locally

Start the Hugo development server:
```bash
hugo server --buildDrafts
```

**Server Options:**
- `--buildDrafts`: Include draft posts in preview
- `--disableFastRender`: Full rebuild on changes (slower but more reliable)
- `--bind 0.0.0.0`: Make server accessible from other devices

Visit `http://localhost:1313` to preview your site.

### Step 5: Test Your Post

1. Navigate to your post URL: `http://localhost:1313/posts/your-post-title/`
2. Check that all formatting renders correctly
3. Verify images and links work
4. Test responsive design on different screen sizes
5. Check that tags and categories are working

### Step 6: Commit and Push to GitHub

#### Stage Your Changes
```bash
git add content/posts/your-post-title.md
```

#### Commit with a Descriptive Message
```bash
git commit -m "Add new post: Your Post Title

- Brief description of what the post covers
- Any important notes about the content"
```

#### Push to GitHub
```bash
git push origin main
```

### Step 7: Verify Deployment

1. Wait 2-5 minutes for GitHub Pages to build
2. Visit `https://khalidlabs.github.io` to see your live site
3. Check that your new post appears in the posts list
4. Verify all links and images work on the live site

## Advanced Features

### Adding Images

1. Place images in the `static/images/` directory
2. Reference them in your post: `![Alt text](/images/filename.jpg)`
3. Use descriptive filenames and alt text for accessibility

### Using Shortcodes

Hugo supports custom shortcodes for enhanced functionality:

```markdown
{{< figure src="/images/image.jpg" caption="Image caption" >}}
{{< highlight python >}}
def code_example():
    return "Hello World"
{{< /highlight >}}
```

### Draft Posts

To create a draft post that won't be published:
```bash
hugo new content posts/draft-post.md
```

The front matter will have `draft: true` by default. Keep this setting until ready to publish.

### Scheduled Posts

Set a future date in the front matter to schedule a post:
```yaml
date: '2025-02-01T10:00:00+03:00'
```

## Troubleshooting

### Common Issues

1. **Post not appearing**: Check that `draft: false` in front matter
2. **Images not loading**: Verify path starts with `/` and image exists in `static/`
3. **Build errors**: Check Hugo syntax and front matter formatting
4. **Git push fails**: Ensure you have write access to the repository

### Useful Commands

```bash
# Check Hugo syntax
hugo --gc --minify

# Build site for production
hugo

# Check git status
git status

# View recent commits
git log --oneline -10

# Pull latest changes
git pull origin main
```

## Best Practices

1. **Use descriptive titles** that clearly indicate the post content
2. **Include relevant tags** for better discoverability
3. **Write engaging descriptions** for social sharing
4. **Use proper Markdown formatting** for readability
5. **Test locally** before pushing to production
6. **Commit frequently** with meaningful commit messages
7. **Keep images optimized** for web (compress if needed)

## Resources

- [Hugo Documentation](https://gohugo.io/documentation/)
- [Markdown Guide](https://www.markdownguide.org/)
- [PaperMod Theme Documentation](https://github.com/adityatelange/hugo-PaperMod)
- [GitHub Pages Documentation](https://pages.github.com/)

---

**Happy blogging! 🚀**
