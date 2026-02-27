### **AionUI CSS Theme Generator (English Documentation)**

#### **Overview**

A specialized tool for AionUI that automatically derives a full set of CSS variables and component styles based on text descriptions or uploaded background images. It generates roughly 1,200 lines of CSS code and saves it as a `.css` file.

#### **⚠️ Critical Instruction for AI Agent**

Before performing any generation task, you **must** load the following files. **Do not fabricate CSS or omit lines from the template.**

1. `references/color-theory.md` (Color derivation logic)
2. `references/css-template.md` (Output template)

---

#### **Workflow**

**Step 1: Understand User Request**

* Identify style keywords (Cyberpunk, Retro-futurism, etc.).
* Identify background images (used for color inspiration only).
* Confirm mode preference (Light/Dark; default is both).

**Step 2: Color Palette Analysis**

* **With Image:** Extract the primary non-neutral color using image analysis tools.
* **Without Image:** Map the description to a palette using the style mapping table in `references/color-theory.md`.

**Step 3: Variable Derivation**

* Derive all AionUI variables (e.g., `--bg-1`, `--text-primary`).
* **Advanced Privilege:** You may bypass standard brightness limits for "Cyberpunk" or "Glassmorphism" styles.

**Step 4: CSS Generation**

* Fill the `references/css-template.md` placeholders with actual values.
* **Note:** Do **not** add `!important` manually (AionUI adds it automatically).
* **Note:** Do **not** write background image code. Place high-level effects (glows, blurs) in the `{{ADVANCED_EFFECTS_CSS}}` placeholder at the end.

**Step 5: Save and Present**

* Save the code to `~/Desktop/aion-theme-[style].css`.
* **Encoding:** Must use **UTF-8** and start with `@charset "UTF-8";`.

---

#### **Important Rules**

* **Background Images:** This skill **does not** handle background images. Users must upload them manually in **AionUI Settings → Theme**. AionUI will then automatically append the background image block to your CSS.
* **Encoding:** Ensure the file is UTF-8 to prevent garbled Chinese comments.
* **Compatibility:** Use the `data-theme` attribute for dark mode (do not use media queries).
* **Color Format:** Use Hex (`#rrggbb`) or `rgba()` for transparency.

#### **Output Format**

1. **Save File:** Path should be `~/Desktop/aion-theme-[style].css`.
2. **Explain Design:** Provide 3–5 sentences on color choice and overall vibe.
3. **Usage Instructions:** * Open AionUI → Settings → Theme → Custom CSS.
* Paste the file content.
* Upload the background image separately in theme settings if needed.
