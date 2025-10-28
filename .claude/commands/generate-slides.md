# **Generate Marp Slides from Input**

Generate Marp presentation slides automatically from an input file.

## 🧩 **Execution Steps**

1. **Read Input File**
* Read the input file specified by `$ARGUMENTS`
  (Default: the most recent file in the `input/` directory)
* Extract key elements such as:
  * Title
  * Purpose
  * Target audience
  * Agenda
* If the input file contains a URL, fetch the content from that URL and include it in the input context.

2. **Prepare the Template**
* Copy `YYYYMMDD_template.md` to create a new file.
* File name format:```YYYYMMDD_[Title].md```(Use the same name as the input file whenever possible.)

3. **Generate Slides**
* Place the extracted content into the appropriate sections of the template.
* Add code blocks or Mermaid diagrams for technical content.
* Follow the rules defined in **CLAUDE.md**:
  * One main message per slide
  * Maximum title length: **30 characters**
  * The **header** must include the full presentation title
  * Maximum **40 characters per line**, **400 characters / 12 lines per slide**
  * **3–5 bullet points** per list

4. **Apply Styling**
* Specify the theme in the frontmatter:```yamltheme: themes/theme```
* Reference shared images from the `.images/` directory.

5. **Output**
* Save the generated file into the `output/` directory.
* File name should match the input file.
* Display a command suggestion for previewing the slides.

## 💡 **Example Usage**

```bash
/generate-slides input/my-presentation-outline.md
```

If no arguments are provided, the latest file in the `input/` directory will be used automatically.