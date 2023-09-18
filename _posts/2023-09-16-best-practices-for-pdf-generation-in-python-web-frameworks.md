---
layout: post
title: "Best Practices for PDF generation in Python backends"
---

PDF is a good way to create invoices, reports or tickets. Threfore, We need to create PDF files in the web apps. However, There are multiple ways to do this.

In the first way, It is possible to create some labels and texts in the memory space. Then, Use a library which creates an PDF from it. It is strictly connected to the library and then it makes harder to replace. Instead of this, I would like to have an HTML item for the printed object. Why? Because HTML is widely accepted and valid within different browsers and packages. Then, Returning to the PDF with libraries.

The tool, WeasyPrint.

```python
>> pip install weasyprint
```

