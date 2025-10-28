# **Claude Code Slide Creation Guide**

This document provides guidelines for efficiently creating **Marp slides** using **Claude Code**.

---

## 🧭 **Project Overview**

This repository is a **template system** designed to help you quickly create presentation slides with a **consistent design**.

---

## 📁 **Directory Structure**

```
├── .claude/commands/        # Custom Claude Code commands
├── common/                  # Shared resources
│   ├── themes/              # Common themes (theme.css, theme-light.css)
│   └── images/              # Common image assets
├── slides/                  # Individual slide directories
│   ├── YYYY-MM-DD-topic/    # Each presentation
│   │   ├── input/           # Input files (outline, requirements)
│   │   ├── output/          # Generated slides (.md, .pdf, .html)
│   │   ├── resources/       # Reference materials (articles, blogs)
│   │   └── themes/          # Slide-specific themes (optional)
│   └── ...
├── templates/               # Templates
│   └── slide_template.md    # Base slide template
├── CLAUDE.md                # Configuration and rules for Claude Code
└── README.md
```

---

## 🧱 **Slide Creation Workflow**

### **1️⃣ Create a New Slide Directory**

```bash
mkdir -p slides/YYYY-MM-DD-topic/{input,output,resources,themes}
```

---

### **2️⃣ Prepare Input Files**

Place a Markdown file in `slides/YYYY-MM-DD-topic/input/` containing:

* Presentation title
* Purpose and target audience
* Key points and agenda
* Required visuals or data

---

### **3️⃣ Generate Slides**

1. Use `templates/slide_template.md` as a base
2. Parse input content
3. Fill each section appropriately
4. Add Mermaid diagrams or code blocks as needed
5. Save output files in `slides/YYYY-MM-DD-topic/output/`

---

### **4️⃣ Styling**

* Use `common/themes/theme.css` or `theme-light.css` for standard design
* For custom styles, place theme files in `slides/YYYY-MM-DD-topic/themes/`
* Reference shared images from `common/images/`
* Place slide-specific images in `slides/YYYY-MM-DD-topic/resources/`
* Maintain visual and layout consistency across all slides

---

## 🧩 **Key Marp Syntax**

### **Basic Settings**

```yaml
---
marp: true
theme: custom       # Use custom theme
paginate: true
header: '<Title>'
footer: 'Footer text'
---
```

---

### **Slide Separation**

Use `---` to start a new slide.

---

### **Images**

```markdown
![bg](path/to/image.png)           # Background image
![bg left](path/to/image.png)      # Left-side background
![w:500](path/to/image.png)        # Set image width
```

---

### **Layouts**

```markdown
<!-- _class: lead -->   # Centered layout
<!-- _class: split -->  # Split layout (requires custom CSS)
```

---

## 🧠 **Best Practices for Content Creation**

### **Structural Consistency**

* Maintain a consistent slide structure across all decks
* Follow the flow: *Agenda → Main Content → Summary*

---

### **Visual Elements**

* Use diagrams (Mermaid), tables, and charts appropriately
* Apply syntax highlighting to code blocks
* Reference shared images from `common/images/`
* Store slide-specific visuals in each slide’s `resources/` folder

---

### **Text Principles**

* One key message per slide
* Keep bullet points to 3–5 items
* Use visuals for technical explanations
* Title: up to 30 characters
* Body: up to 40 characters per line
* Max ~400 characters or 12 lines per slide

---

### **Notes for Presentations**

* Maintain large, readable font sizes (min. 24pt)
* Ensure good line spacing and margins
* Ensure the slide header and title do not overlap.
* Adjust spacing so that no bullet points go below the footer.
* Check margins and padding for a clean layout.

---

## ✅ **Checklist for Slide Generation**

1. [ ] Copy the template file and rename it with the current date
2. [ ] Reflect all input file content appropriately
3. [ ] Add necessary diagrams and images
4. [ ] Update header and footer information
5. [ ] Review logical flow and consistency
6. [ ] Verify PDF export and formatting

---

## 💻 **Common Marp Commands**

```bash
# Preview (using common theme)
marp --preview slides/YYYY-MM-DD-topic/output/presentation.md --theme common/themes/theme.css

# Export to PDF (using common theme)
marp slides/YYYY-MM-DD-topic/output/presentation.md --pdf --theme common/themes/theme.css --allow-local-files

# Export to PDF (using light theme)
marp slides/YYYY-MM-DD-topic/output/presentation.md --pdf --theme common/themes/theme-light.css --allow-local-files

# Export with slide-specific theme
marp slides/YYYY-MM-DD-topic/output/presentation.md --pdf --theme slides/YYYY-MM-DD-topic/themes/custom.css --allow-local-files
```

---

## 🧩 **Troubleshooting**

### 🖼️ Image Not Displaying

* Check if the relative path is correct
* Verify that the image file actually exists

### 📐 Layout Issues

* Check for CSS conflicts in custom themes
* Ensure correct Marp syntax usage

### 🧾 PDF Export Errors

* Make sure Chromium is installed
* Avoid Japanese characters in file paths
