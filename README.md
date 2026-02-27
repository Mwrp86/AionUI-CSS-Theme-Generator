**CSS Theme Generation Skill specifically designed for AionUI**
Automatically generates complete AionUI theme CSS code based on style descriptions or background images.

---

### ✨ Feature Highlights

| Feature | Description |
| --- | --- |
| **🎨 Intelligent Color Matching** | Automatically extracts primary tones from images or generates color schemes based on style descriptions like "Cyberpunk" or "Fresh Nature." |
| **🌓 Dual Mode Support** | Simultaneously generates two complete sets of styles: Light and Dark. |
| **📦 Ready-to-Use** | Generates approximately 700 lines of full CSS—just copy and paste to use. |
| **🖼️ Background Support** | Upload background images in AionUI theme settings; the CSS adapts automatically. |
| **🧠 Smart Decision Making** | Quickly determines monochromatic/bichromatic schemes, border radius, and special effects, with optional follow-up for detail preferences. |
| **🔄 Iterative Adjustments** | Supports quantitative tweaks like "make it a bit redder" or "make it brighter." |
| **📚 Advanced Techniques** | Supports special effects such as frosted glass (glassmorphism), neon glows, and pixel borders. |
| **📐 Specification Compliant** | Strictly follows AionUI variable naming and component structures. |

---

### Installation

Run the following commands in your terminal:

**macOS / Linux:**

```bash
git clone https://github.com/taekchef/aionui-css-theme-generator.git /tmp/css-theme-gen && \
cp -r /tmp/css-theme-gen/css-theme-generator ~/.aionui-config/skills/ && \
rm -rf /tmp/css-theme-gen

```

**Windows:**

```powershell
git clone https://github.com/taekchef/aionui-css-theme-generator.git %TEMP%\css-theme-gen
xcopy /E /I "%TEMP%\css-theme-gen\css-theme-generator" "%USERPROFILE%\.aionui-config\skills\"
rmdir /s /q "%TEMP%\css-theme-gen"

```

After installation, you can choose between two methods of use:

#### Method A: Direct Skill Usage (Requires Trigger Keywords)

Trigger the skill in any conversation using keywords such as:

* "Help me generate a theme"
* "Make a cyberpunk style theme"
* "Generate a theme using this image"
* **Pros:** Quick to start, no extra configuration needed.
* **Cons:** Requires remembering keywords; needs explicit requirements every time.

#### Method B: Create a Dedicated Assistant (Recommended ⭐)

Create a specialized "Theme Designer" assistant for more natural interactions:

1. **Step 1: Create a New Assistant in AionUI**
* Go to **Assistant Management** → **Create Assistant**.
* **Name:** Theme Designer
* **Description:** Specialized in generating AionUI CSS themes.


2. **Step 2: Configure Assistant Rules (Important!)**
* **Rule File Location:** `theme-designer-assistant-rule.md`
* **How to get it:** Check GitHub online or locate it in the root directory of your cloned repository.
* **Action:** Copy all content from the file and paste it into the assistant's **Rules** input box.


3. **Step 3: Link the Skill**
* In the assistant's skill configuration, check ✅ **css-theme-generator**.


4. **Step 4: Start Using**
* Switch to the "Theme Designer" assistant.
* Speak naturally: "Generate a cyberpunk theme" or upload an image and say "Match a theme to this."



---

### Usage

**Option 1: Image-Based Generation**

* "Help me generate a theme based on this image."
* "Make a theme using @/path/to/image.jpg."
* "Generate a Black Myth: Wukong style theme based on the background."

**Option 2: Description-Based Generation**

* "Help me generate a cyberpunk style theme."
* "Make a fresh and natural theme."
* "Generate a Dark Gothic CSS."

---

### Requirements

* **Recommended:** Python 3 (optional) for saving CSS files with UTF-8 encoding.
* **Optional (Image Analysis):** Requires an MCP tool (e.g., `mcp__4_5v_mcp__analyze_image`) for color extraction.

---

### Output & Application

**Output Path:** `~/Desktop/aion-theme-[style].css` (e.g., `aion-theme-cyberpunk.css`)

**Steps to Apply:**

1. **Generate:** Trigger the skill in AionUI.
2. **Locate:** Find the `.css` file on your desktop.
3. **Apply:** Open **AionUI → Settings → Theme**, click "Add," and paste the code into the **Custom CSS** box.
4. **Upload Image (Optional):** Upload your background image in the theme settings *after* pasting the CSS.

---

### Technical Details

**Reference Documents:**

* `SKILL.md`: Skill definitions and workflow.
* `theme-designer-assistant-rule.md`: Assistant rule file.
* `references/css-template.md`: Full AionUI CSS template structure.
* `references/color-theory.md`: Color derivation methodology.

**Included in Generated CSS:**

* ✅ Full CSS variable system (colors, spacing, radius, etc.).
* ✅ Light Mode (`:root`) and Dark Mode (`[data-theme='dark']`).
* ✅ All AionUI component styles (sidebars, bubbles, buttons, etc.).
* ✅ Detailed styles for Scrollbars, Tooltips, Modals, etc.
* ✅ Responsive and print styles.

**Encoding Note:**
Generated files use **UTF-8** with a `@charset "UTF-8";` declaration to ensure comments display correctly.

---

### FAQ

* **Q: Why isn't the background image appearing?**
* A: Ensure the correct order: paste the CSS first, then upload the image. If it persists, restart AionUI.


* **Q: Why is there garbled text (encoding issues) in the CSS?**
* A: The file includes a UTF-8 declaration; simply ensure your text editor saves/opens in UTF-8.


* **Q: Can I customize the colors?**
* A: Yes. The generated CSS is a standard text file; you can manually edit any value.



---

### License & Contribution

* **License:** MIT License
* **Contribution:** Issues and Pull Requests are welcome!
