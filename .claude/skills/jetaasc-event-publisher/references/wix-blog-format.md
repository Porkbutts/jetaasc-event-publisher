# Wix Blog Post Format

Ricos JSON structure for blog post rich content.

## Node Examples

### Image Node
```json
{
  "type": "IMAGE",
  "id": "img1",
  "nodes": [],
  "imageData": {
    "containerData": {
      "width": {"size": "CONTENT"},
      "alignment": "CENTER"
    },
    "image": {
      "src": {"id": "wix-media-file-id"},
      "width": 800,
      "height": 600
    },
    "altText": "Event flyer description"
  }
}
```

### Paragraph with Plain Text
```json
{
  "type": "PARAGRAPH",
  "id": "p1",
  "nodes": [
    {
      "type": "TEXT",
      "id": "t1",
      "textData": {
        "text": "Your text here",
        "decorations": []
      }
    }
  ],
  "paragraphData": {}
}
```

### Bold Text
```json
{
  "type": "TEXT",
  "id": "t1",
  "textData": {
    "text": "Bold text",
    "decorations": [{"type": "BOLD"}]
  }
}
```

### Italic Text
```json
{
  "type": "TEXT",
  "id": "t1",
  "textData": {
    "text": "Italic text",
    "decorations": [{"type": "ITALIC"}]
  }
}
```

### Link
```json
{
  "type": "TEXT",
  "id": "t1",
  "textData": {
    "text": "Click here",
    "decorations": [
      {
        "type": "LINK",
        "linkData": {
          "link": {"url": "https://example.com"}
        }
      }
    ]
  }
}
```

### Heading Node
```json
{
  "type": "HEADING",
  "id": "h1",
  "nodes": [
    {
      "type": "TEXT",
      "id": "t1",
      "textData": {
        "text": "Section Title",
        "decorations": []
      }
    }
  ],
  "headingData": {
    "level": 2
  }
}
```

### Empty Paragraph (Visual Break / Spacing)
To add visual spacing between sections, use an empty paragraph node with no text nodes:
```json
{
  "type": "PARAGRAPH",
  "id": "spacer1",
  "nodes": [],
  "paragraphData": {}
}
```

**Important:** Without empty paragraphs between sections, content will appear "squished" with no visual separation. Add empty paragraphs:
- After the image
- Between description paragraphs
- Before the What/When/Where/Cost section
- After the What/When/Where/Cost section (before closing text)

## Example: Complete Event Post

Category and tag IDs are in [platforms.md](platforms.md).

```json
{
  "draftPost": {
    "title": "JETAASC Shinenkai 2026",
    "categoryIds": ["<upcoming-category-id>"],
    "tagIds": ["<shinnenkai-tag-id>", "<other-tag-ids>"],
    "richContent": {
      "nodes": [
        {
          "type": "IMAGE",
          "id": "img1",
          "nodes": [],
          "imageData": {
            "containerData": {"width": {"size": "CONTENT"}, "alignment": "CENTER"},
            "image": {"src": {"id": "media-file-id"}, "width": 800, "height": 600},
            "altText": "JETAASC Shinenkai 2026 Event Flyer"
          }
        },
        {"type": "PARAGRAPH", "id": "spacer1", "nodes": [], "paragraphData": {}},
        {
          "type": "PARAGRAPH",
          "id": "p1",
          "nodes": [
            {"type": "TEXT", "id": "t1", "textData": {"text": "Join us for our annual New Year celebration!", "decorations": []}}
          ],
          "paragraphData": {}
        },
        {"type": "PARAGRAPH", "id": "spacer2", "nodes": [], "paragraphData": {}},
        {
          "type": "PARAGRAPH",
          "id": "p2",
          "nodes": [
            {"type": "TEXT", "id": "t2", "textData": {"text": "What: ", "decorations": [{"type": "BOLD"}]}},
            {"type": "TEXT", "id": "t3", "textData": {"text": "Shinenkai (New Year Party)", "decorations": []}}
          ],
          "paragraphData": {}
        },
        {
          "type": "PARAGRAPH",
          "id": "p3",
          "nodes": [
            {"type": "TEXT", "id": "t4", "textData": {"text": "When: ", "decorations": [{"type": "BOLD"}]}},
            {"type": "TEXT", "id": "t5", "textData": {"text": "Saturday, January 25, 2026 at 6:00 PM", "decorations": []}}
          ],
          "paragraphData": {}
        },
        {
          "type": "PARAGRAPH",
          "id": "p4",
          "nodes": [
            {"type": "TEXT", "id": "t6", "textData": {"text": "Where: ", "decorations": [{"type": "BOLD"}]}},
            {"type": "TEXT", "id": "t7", "textData": {"text": "Little Tokyo, Los Angeles", "decorations": []}}
          ],
          "paragraphData": {}
        },
        {
          "type": "PARAGRAPH",
          "id": "p5",
          "nodes": [
            {"type": "TEXT", "id": "t8", "textData": {"text": "Cost: ", "decorations": [{"type": "BOLD"}]}},
            {"type": "TEXT", "id": "t9", "textData": {"text": "$25 members / $30 non-members", "decorations": []}}
          ],
          "paragraphData": {}
        },
        {
          "type": "PARAGRAPH",
          "id": "p6",
          "nodes": [
            {"type": "TEXT", "id": "t10", "textData": {"text": "RSVP: ", "decorations": [{"type": "BOLD"}]}},
            {"type": "TEXT", "id": "t11", "textData": {"text": "Click here to register", "decorations": [{"type": "LINK", "linkData": {"link": {"url": "https://forms.google.com/..."}}}]}}
          ],
          "paragraphData": {}
        },
        {"type": "PARAGRAPH", "id": "spacer3", "nodes": [], "paragraphData": {}},
        {
          "type": "PARAGRAPH",
          "id": "p7",
          "nodes": [
            {"type": "TEXT", "id": "t12", "textData": {"text": "We hope to see you there!", "decorations": []}}
          ],
          "paragraphData": {}
        }
      ]
    }
  }
}
```
