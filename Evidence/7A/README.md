# Action 7A — Greenward: A New Crew

## User Story
As a new member of Sana Vey's garden crew, I want an illustrated offline guide so I can follow the current instructions when the network is down.

## Story
- Beginning: A new crew member arrives at Sana's garden.
- Problem: The new member finds an outdated instruction card and asks Sana before starting.
- Ending: Sana explains the current instructions and the first task.

## Prototype
[Open the PowerPoint prototype](Greenward-7A-Prototype-Updated.pptx)

| Slide | Array Index | Image |
| --- | --- | --- |
| 1 — Beginning | 0 | Assets/Images/01.jpg |
| 2 — Problem | 1 | Assets/Images/02.jpg |
| 3 — Ending | 2 | Assets/Images/03.jpg |

## How to Run
Open StoryGameApp/StoryGameApp.csproj from the repository in Visual Studio on Windows with the .NET 10 SDK and the .NET desktop development workload installed. Press F5 to run.

## Controls
- Next moves to the next slide.
- Back returns to the previous slide.
- Restart returns to slide 1.
- Back is disabled on slide 1.
- Next is disabled on slide 3.
- A missing image displays an error message instead of crashing.

## Evidence
This folder contains:
- Three-screen PowerPoint prototype
- Screenshots of slides 1, 2, and 3
- Starter first-run screenshot
- Whiteboard photo
- Discord peer-review screenshot

## Test Checklist
Mark each item after checking the actual result.

- [x ] All three slides show the correct text and images.
- [x ] Next and Back move to the correct slides.
- [x ] Restart returns to slide 1.
- [x ] Back is disabled on the first slide.
- [x ] Next is disabled on the last slide.
- [x ] A missing image is handled without crashing.
- [x ] A classmate compares the prototype with the app and traces one button click.

## Credits
The app uses the course-provided WPF starter.
The illustrations and PowerPoint prototype were created with assistance from AI:))