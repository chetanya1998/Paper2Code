# Paper2Code

This project explores automated extraction of code from research papers. See [UI_UX_Flow.md](UI_UX_Flow.md) for the proposed user interface and output design.

A minimal web prototype is included using [Flask](https://flask.palletsprojects.com/). To run the app locally:

```bash
pip install flask PyPDF2
python app.py
```

Then visit `http://localhost:5000` to upload a PDF and view the generated placeholders.
