---
name: Bug Report
about: Found a technical bug? Submit it here.
title: ''
labels: bug
assignees: Loop-Lab-Studio

---

IMPORTANT: Do not attach projects or `.setting` files to issues. 

Before submitting a bug report, please:
 
1. Exit Fusion and restart your device.
1. Fix red nodes - these usually indicate a typo in an `Expression` field.
1. Relink your `Transform` or other node to the tool's `Curve` link.
1. Double-check node wiring. 

If your project is complex, please perform a simplified test: 

1. Download the [test_fusion_comp.setting]().
1. Start a new project and add a new Fusion comp.
1. Switch to the Fusion page and drag `test_fusion_comp.setting` to the canvas.
1. Add the LoopLab tool to the canvas. 
1. Link one of the `Test_` nodes to the tool's `Curve` and test. 

To help expedite bug reports, please include:

- Your device's OS
- DaVinci Resolve version number
- The name of the tool (available as a label)
- Steps to reproduce the issue
- Screenshots or composted video demonstrating the issue
