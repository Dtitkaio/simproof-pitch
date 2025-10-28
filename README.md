# **Slides Generation by Claude Code × Marp**

A **template system** for efficiently creating **presentation slides with a unified design**, powered by **Claude Code** and **Marp**.

---

## 🧭 **Overview**

This repository provides **templates and tools** to quickly generate consistent, well-designed presentations using **Marp**.
You can automatically generate slides via **Claude Code** using structured Markdown input files.

---

## ⚙️ **Requirements**

* [Marp CLI](https://github.com/marp-team/marp-cli)
* Node.js (v14 or higher recommended)
* [Claude Code](https://claude.ai/code) – for automatic slide generation

---

## 🚀 **Installation**

```bash
# Install Marp CLI
npm install -g @marp-team/marp-cli

# Clone this repository
git clone [your-repo-url]
cd slides
```

---

## 💡 **Usage**

### **1️⃣ Create a New Slide Directory**

```bash
mkdir -p slides/YYYY-MM-DD-topic/{input,output,resources,themes}
```

---

### **2️⃣ Add Your Content**

Write your presentation outline inside:
`slides/YYYY-MM-DD-topic/input/`

Include:

* The main topic and talking points
* Related resources and links
* Duration and target audience

---

### **3️⃣ Generate Slides with Claude Code**

Run the following command in Claude Code:

```
/project:generate-slides slides/YYYY-MM-DD-topic/input/topic.md
```

Claude will generate slides automatically and save them to:
`slides/YYYY-MM-DD-topic/output/`

---

### **4️⃣ Preview and Export**

```bash
# Preview (using the common theme)
marp --preview slides/YYYY-MM-DD-topic/output/presentation.md --theme common/themes/theme.css

# Export to PDF (common theme)
marp slides/YYYY-MM-DD-topic/output/presentation.md --pdf --theme common/themes/theme.css --allow-local-files

# Export to PDF (light theme)
marp slides/YYYY-MM-DD-topic/output/presentation.md --pdf --theme common/themes/theme-light.css --allow-local-files

# Export to HTML (common theme)
marp slides/YYYY-MM-DD-topic/output/presentation.md --html --theme common/themes/theme.css --allow-local-files
```

---

## 📂 **Directory Structure**

```
.
├── .claude/                     # Claude Code settings
│   └── commands/                # Custom commands
├── common/                      # Shared resources
│   ├── themes/                  # Common themes
│   │   ├── theme.css            # Dark theme
│   │   └── theme-light.css      # Light theme
│   └── images/                  # Shared image assets
│       ├── architecture-containers.png
│       └── extension-install.png
├── slides/                      # Each presentation directory
│   ├── 2025-07-27-devcontainer/ # Example: “Dev Container” presentation
│   │   ├── input/               # Input files
│   │   ├── output/              # Generated slides
│   │   ├── resources/           # Slide-specific resources
│   │   └── themes/              # Slide-specific themes (optional)
│   └── 2025-10-25-study-session/ # Example: Study session slides
│       ├── input/
│       ├── output/
│       ├── resources/
│       └── themes/
├── templates/                   # Templates
│   └── slide_template.md        # Base slide template
├── CLAUDE.md                    # Guide for Claude Code usage
└── README.md
```

---

## 🎨 **Customization**

### **Common Themes**

Themes stored in `common/themes/` can be applied as follows:

```bash
marp slides/YYYY-MM-DD-topic/output/presentation.md --theme common/themes/theme.css --pdf --allow-local-files
```

---

### **Slide-Specific Theme**

If you want a unique look for specific slides, add a custom theme under:
`slides/YYYY-MM-DD-topic/themes/custom.css`

Example:

```css
/* slides/YYYY-MM-DD-topic/themes/custom.css */
@theme custom {
  @import 'default';

  section {
    background-color: #f5f5f5;
    color: #333;
  }

  h1 {
    color: #0066cc;
  }
}
```

---

### **Image Assets**

#### Shared Images

Images used across multiple presentations should be stored in `common/images/`:

```markdown
![bg](../../common/images/background.png)
![logo](../../common/images/logo.png)
```

#### Slide-Specific Images

Images unique to one presentation should be stored in that slide’s `resources/` directory:

```markdown
![diagram](resources/diagram.png)
```

---

## 🧠 **Best Practices**

1. **Naming Convention:**
   Use `YYYY-MM-DD-topic` for directories and `YYYYMMDD_title.md` for files.
2. **Version Control:**
   Commit important presentations to Git for backup and collaboration.
3. **Image Optimization:**
   Compress images to a reasonable size for faster builds.
4. **Use Templates:**
   Always start from `templates/slide_template.md`.
5. **Shared Resources:**
   Keep reusable assets in the `common/` directory.
6. **Slide-Specific Resources:**
   Store unique materials within each slide’s own directory.

---

## 🧩 **Troubleshooting**

### **Marp CLI Not Working**

```bash
# Check Node.js version
node --version

# Reinstall Marp CLI
npm uninstall -g @marp-team/marp-cli
npm install -g @marp-team/marp-cli
```

### **PDF Export Errors**

* Ensure Chromium dependencies are installed
* Avoid using special or non-ASCII characters in file paths

---

## 📜 **License**

[MIT License](LICENSE)

---

## 🔗 **Related Links**

* [Marp Official Documentation](https://marpit.marp.app/)
* [Marp CLI](https://github.com/marp-team/marp-cli)
* [Claude Code](https://claude.ai/code)