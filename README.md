# ROAD RAGE: DEAD RUN

A standalone HTML5 Canvas zombie-driving game. Keyboard play works locally. Optional face controls need camera permission and an internet connection on first use to load the face-tracking library.

## Run locally

1. Open this project folder.
2. On Windows, double-click `START_GAME.bat`. It starts a local server and opens the game at `http://localhost:8000/road-rage-dead-run-updated.html`. Keep the launcher window open while playing.
3. Click **Enable face controls** and allow camera access in the browser prompt. If permission was previously denied, click the site icon beside the address bar, change Camera to Allow, then reload.
4. The first run downloads the face-tracking model from MediaPipe. After it loads, the game processes camera frames locally.
5. Press **Z** to start, or open your mouth to trigger the Z action.

Alternative: from this folder run `python -m http.server 8000 --bind 127.0.0.1`, then open `http://localhost:8000/road-rage-dead-run-updated.html`.

## Controls

### Webcam gestures (new)

- **Move head up:** Accelerate
- **Move head down:** Brake
- **Move head left / right:** Steer
- **Blink:** Trigger the Space action
- **Open mouth:** Trigger the Z action (start/restart)
- Keep your head near the calibrated centre to drive straight. Blink and mouth gestures have cooldowns to avoid repeated activation.

Camera access is requested by the browser. Video is processed locally and is not recorded or uploaded. The initial face-tracking model load requires an internet connection. If camera tracking is unavailable, keyboard controls remain available.

- **Up Arrow:** Accelerate
- **Down Arrow:** Brake
- **Left / Right Arrows:** Steer
- **Z:** Start or restart
- **Space:** Secondary action shown on the title screen

### Game-jam head-gesture controller

The participant listener sends standard keyboard input, so it works with the same arrow, Z, and Space controls as a keyboard. Open the game to its title screen, click the game area to focus the browser, then start the listener and self-test as described in the participant command sheet. Keep the game tab focused and the listener running during play.

### Optional hands-free face controls

1. Open the game in Chrome or Edge. For camera access, use `localhost` or an HTTPS page if opening the file directly does not permit the camera.
2. Click **Enable face controls** and allow camera permission.
3. Face the camera and click **Calibrate neutral** while looking straight ahead.
4. Move your head up to accelerate, down to brake, left/right to steer, blink to trigger Space, and open your mouth to trigger Z.
5. Click **Stop camera** to turn off the webcam. Frames are processed locally and are not recorded or uploaded.

Face tracking downloads MediaPipe Face Mesh from a CDN when enabled, so the first setup needs internet access. Keyboard controls remain available as a fallback.

The game runs in one browser tab and uses embedded HTML, CSS, and JavaScript. Gesture tracking uses the MediaPipe Tasks Vision module and face-landmark model, loaded from their public CDNs.

## Game-jam rules

Read `AGENTS.md` before changing the project. Its rules are mandatory. The AI tool instructions in `CLAUDE.md`, `GEMINI.md`, `.cursorrules`, `.cursor/rules/game-jam.mdc`, `.windsurfrules`, and `.github/copilot-instructions.md` point back to it.
