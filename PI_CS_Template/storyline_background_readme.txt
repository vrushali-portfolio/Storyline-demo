Storyline 360 – Custom Browser Background (Image & Responsive Setup)

Purpose:
This guide explains how to add and control a full-browser background (color or image)
in Articulate Storyline 360 published output, including responsive behavior for desktop,
tablet, and portrait modes.

Project Structure:
This project/
├── story.html
├── index_lms.html
├── story_content/
│   ├── background-img.png
│   ├── bg-landscape.png
│   ├── bg-portrait.png
├── html5/
│   └── data/
│       └── css/
│           └── output.min.css

Key Concept:
Storyline does NOT use <body> for the visible background.
Instead, the visible outer area is controlled by .cs-base.

Steps:
1. Add images to story_content/
2. Open html5/data/css/output.min.css
3. Add:

.cs-npnxnanbnsnfns00000000001.cs-base {
  background: #CBC2E0 url("../../../story_content/background-img.png") no-repeat center center !important;
  background-size: cover !important;
}

@media (max-width: 1024px) and (orientation: landscape) {
  .cs-npnxnanbnsnfns00000000001.cs-base {
    background: #CBC2E0 url("../../../story_content/bg-landscape.png") no-repeat center center !important;
    background-size: cover !important;
  }
}

@media (max-width: 1024px) and (orientation: portrait) {
  .cs-npnxnanbnsnfns00000000001.cs-base {
    background: #CBC2E0 url("../../../story_content/bg-portrait.png") no-repeat center center !important;
    background-size: cover !important;
  }
}

Notes:
- Republish overwrites CSS
- Use correct relative path ../../../story_content/
- Use background-size: cover
- Slides remain fixed size

Testing:
- Resize browser
- Rotate device
- Hard refresh (Ctrl + Shift + R)

Summary:
Use .cs-base to control the browser background and apply responsive images.
