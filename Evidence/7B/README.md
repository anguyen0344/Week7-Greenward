# 7B – Screen Capture Checkpoint

## Features
Added Capture screen, Save PNG, and Clear to the existing WPF slideshow using CaptureService.cs.

## Test Results
- Save before Capture: disabled.
- Capture: preview appeared.
- Save PNG: saved story-capture.png and opened it successfully.
- Cancel Save: kept the preview and current slide.
- Clear: removed the preview and disabled Save PNG.
- Capture again: preview appeared again.
- Back, Next, and Restart: still worked.
- Capture, Save, Cancel, and Clear did not change the current slide.

## AI Check

Prompt: I am adding screen capture to a beginner WPF C# slideshow
app. Propose ONE test for Save/Cancel. Do not rewrite the project.
Name the file, method, input, output and result I should observe.
Use fictional data only.

Response:
File: StoryGameApp/MainWindow.xaml.cs
Method: SaveCaptureButton_Click
Input: On slide 2, capture the screen, click Save PNG, then Cancel.
Expected output: No new file is created. The preview remains,
and currentSlide stays unchanged.

Observed result: The preview remained, no new file was created,
and the app stayed on slide 2.
Decision: Keep the implementation because the test passed.
## Evidence
- capture-preview.png
- click save png evidence.png
- story-capture.png

## Credits
Used the course-provided capture helper and integration snippets.
ChatGPT helped explain the integration and suggest a test.