# 🌸 Bankai: Senbonzakura Kageyoshi

An interactive, high-performance WebGL 3D particle simulation inspired by Byakuya Kuchiki's iconic Bankai from *Bleach*. This project leverages custom GLSL shaders and real-time physics to render thousands of cherry blossom petals that respond dynamically to user interaction.

**[🔗 CLICK HERE TO VISIT THE PROJECT'S OFFICIAL WEBSITE](https://aazimquadiri.github.io/BankaiSenbonzakuraKageyoshi/)**

---

## 🎬 Image Preview

<div align="center">
  <a href="https://aazimquadiri.github.io/BankaiSenbonzakuraKageyoshi/">
    <img src="https://iili.io/B0jfl4t.png" alt="Senbonzakura Kageyoshi Preview" width="100%" style="border-radius: 10px; box-shadow: 0 10px 30px rgba(0,0,0,0.5);">
  </a>
  <p><i>Click the image above to experience the interactive Bankai release.</i></p>
</div>

---

## ✨ Key Features

### 🌌 Advanced WebGL Rendering
* **High Particle Count:** Effortlessly renders 2,000+ individual petals using GPU-accelerated instancing.
* **Custom GLSL Shaders:** Utilizes bespoke Vertex and Fragment shaders to handle complex petal geometry and lighting calculations on the GPU.
* **Dynamic Lighting & Specular Highlights:** Real-time calculation of diffuse and specular components, giving petals a realistic shimmer as they rotate.

### 🌬️ Interactive Physics Engine
* **Mouse Repulsion:** Petals calculate distance from the cursor and react with a "scatter" effect, simulating a physical wind force.
* **Turbulence & Spin:** Proximity to the cursor increases rotational velocity, creating chaotic and beautiful movement patterns.
* **Smooth Return:** A built-in "base velocity" system ensures petals gracefully return to their original falling path after interaction.

### 🎨 Cinematic Visual Effects
* **Depth of Field (DOF):** A realistic lens effect that blurs petals as they move toward or away from the camera's focus plane.
* **Bloom & Directional Blur:** Custom post-processing passes that create a soft, ethereal glow and motion streaks.
* **Liquid Glass UI:** Modern "Glassmorphism" UI elements with liquid-morphing animations and backdrop blurs.

---

## 🕹️ Interaction & UI Guide

### 👁️ The Bankai Toggle (Eye Button)
Located on the right side, this interactive "liquid-glass" button controls the presence of the subject:
* **Function:** Toggles the visibility of `subject.png`.
* **Visual Feedback:** Triggers a **Canvas 2D Particle Burst** at the button's coordinates upon click.
* **Aesthetics:** Features a morphing organic shape animation and a glassmorphism backdrop filter.

### 🌪️ Environmental Control
| Action | Result |
| :--- | :--- |
| **Move Mouse** | Scatter petals and create wind turbulence via repulsion physics. |
| **Touch (Mobile)** | Repel petals from the point of contact on mobile devices. |
| **Social Icons** | Pulse and ripple animations on interaction with GitHub/Social links. |

---

## 🛠️ Technical Deep Dive

### The Shaders
The core of the visual beauty lies in the scripts:
* **Vertex Shader (`petals_point_vsh`):** Handles positioning, rotation, and size calculation based on the camera matrix.
* **Fragment Shader (`petals_point_fsh`):** Draws the actual petal shape using mathematical ellipses and applies color gradients.

### Post-Processing Pipeline
1.  **Main Render:** Draws the petals to a hidden texture.
2.  **Bright Pass:** Extracts the brightest parts of the scene for the glow.
3.  **Directional Blur:** Applies horizontal and vertical blurs to the bright pass.
4.  **Final Composition:** Merges the original scene with the blurred pass (Bloom).

---

## 📁 File Structure

```text
├── index.html       # Entry point & GLSL Shader code
├── style.css        # UI styling & liquid-morphing animations
├── script.js        # WebGL Engine & Physics interactions
├── preview.mp4      # Looping video for README (Root Directory)
├── CNAME            # Custom domain configuration (bankai.plaxinfy.in)
└── assets/
    └── subject.png  # The central character image
```

---

## 🚀 Local Development

Because this project uses WebGL and external assets, running it through a local server is **required** to avoid CORS (Cross-Origin Resource Sharing) security errors.

### Option 1: VS Code (Recommended)
1. Install the **Live Server** extension.
2. Right-click `index.html` and select **"Open with Live Server"**.

### Option 2: Python Server
If you have Python installed, run this command in your project folder:
```bash
# For Python 3.x
python -m http.server 8000
```
Then visit `http://localhost:8000`.

### Option 3: Node.js (npx)
If you have Node.js installed, use one of these commands:
```bash
# Using 'serve'
npx serve .

# OR using 'http-server'
npx http-server .
```
Then visit the URL provided in the terminal.

---

## 👨‍💻 Author

**Aazim Quadiri**
* **GitHub:** [@aazimquadiri](https://github.com/aazimquadiri)
* **X (Twitter):** [@captainfinite](https://x.com/captainfinite)
* **Instagram:** [@captainfinite](https://www.instagram.com/captainfinite)

## 📄 License

This project is licensed under the **MIT License**. Feel free to use, modify, and distribute the code while providing attribution.
