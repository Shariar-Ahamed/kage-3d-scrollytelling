# ⛩️ Kage — Immersive 3D Scrollytelling Landing Page

[![React](https://img.shields.io/badge/React-19.2-61DAFB?logo=react&logoColor=black)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-6.0-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Vite](https://img.shields.io/badge/Vite-8.2-646CFF?logo=vite&logoColor=white)](https://vitejs.dev/)
[![Three.js](https://img.shields.io/badge/Three.js-WebGL-black?logo=three.js&logoColor=white)](https://threejs.org/)
[![ThreeUI](https://img.shields.io/badge/ThreeUI-DesignCode-FF3366)](https://threeui.designcode.io)

An Awwwards-style, high-performance 3D scrollytelling web experience featuring an interactive Japanese temple narrative (*Kage / Secret Pathways*). Built with **React 19**, **TypeScript**, **Vite**, and **ThreeUI**, combining custom WebGL shaders, camera parallax, responsive typography, and self-contained static assets.

---

## 🌟 Features

- **⛩️ 3D Scrollytelling & Camera Kinematics**: Smooth scroll-linked camera translation, depth-layer displacement, and responsive mouse parallax.
- **⚡ Custom WebGL Rendering**: GPU-accelerated atmospheric fog, custom lighting, depth maps, and dynamic Torii gate scenes powered by Three.js.
- **🎨 Configurable React Component**: Fully typed `<KageLandingPage />` with customizable typography, colors, font weights, and letter spacing.
- **📦 100% Offline Asset Suite**: Self-hosted fonts (`Onest`), Three.js runtime, and high-fidelity WebP binary visual assets with zero third-party CDN latency.
- **🔒 Byte-Verified Integrity**: Verified against exact canonical SHA-256 hashes for pixel-perfect fidelity.
- **🚀 Ultra-fast DX**: Built on Vite 8 with Oxlint for instant HMR and optimized production bundles.

---

## 🛠️ Tech Stack

| Layer | Technology | Description |
| :--- | :--- | :--- |
| **Framework** | [React 19](https://react.dev/) | Component architecture & state management |
| **Language** | [TypeScript](https://www.typescriptlang.org/) | Type safety and strict interfaces |
| **Bundler & Tooling** | [Vite 8](https://vitejs.dev/) + [Oxlint](https://oxc.rs/) | High-speed build tooling and linting |
| **3D & Shaders** | [Three.js](https://threejs.org/) + [ThreeUI](https://threeui.designcode.io) | WebGL scenes, scrollytelling engine & recipes |
| **Styling** | Vanilla CSS + Design System Tokens | Fluid layouts, glassmorphism, and responsive frames |

---

## 📂 Project Structure

```text
Demo/
├── public/
│   ├── favicon.svg                     # Application favicon
│   ├── icons.svg                       # SVG sprite definitions
│   └── landing-pages/
│       ├── kage.html                   # Canonical WebGL scene canvas & iframe sandbox
│       └── secret-pathways-assets/
│           ├── fonts.css               # Embedded Onest font definitions
│           ├── three.min.js            # Standalone Three.js runtime
│           ├── foreground/             # Optimized WebP parallax foreground assets
│           └── generated/              # WebP environment & depth texture maps
├── src/
│   ├── assets/                         # UI icons and static visuals
│   ├── shaders/
│   │   ├── landing-pages/
│   │   │   ├── LandingPages.tsx        # React wrapper & iframe communication layer
│   │   │   ├── pageRecipes.ts          # Scene layout metadata & text definitions
│   │   │   └── pageTypography.ts       # Dynamic font sizing & letter-spacing logic
│   │   └── threeui.css                 # ThreeUI structural stylesheet
│   ├── App.css                         # App-level styling and viewport layout
│   ├── App.tsx                         # Root application entry
│   ├── index.css                       # Global CSS resets and theme tokens
│   ├── main.tsx                        # React DOM mounting
│   └── Scene.tsx                       # Configured KageLandingPage instance
├── index.html                          # HTML shell
├── package.json                        # Dependencies and script definitions
├── tsconfig.json                       # TypeScript compiler options
└── vite.config.ts                      # Vite configuration
```

---

## 🚀 Getting Started

### Prerequisites

Ensure you have **Node.js** (v18.0.0 or higher) and **npm** installed:

```bash
node -v
npm -v
```

### 1. Installation

Clone or open the project directory and install the dependencies:

```bash
npm install
```

### 2. Run Development Server

Start the local development server with Hot Module Replacement (HMR):

```bash
npm run dev
```

Open your browser and navigate to `http://localhost:5173`.

### 3. Build for Production

Compile TypeScript and build the optimized production bundle:

```bash
npm run build
```

### 4. Preview Production Build

Preview the generated `dist/` bundle locally:

```bash
npm run preview
```

### 5. Linting

Run Oxlint to check code quality and syntax standards:

```bash
npm run lint
```

---

## ⚙️ Component Usage & Customization

The main scene is configured inside [`src/Scene.tsx`](file:///C:/Users/User/Desktop/Demo/src/Scene.tsx):

```tsx
import { KageLandingPage } from "@designcodeio/threeui";
import "@designcodeio/threeui/style.css";

export function Scene() {
  return (
    <div className="shader-frame">
      <KageLandingPage
        headingFont="onest"
        bodyFont="onest"
        headingWeight="400"
        bodyWeight="300"
        primaryColor="#e0231c"
        headingSize={46}
        bodySize={17}
        headingLetterSpacing={-0.012}
      />
    </div>
  );
}
```

### Available Props

| Prop | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| `primaryColor` | `string` | `"#e0231c"` | Accent branding color for highlights, links & buttons |
| `headingFont` | `string` | `"onest"` | Font family applied to section titles and hero headers |
| `bodyFont` | `string` | `"onest"` | Font family applied to descriptions and body copy |
| `headingWeight`| `string \| number` | `"400"` | Font weight for headings (`300`, `400`, `600`, `700`) |
| `bodyWeight` | `string \| number` | `"300"` | Font weight for body copy |
| `headingSize` | `number` | `46` | Base headline font size (in px) |
| `bodySize` | `number` | `17` | Base body text font size (in px) |
| `headingLetterSpacing` | `number` | `-0.012` | Tracking / letter spacing adjustment for typography |

---

## 🔒 Asset Verification & Canonical Hashes

All source components and binary WebP assets have been verified against their canonical SHA-256 checksums:

| File Path | SHA-256 Hash |
| :--- | :--- |
| `src/shaders/landing-pages/LandingPages.tsx` | `d34af7b5bf8239835102e34de46e7cae69ab29f875acffd3050209ba64b684f5` |
| `src/shaders/landing-pages/pageTypography.ts` | `809cc65797d531cd3b3ca5a56815d55d24b3ee8d293e4e4bad6fdfe6c83244cc` |
| `src/shaders/landing-pages/pageRecipes.ts` | `c9d9849cc255bac2d1d938d088c50917f84916f1c516d2bbb27fcfd803523233` |
| `public/landing-pages/kage.html` | `c8e06b90397ac246baf0ab6f32f5f6b570acc6fe03c7009f711b579fb72d9f49` |
| `public/landing-pages/secret-pathways-assets/fonts.css` | `985f85a904a4096f92c06552b06f42a45973ac004af4780d68f18af65ddcc1b0` |
| `public/landing-pages/secret-pathways-assets/three.min.js` | `8a5f7249903b54d30f79f708699d2fed2d6a1d0741a4cd41377d1f01bb5a2271` |
| `src/shaders/threeui.css` | `efe4447139f1358dd8e9be68edf6fa46cbefbd1de423a4d6c439ca61d2c8eccf` |

---

## 🤝 Contributing & Guidelines

1. Fork or branch from `main`.
2. Ensure linting passes via `npm run lint`.
3. Verify type-checks with `npm run build`.
4. Open a clear Pull Request with context on UI or performance enhancements.

---

## 👨‍💻 Developer & Connect

Crafted with devotion by **Shariar Ahamed**

- 🌐 **Portfolio**: [shariarahamed.me](https://www.shariarahamed.me/)
- 💼 **LinkedIn**: [in/shariarahamed](https://www.linkedin.com/in/shariarahamed/)
- 🐙 **GitHub**: [@Shariar-Ahamed](https://github.com/Shariar-Ahamed)
- 🐦 **X / Twitter**: [@ShariarAlways](https://x.com/ShariarAlways)
- 📸 **Instagram**: [@shahriar_thebrowncat](https://www.instagram.com/shahriar_thebrowncat)
- 📘 **Facebook**: [Shahriar.TheBrownCat](https://www.facebook.com/Shahriar.TheBrownCat)

---

## 📄 License & Credits

- **Engine & Assets**: Designed & created by [DesignCode](https://designcode.io) / ThreeUI.
- **Developer**: [Shariar Ahamed](https://www.shariarahamed.me/)
- **License**: MIT
