# Seongmin Hwang

**English** · [한국어](./README.ko.md)

I look for where people get stuck, turn what I learn into requirements a system can follow, and test what we build against real scenarios.

## Tech Stack

**Languages**  
<img src="assets/stack-languages.svg" alt="Python, C, Java, TypeScript, Kotlin">

**Services & Data**  
<img src="assets/stack-api-pipelines.svg" alt="Django, SQL, FastAPI">

**AI & Media**  
<img src="assets/stack-ai-data.svg" alt="LangGraph, Chroma, FFmpeg">

**Apps & Integration**  
<img src="assets/stack-web-desktop.svg" alt="Next.js, React, Electron, SSE, WebSocket">

## Projects

### HAMA · Where should AI pause for human review?

In a two-person capstone, I designed and implemented **how users review the AI's research plan and decide whether to place a simulated order**. We explored five types of review and focused the final demo on two points where the user could make a specific decision. I worked with my teammate on the API contract for progress, approvals, edits, and rejections, then checked the full sequence from request to result against actual server responses.

[Presentation video](https://www.youtube.com/watch?v=WFqmJOUc1qU&t=95s) · [Frontend code](https://github.com/HAMA-team/HAMA-frontend-v2) · Silver Award, 2025 Capstone Design Showcase

<details>
<summary><b>See the team's agent architecture</b></summary>

From our final capstone poster. The LangGraph supervisor routes requests to research and quantitative subgraphs or calls portfolio, risk, and trading tools. Blue marks where the user can intervene. I connected the client to the server's progress events and approval API.

<a href="./assets/hama-agent-architecture.jpeg"><img src="assets/hama-agent-architecture.jpeg" width="860" alt="HAMA team architecture from the capstone poster. A supervisor routes user requests to tools, research, or quantitative analysis. Human intervention points are highlighted in blue."></a>

[Architecture notes](https://github.com/HAMA-team/HAMA-frontend-v2/blob/main/docs/how_it_works_agent_architecture.md)

</details>

<details>
<summary><b>See the research plan and order review screens</b></summary>

Users can choose the scope and method of the research, then change the quantity and price when they review a proposed order.

<img src="assets/hama-review.png" width="560" alt="Research plan review with scope and method controls on the left, and simulated order review with editable quantity and price on the right">

</details>

### PromptBall · Getting a baseball highlight tool ready for a user study

**Undergraduate research intern at IXLAB**

PromptBall turns written requests for baseball plays into highlight videos. I automated the **game data preparation pipeline** and improved the experience from selecting a game through replaying a clip. I added WebSocket progress updates and a timeline that jumps to individual clips. For the user study, I improved logging so researchers could trace each request to its results, and compiled viewing times for each participant.

<details>
<summary><b>Game data preparation, feedback on failed requests, and video processing</b></summary>

- The pipeline split game footage by inning, transcribed the audio, and generated summaries in one run, including games with extra innings.
- I added separate messages for requests involving a player outside the lineup and plays that did not happen in the selected game, so users knew how to revise their requests.
- I identified video re-encoding as a bottleneck and switched to FFmpeg stream copying. In internal lab tests, generation time per video went **from 3–10 minutes to 10–30 seconds**.

</details>

<details>
<summary><b>See the original PromptBall screens</b></summary>

*Team and game selection*

<img src="assets/promptball-game-selection.jpeg" width="720" alt="PromptBall team and game selection with Korean baseball teams and a game-date picker">

*Preparing to generate a highlight*

<img src="assets/promptball-generating-highlights.jpeg" width="720" alt="PromptBall with a highlight request field, the game box score, and a message that highlight generation is being prepared">

</details>

### Sticky Markdown Note · Pick up where you left off

I built this Electron app because I wanted to keep several notes open beside my work. It **saves notes as `.md` files and restores each open window's position and size** when you reopen the app. I also published a Windows installer.

[Source code](https://github.com/seongmini/sticky-markdown-note) · [Installer](https://github.com/seongmini/sticky-markdown-note/releases/latest)

### TripTrace · The same photos tell different stories by time and distance

TripTrace groups photos into trips using their timestamps and GPS coordinates, then displays them on a map. I implemented the trip segmentation by **treating each photo as a vertex and weighting the edges by elapsed time or distance**. The app builds a minimum spanning tree with Prim's algorithm and cuts edges that exceed the selected threshold.

[Screenshots and design](https://github.com/seongmini/triptrace#readme) · [Trip segmentation code](https://github.com/seongmini/triptrace/blob/master/test/trips.mjs)

<details>
<summary><b>Compare the time and distance rules</b></summary>

Say photo 3 was taken in the same neighborhood as photo 2, but two days later. The **24-hour** rule can split them into separate trips, while the **50 km** rule can group them together.

<img src="assets/triptrace-split.en.svg" width="800" alt="Five sample photos. Grouping by time puts photos 1–2 and 3–5 in separate trips. Grouping by location puts photos 1–3 and 4–5 in separate trips.">

[Time-based view](https://github.com/seongmini/triptrace/blob/master/photosforreadme/triptrace-time-based-trips.png) · [Distance-based view](https://github.com/seongmini/triptrace/blob/master/photosforreadme/triptrace-distance-based-trips.png)

</details>

## More Work

- **Campus Go** — In a three-person design project, I traced signup, approval, and cancellation through requirements and the data model. That exposed when pending applicants could be counted as confirmed attendees. Our report covered 34 functional requirements.
- **Coding instruction** — I teach C, Python, and data structures. I also designed criteria for sorting over 1,000 practice problems, reviewed the AI-assisted first pass for gaps in prerequisite order, and used the selection tool in lessons.
- **MoneyHub** — I integrated receipt OCR into a Kotlin Android app so users could review and correct the suggested transaction fields. [Code](https://github.com/seongmini/moneyhub)
- **SOS!** — I worked on quiz grading, saved attempts, and wrong-answer history in a Django learning app. [Code](https://github.com/gom31/WEBSOS)

In a source-grounded AI prototype, I defined when to retrieve evidence and when to let the user freely develop a story. The stack included FastAPI, LangGraph, and Chroma. I used AI coding tools for implementation and tested the behavior myself.
