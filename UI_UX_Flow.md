# Paper2Code — UI/UX Flow & Output Blueprint

## 1. User Journey: Step by Step

### A. Home / Landing Page
- **Header**: App name/logo "Paper2Code" and short tagline "Turn research papers into working code." 
- **Call to Action**: Central "Upload your research paper (PDF)" box/button.
- **Supported models**: display tags such as "Powered by Gemini, DeepSeek, Ollama".
- **Optional**: Info icon for "How it works".

### B. PDF Upload
1. User clicks *Upload*, selects a PDF from the device.
2. Show progress indicator or spinner "Uploading…".
3. On errors (file too large or wrong format) display a clear message.
4. On success, move to the processing stepper.

### C. Processing State (Stepper Progress Flow)
- **Visual stepper** showing:
  1. PDF Uploaded
  2. Text Extracted
  3. Methodology Identified
  4. Pseudocode Generated
  5. Python Code Generated
  6. Test Data Created
  7. Results Ready!
- Highlight the active step with a spinner, mark completed steps with a check.
- Optionally show real-time logs or "AI is thinking…" animations.

### D. Results Display (Tabbed Output)
Once the LLM finishes, show four tabs:
1. **Methodology** – summarized in plain language with a copy button.
2. **Pseudocode** – numbered steps, clear indentation, copy button.
3. **Python Code** – syntax-highlighted, copy and download button.
4. **Test Data & Output** – test code with optional sample output, copy button.

### E. Actions/Enhancements
- **Download All** sections as a Notebook, Markdown, or ZIP.
- **Retry** with optional prompt tweak.
- **Switch LLM** backend.
- **New Upload** to restart.
- **Feedback** widget for usefulness.

### F. Error/Edge Cases
- PDF too short/unreadable: "Could not extract sufficient text."
- LLM API issues: "Provider overloaded. Please try again later." 
- Section not found: tab displays "Section not generated—try regenerating or check your PDF."

## 2. Detailed UI Layout
### A. Desktop Web Example
```
+----------------------------------------------------------+
| Paper2Code   [logo]                          [About]     |
+----------------------------------------------------------+
|    "Turn research papers into working code."             |
|                                                          |
|  [Upload PDF]                                            |
|   (or drag & drop)                                       |
|                                                          |
|   [ Model: Gemini ▼ ]   [Try Demo PDF]                   |
|----------------------------------------------------------|
|  (Stepper: 1..2..3..4..5..6..7..)                        |
|----------------------------------------------------------|
|  [Tab: Methodology] [Tab: Pseudocode] [Tab: Code] [Tab: Test Data]   |
|                                                          |
|   [Code block / text output]                             |
|   [Copy]    [Download]                                   |
|----------------------------------------------------------|
|  [New Upload]         [Feedback]                         |
+----------------------------------------------------------+
```

### B. Mobile/Tablet
- Tabs become collapsible accordion sections.
- Sticky upload or "new" button.
- Progress steps shown as a vertical stack.

## 3. Output Examples at Each Stage
| Stage | Output Example |
|-------|----------------|
| Methodology | "This paper introduces a novel transformer-based architecture for ..." |
| Pseudocode | `1. Initialize weights\n2. For each epoch:\n  a. Forward pass\n  b. Compute loss\n  c. Backprop and update weights` |
| Python Code | `import torch\ndef train(X, y):\n    ...` |
| Test Data | `# Example usage\nX_test = ...\nmodel.predict(X_test)\nOutput:\n[0.7, 0.2, 0.8]` |

## 4. User Experience Enhancements
- Optimistic UI placeholders while generating.
- Progressive disclosure for advanced settings.
- Accessibility support: keyboard navigation, screen reader labels.
- Dark mode theming.

## 5. Best Practices & Future Proofing
- Never expose API keys in the browser. Sanitize uploads.
- Provide a feedback loop for failed generations.
- Design modularly to add more models or output formats.

## 6. Complete Flow
1. Visit site → Welcome → Upload PDF.
2. Stepper shows progress: "Extracting…", "Generating code…".
3. Tabs fill with Methodology, Pseudocode, Python, Test Data.
4. User can copy, download, or run the code.
5. Errors are shown inline.
6. User can start over with a new paper or model.

