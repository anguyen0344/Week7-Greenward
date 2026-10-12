# Greenward: A New Crew

CS110 Week 7 WPF story app by An Nguyen

## Grading Guide — Week 7 Requirements R1–R6

Please review Evidence/7A and Evidence/7B as part of this Week 7 final submission. These Action folders contain the planning, implementation, testing, and AI evidence reused for the weekly requirements. Final packaging and handoff evidence is in Evidence/Final.

| Requirement | Evidence to review |
| --- | --- |
| R1 — Plan for one reader | [7A planning and user story](Evidence/7A/README.md), [whiteboard](Evidence/7A/Whiteboard.jpg), and [visual prototype](Evidence/7A/Greenward-7A-Prototype-Updated.pptx). |
| R2 — Build and record 7A | [WPF source](StoryGameApp), [7A test record](Evidence/7A/README.md), screenshots of [slide 1](Evidence/7A/slide-1.png), [slide 2](Evidence/7A/slide-2.png), [slide 3](Evidence/7A/slide-3.png), and [Discord evidence](Evidence/7A/Discord.jpg). |
| R3 — Add screen capture | [Capture helper](StoryGameApp/CaptureService.cs), [event handlers](StoryGameApp/MainWindow.xaml.cs), [capture preview](Evidence/7B/capture-preview.png), [saved PNG](Evidence/7B/story-capture.png), and [capture test results](Evidence/7B/README.md). |
| R4 — Test and record 7B | [7B test and AI record](Evidence/7B/README.md), [AI screenshot](Evidence/7B/AI-suggestion.jpg), [lesson notes](Evidence/7B/lesson-notes.txt), [whiteboard 1](Evidence/7B/whiteboard1.jpg), [whiteboard 2](Evidence/7B/whiteboard2.jpg), and [Discord evidence](Evidence/7B/discord.jpg). |
| R5 — Explain and package | Setup, controls, code map, tests, credits, and limitations in this README; [editable tutorial](Evidence/Final/Greenward-Tutorial.pptx), [PDF tutorial](Evidence/Final/Greenward-Tutorial.pdf), [Release-build evidence](Evidence/Final/release-build.png), [source ZIP](Evidence/Final/Week7-Greenward-Final.zip), [peer test record](Evidence/Final/handoff-test.md), and [peer screenshots](Evidence/Final/peer-check-screenshots). |
| R6 — Submit one GitHub URL | [Course route receipt](Evidence/Final/route-receipt.html) and [handoff/access record](Evidence/Final/handoff-test.md). The repository URL for Canvas is https://github.com/anguyen0344/Week7-Greenward. |

## Intended User and Purpose

As a new member of Sana Vey's garden crew, I want an illustrated offline guide so I can follow the current instructions when the network is down.

The three-slide story introduces the crew, shows an outdated instruction card, and ends with Sana explaining the current instructions. Screen capture lets the user keep visible evidence as a PNG.

## Setup and Run

Requirements: Windows, Visual Studio with the .NET desktop development workload, and the .NET 10 SDK. This is a source package that needs these tools to build and run.

1. Clone this repository or extract the source ZIP to a new folder.
2. Open `StoryGameApp/StoryGameApp.csproj` in Visual Studio.
3. Select **Release** in the configuration dropdown.
4. Choose **Build > Build Solution** and confirm that the build succeeds.
5. Choose **Debug > Start Without Debugging** (Ctrl+F5).
6. Put the app on the primary display before capturing the screen.

Alternatively, from the extracted repository folder on Windows:

```powershell
dotnet build StoryGameApp/StoryGameApp.csproj -c Release
dotnet run --project StoryGameApp/StoryGameApp.csproj -c Release
```

Keep `Assets/Images/01.jpg`, `02.jpg`, and `03.jpg` in the project. Their project settings copy them to the build output.

## Controls

|Control|Behavior|
|-|-|
|Next|Moves forward. Disabled on slide 3.|
|Back|Moves backward. Disabled on slide 1.|
|Restart|Returns to slide 1.|
|Capture screen|Captures the entire primary display and shows a preview.|
|Save PNG|Saves the captured image. Disabled before capture and after Clear.|
|Cancel in Save dialog|Creates no new file and keeps the preview.|
|Clear|Removes the stored capture and preview, and disables Save and Clear.|

Capture, Save, Cancel and Clear leave the story position unchanged. If an image is missing, the app shows an explanatory status message instead of crashing.

## Code and Evidence Map

|Path|Purpose|
|-|-|
|`StoryGameApp/StoryGameApp.csproj`|.NET 10 Windows project and image-copy settings|
|`StoryGameApp/MainWindow.xaml`|Story UI, navigation and capture controls|
|`StoryGameApp/MainWindow.xaml.cs`|Slide data, ShowSlide, navigation and capture handlers|
|`StoryGameApp/CaptureService.cs`|Captures the primary display and returns BitmapSource|
|`StoryGameApp/App.xaml` and `App.xaml.cs`|WPF application startup|
|`StoryGameApp/Assets/Images`|Illustrations for the three story slides|
|[Evidence/7A](Evidence/7A)|Prototype, story screenshots, planning and Discord evidence|
|[Evidence/7B](Evidence/7B)|Capture screenshots, saved PNG, notes, whiteboard and AI test|
|[Evidence/Final](Evidence/Final)|Tutorial slides, PDF and final handoff records|

## Test Results

These results come from the student's recorded 7A/7B checks, not an independent package test.

|Test|Recorded result|
|-|-|
|Correct text and images on all three slides|Pass|
|Back, Next, Restart and safe first/last slide|Pass|
|Missing-image status feedback|Pass|
|Save disabled before Capture|Pass|
|Capture preview and saved PNG reopened|Pass|
|Cancel keeps preview and slide 1 without a new file|Pass|
|Clear removes preview and disables Save|Pass|
|Capture again works|Pass|
|Capture actions preserve currentSlide|Pass|
|Final Release build|Pass- Release build: 1 succeeded, 0 failed. Evidence: Evidence/Final/release-build.png|
|Another person extracts, builds and runs the source ZIP|PASS — See Evidence/Final/handoff-test.md.|

The AI check tested cancelling Save after capturing slide 1 (currentSlide = 0). The preview and slide position remained unchanged, and no new file was created. Decision: Keep. See Evidence/7B.

## Tutorial

* [Editable tutorial](Evidence/Final/Greenward-Tutorial.pptx)
* [PDF tutorial](Evidence/Final/Greenward-Tutorial.pdf)

The tutorial covers the user story, story flow, prototype and app comparison, one method walkthrough, capture evidence, tests and contributions.

## Credits and Contributions

* Nguyen Thanh An integrated the starter and capture snippets, added the story assets, ran the recorded checks and collected evidence.
* The CS110 course supplied the WPF starter, CaptureService helper and integration snippets.
* ChatGPT helped generate the illustrations (`01.jpg`, `02.jpg`, `03.jpg`) and 7A prototype, explain integration, propose the Cancel test and prepare final documentation/tutorial.
* Peer/Discord evidence is in the Action folders. Add actual peer feedback and the independent package-test result to the final handoff record.

## Limitations and Next Step

The app requires Windows and .NET 10. It captures the entire primary display, including other visible windows. It has a linear three-slide story. Sound and branching are optional and omitted.

Next: submit the tested repository URL through Canvas.
A later improvement could capture only the app window.

## Source Package

The ZIP contains the source project, Assets, README, tutorial and evidence. It omits `bin`, `obj`, `.vs`, Git history and other ZIP files. Keep it under 100 MB. After changing any included file, regenerate the ZIP and test the updated package.

