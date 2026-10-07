# ISS Virtual Experience

An interactive space education website built with HTML, CSS, and JavaScript. Explore an ISS-inspired Cupola view, experiment with neutral buoyancy and weightlessness, and play a satellite mission game directly in the browser.

The project combines educational content, animated simulations, NASA imagery, and an external ISS position feed to make space exploration more engaging.

## Experiences

### ISS Cupola

Explore a themed Earth-observation dashboard inspired by the International Space Station's Cupola.

- Animated Earth view with an ISS position marker.
- Latitude, longitude, and altitude from an external ISS tracking API when available.
- Periodic position updates, approximately every five seconds.
- Topic windows covering climate, auroras, disasters, urban growth, oceans, space weather, and scientific research.
- Image searches through the NASA Image and Video Library API.
- Controls for globe rotation, centering, ISS lock, themes, and cloud display.
- Optional generated ambient sound and browser-based spoken narration.

The dedicated experience is available in `cupola.html`.

### Neutral Buoyancy Lab

An astronaut-training-inspired activity demonstrating the relationship between weight and buoyancy.

- Adjust ballast, fine-tuning, and trim controls.
- Observe changes in an astronaut avatar's simulated position.
- Monitor buoyancy and stability indicators.
- Start a timed challenge and respond to simulated disturbances.
- Review performance feedback after the challenge.
- Explore educational material about underwater training and its differences from spaceflight.

### Weightlessness Demo

- Click in the viewport to spawn floating objects.
- Drag objects and release them to observe drift.
- Watch objects bounce off the viewport boundaries.
- View the object count and clear the scene.

### Satellite Mission Control

- Move a satellite using keyboard controls or on-screen buttons.
- Avoid debris and collect data points.
- Track score, level, and health during the game.

## Tech Stack

| Technology | Purpose |
| --- | --- |
| HTML5 | Page structure and experience interfaces |
| CSS3 | Responsive layouts, themes, transitions, and animations |
| Vanilla JavaScript | Interactions, simulation state, and game logic |
| Canvas 2D | Animated orbit-style visualization |
| Fetch API | External image and ISS position requests |
| Web Audio API | Generated ambient sound |
| Web Speech API | Optional narration |
| Google Fonts | Typography |

There is no npm package installation, frontend framework, database, or separate backend in the repository. Styles and scripts are embedded in the two HTML files.

## Getting Started

### Requirements

- A modern browser.
- Internet access for external fonts, NASA imagery, and ISS position data.
- Python 3 for the optional local server, or an editor extension such as VS Code Live Server.

### Clone the Repository

```bash
git clone https://github.com/AhmedMemon7x/NASA-Project-Final-Version.git
cd NASA-Project-Final-Version
```

If the repository is renamed, update the URL and directory name in these commands.

### Run Locally

Serve the project folder with Python:

```bash
python -m http.server 8000
```

On Windows, you can also use:

```powershell
py -m http.server 8000
```

Open:

- Main experience: `http://localhost:8000/`
- Cupola dashboard: `http://localhost:8000/cupola.html`

Alternatively, open `index.html` with VS Code Live Server. A local HTTP server provides a consistent environment for page navigation and external requests.

## Controls

| Experience | Controls |
| --- | --- |
| Main menu | Select an experience card |
| Main page shortcuts | `1` opens the built-in Cupola mode; `2` opens the buoyancy mode |
| Main page experiences | `Escape` returns to the menu |
| Weightlessness | Click to spawn; drag and release to move; use Clear All to reset |
| Satellite game | Arrow keys or `W`, `A`, `S`, `D`; on-screen direction buttons |
| Buoyancy challenge | Adjust sliders and select Start Mission |
| Dedicated Cupola page | Use toolbar buttons and topic windows; `1` opens climate and `2` opens aurora content |

The dedicated Cupola page has its own Back to Menu link.

## Project Files

| File | Purpose |
| --- | --- |
| `index.html` | Main menu, educational sections, buoyancy activity, weightlessness demo, and satellite game |
| `cupola.html` | Dedicated Earth-observation and ISS position dashboard |

## External Resources

The current code calls these endpoints directly from the browser:

- NASA image search: `https://images-api.nasa.gov/search`
- ISS position: `https://api.wheretheiss.at/v1/satellites/25544`

The implementation does not supply an API key for either request. Availability depends on the providers, network access, and browser cross-origin policies. Additional images and fonts are loaded from external websites.

## Live Data and Simulations

- ISS position values can come from the tracking API. Some failed requests trigger randomly generated fallback values labelled **Simulated** by the request handler.
- Temperature anomalies, ocean temperature, and related story metrics are generated demonstration values, not retrieved environmental measurements.
- The orbit animation and globe marker mapping are visual approximations rather than an orbital model.
- Buoyancy, weightlessness, and satellite interactions are simplified educational simulations.

## Current Limitations

- The **View 3D (beta)** and **Export Snapshot** buttons currently display placeholder alerts.
- **View 360°** opens an external NASA image page; an interactive panorama viewer is not implemented.
- The training video embed currently uses a placeholder YouTube video and should be replaced with relevant content.
- Some external image URLs may become unavailable.
- Browser support and user interaction affect audio and narration availability.
- The Cupola startup code can overwrite its Live/Simulated status label with Ready; that label needs refinement for reliable data-source reporting.
- This README is based on a source review. Browser interactions and external service availability were not verified during its preparation.

## Deployment

The project can be hosted as a static website. Publish both HTML files together and use `index.html` as the entry page. No build command is required.

For GitHub Pages, select the branch containing these files and its root folder under **Settings → Pages**. Keep `cupola.html` alongside `index.html` so the relative navigation link works.

## Possible Improvements

- Implement a WebGL globe and a real snapshot export.
- Separate inline styles and scripts into maintainable files.
- Improve data-source labels and offline feedback.
- Replace placeholder media and review educational text for accuracy.
- Add interaction tests and improve keyboard and touch accessibility.

## Author

**Ahmed Memon** — [GitHub](https://github.com/AhmedMemon7x)

Created for educational and simulation purposes. This is an independent project and is not affiliated with or endorsed by NASA.
