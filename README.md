# human_computer_interaction_based_car_game
# 🏎️ PolyTrack 3D

A fast-paced **HTML5 3D arcade racing game** built with **Three.js**, featuring a clean white low-poly aesthetic, dynamic racing physics, boost pads, jumps, loops, checkpoints, drifting, procedural audio, and responsive camera modes.

> **PolyTrack 3D – Minimal White Edition**

The game is designed as a lightweight browser-based racing experience that runs directly in a modern web browser without requiring a game engine installation.

---

## 🎮 Game Overview

**PolyTrack 3D** puts the player behind the wheel of a futuristic low-poly sports racer on an elevated stunt circuit.

The track includes:

- 🏁 3-lap time attack racing
- 🌀 Rollercoaster-style loops
- 🚀 High-speed jumps
- ⚡ Speed boost pads
- 🛣️ Banking turns and chicanes
- 🏎️ Arcade-style vehicle physics
- 💨 Drift and handbrake mechanics
- 🚧 Checkpoint gates
- 🌐 Dynamic 3D camera
- 🔊 Procedural engine and tire sounds
- 📱 Mobile touch controls
- 📊 Real-time racing HUD

The start screen itself describes the game as a low-poly racer with loops, high-speed jumps, banking turns, and dynamic drift physics.

---

## ✨ Features

### 🌐 3D Web Rendering

The game uses **Three.js/WebGL** for real-time 3D rendering.

The HTML loads Three.js directly and creates a WebGL renderer with antialiasing, responsive sizing, device-pixel-ratio handling, and shadow rendering. 

### 🏁 Dynamic Race Track

The circuit is generated from a `CatmullRomCurve3` path and contains:

- Long straights
- Fast turns
- Elevated sections
- Ramps
- Chicanes
- Hairpins
- Ski-jump sections
- Loop-style sections

The track is constructed from multiple 3D path points and interpolated into a continuous racing circuit.

### ⚡ Speed Boost System

Four boost pads are distributed around the circuit.

Driving over a boost pad temporarily increases the car's maximum speed and activates a visual boost effect and boost sound.

### 🌀 Drift Physics

Hold **SPACE** while travelling at sufficient speed to activate the drift/handbrake mechanic.

The game increases the turning multiplier while drifting and continuously calculates a drift score.

### 🚀 Jump & Airborne Physics

The vehicle has vertical physics with:

- Gravity
- Vertical velocity
- Elevated track sections
- Airborne state detection
- Landing behavior

The HUD displays whether the car is currently **Grounded** or **AIRBORNE!**.

### 🏎️ 3D Player Car

The player vehicle is constructed directly from Three.js geometry rather than requiring an external 3D model.

The car includes:

- Sports-racer chassis
- Aerodynamic nose
- Cabin/windshield
- Rear spoiler
- Headlights
- Taillights
- Four wheels
- Rims
- Blue performance accents



### 🎧 Procedural Audio

The game includes a browser-based `AudioContext` sound engine.

It generates:

- Engine sound
- Tire/skid sound
- Boost sound
- Checkpoint sound
- Crash/recovery sound

The engine and tire effects are generated procedurally rather than requiring separate audio files.

### 📊 Racing HUD

During gameplay, the interface displays:

- Current lap
- Current race time
- Best lap
- Speed
- Air/ground status
- Checkpoint progress
- Drift status
- Keyboard control indicators
- Audio toggle
- Quick reset



### 🏆 Race Statistics

After completing the race, the game displays:

- Total race time
- Best lap
- Top speed
- Drift score

The race is completed after **3 laps**. 

---

## 🎮 Controls

| Key | Action |
|---|---|
| `W` / `↑` | Accelerate |
| `S` / `↓` | Brake / Reverse |
| `A` / `←` | Steer Left |
| `D` / `→` | Steer Right |
| `SPACE` | Drift / Handbrake |
| `R` | Reset / Recover Car |
| `C` | Change Camera Mode |

These controls are also presented directly in the game's start screen.

---

## 📱 Mobile Controls

PolyTrack 3D includes touch input support.

On a touch device:

- Touching the game canvas activates acceleration.
- Moving the finger horizontally steers the vehicle.
- Moving left steers left.
- Moving right steers right.
- Releasing the touch stops the corresponding input.



---

## 🎥 Camera Modes

Press:

```text
C
```

to switch between the available camera modes.

The game currently supports:

1. Dynamic third-person chase camera
2. Close hood camera



---

## 🏗️ Technology Stack

| Technology | Purpose |
|---|---|
| HTML5 | Game structure |
| CSS3 | Interface and visual styling |
| JavaScript | Game logic and physics |
| Three.js | 3D rendering |
| WebGL | Hardware-accelerated graphics |
| Web Audio API | Procedural sound |
| Tailwind CSS CDN | UI utility styling |
| Google Fonts | Typography |

The project currently imports **Three.js r128**, Tailwind CSS, and Google Fonts through external CDN resources.

---

## 🎨 Visual Design

PolyTrack 3D uses a **minimal white glassmorphism interface**.

The design includes:

- White racing surface
- White translucent HUD panels
- Blue accent lighting
- Dark typography
- Glass blur effects
- Soft shadows
- Minimalist low-poly environment
- Blue track rails
- Cyan boost pads

The interface styling defines translucent white panels with backdrop blur, white solid cards, dark primary buttons, and blue interactive states.

---

## 🌳 Environment

The racing environment contains procedurally positioned low-poly trees surrounding the track.

The environment also includes:

- Large ground plane
- Grid markings
- Fog
- Directional lighting
- Hemisphere lighting
- Dynamic shadows
- Low-poly vegetation

 

---

## 🏁 Race System

The race uses:

```text
3 LAPS
   ↓
4 CHECKPOINTS
   ↓
START/FINISH LINE
   ↓
RACE COMPLETE
```

The game tracks:

- Current lap
- Current checkpoint
- Lap time
- Best lap
- Total race time
- Top speed
- Drift score

The race state progresses through:

```text
START
  ↓
RACING
  ↓
FINISHED
```



---

## 🔊 Audio System

The game uses the browser's Web Audio API.

### Engine

Engine frequency changes according to vehicle speed and acceleration.

### Tire Skid

Filtered white noise is used to simulate tire/drift audio.

### Boost

A rising oscillator sweep is triggered when the vehicle hits a boost pad.

### Checkpoint

A short two-tone effect plays when a checkpoint is reached.

### Crash / Recovery

A descending oscillator effect plays when the vehicle is recovered.



---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/polytrack-3d.git
```

### 2. Enter the project

```bash
cd polytrack-3d
```

### 3. Run the game

Because the project is primarily a client-side HTML5 application, you can open the HTML file in a modern browser.

For the most reliable development experience, use a local HTTP server.

For example:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000/
```

---

## 📁 Project Structure

A minimal repository can use:

```text
polytrack-3d/
│
├── poly_track_3d_racer.html
├── README.md
└── LICENSE
```

The current game is implemented as a single HTML5 file containing the UI, styles, JavaScript game logic, Three.js scene setup, vehicle geometry, physics, audio engine, and controls.

---

## 🖥️ Browser Compatibility

The game is designed for modern browsers supporting:

- HTML5
- WebGL
- JavaScript ES6+
- Web Audio API
- Touch Events

Recommended browsers:

- Google Chrome
- Microsoft Edge
- Mozilla Firefox
- Safari

Performance will depend on the device's GPU, browser, screen resolution, and enabled graphics features.

---

## ⚙️ Performance

The renderer uses:

```javascript
antialias: true
```

and caps the device pixel ratio at:

```javascript
Math.min(window.devicePixelRatio, 2)
```

The game also enables Three.js shadow mapping and uses a soft-shadow configuration.

For better performance on lower-end devices, future versions could add:

- Graphics quality settings
- Shadow-quality controls
- Reduced draw distance
- Object pooling
- Level-of-detail models
- Adaptive pixel ratio
- Optional fog quality
- Mobile performance mode

---

## 🛠️ Customization

You can modify the following game parameters directly in the JavaScript source.

### Vehicle Speed

```javascript
maxSpeed: 170,
boostSpeed: 235
```

### Acceleration

```javascript
accel: 52
```

### Brake Power

```javascript
brakePower: 70
```

### Steering

```javascript
turnSpeed: 2.5
```

### Race Laps

```javascript
const TOTAL_LAPS = 3;
```

These parameters are defined in the game's physics configuration.

---

## 🔮 Future Improvements

Possible future additions include:

- [ ] Multiple racing tracks
- [ ] Multiple cars
- [ ] AI opponents
- [ ] Nitro management
- [ ] Vehicle customization
- [ ] More camera modes
- [ ] Improved collision detection
- [ ] Leaderboards
- [ ] Local high-score storage
- [ ] Online multiplayer
- [ ] Gamepad support
- [ ] Mobile virtual steering controls
- [ ] Graphics-quality settings
- [ ] Texture support
- [ ] More advanced vehicle physics
- [ ] Additional environmental objects
- [ ] Race countdown sequence
- [ ] Pause menu
- [ ] Settings menu

---

## 🤝 Contributing

Contributions are welcome.

1. Fork the repository.
2. Create a feature branch.

```bash
git checkout -b feature/my-new-feature
```

3. Make your changes.
4. Test the game in a modern browser.
5. Commit your changes.

```bash
git commit -m "Add new racing feature"
```

6. Push the branch.

```bash
git push origin feature/my-new-feature
```

7. Open a Pull Request.

---

## 🐛 Bug Reports

If you find a bug, please open a GitHub Issue and include:

- Browser and version
- Operating system
- Desktop or mobile device
- Steps to reproduce
- Expected behavior
- Actual behavior
- Console errors, if available
- Screenshot or screen recording, if useful

---

## 📜 License

Add your preferred open-source license to the repository.

For example:

```text
MIT License
```

If you choose the MIT License, create a `LICENSE` file containing the official MIT license text.

---

## ⚠️ Third-Party Dependencies

This project currently loads external libraries/resources from CDNs, including:

- Three.js
- Tailwind CSS
- Google Fonts

If you deploy the project in an environment requiring fully self-contained assets, consider downloading and hosting these dependencies locally.

---

## ⭐ Support the Project

If you like **PolyTrack 3D**, consider:

⭐ Starring the repository  
🍴 Forking the project  
🐛 Reporting bugs  
💡 Suggesting features  
🔧 Contributing improvements  

---

## 🏎️ Project Name

**PolyTrack 3D — Minimal White Edition**

A browser-based low-poly 3D racing experiment combining arcade physics, stunt-track gameplay, procedural audio, and a modern white glassmorphism interface.

---

### Made with HTML5 + JavaScript + Three.js 🚀
