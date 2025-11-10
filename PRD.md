# 📘 Product Requirements Document: Decoraphonic

## 🧭 Overview
**Decoraphonic** is an elegant, cylindrical wireless speaker system designed to blend discreetly into home decor as a curio or plant stand. It features a 2-way audio system with a down-firing woofer and forward-facing full-range driver for rich, high fidelity sound. Housed in a 3D-printed column with a wooden base and top, the speaker integrates with Music Assistant via Bluetooth or WiFi and supports scalable multi-room audio.

---

## 🎯 Goals
- Deliver high-fidelity, room-filling sound in an elegant, discreet, functional form that’s as pleasing to the eye as it is to the ear.
- Enable scalable multi-room audio deployment.
- Maintain a build cost under $100 per unit.
- Support future outdoor variant.

---

## 🔊 Core Features

### Audio System
- **2-Way Configuration**:
  - Down-firing woofer with acoustic diffuser
  - Forward-facing full-range driver mounted to a flattened surface near the top
- **Bi-amplified DSP-enabled amplifier**:
  - Active crossover
  - Bluetooth or WiFi streaming
  - Multi-room sync via Music Assistant
  - Configurable as left channel, right channel, or stereo blend

### Physical Design
- **Form Factor**: 42" tall, 6" diameter (base/top caps); 4.8" diameter speaker cylinder
- **Modular Construction**:
  - 3D-printed (optimized for 250×250×250 mm build volume) in 4 interlocking segments
  - Bayonet-style twist-lock mechanism with silicone gaskets for a tight, vibration-free seal
- **Materials**:
  - Interchangeable speaker cloth sleeve slides over assembled cylinder, tucks into a recessed groove, and locks in place with end caps
  - Interchangeable wooden base and top attach via strong magnets to speaker cloth retainer caps

### Electronics
- **Amplifier Module**:
  - DSP-enabled, bi-amp capable
  - Compact form factor
- **Power Supply**:
  - Internal AC module with fully concealed AC power cord routed through internal channels and exiting discreetly through the bottom surface of the base
- **Connectivity**:
  - Bluetooth or WiFi

---

## 🧠 Expanded Design Considerations

### Acoustic & Audio Enhancements
- Internal felt lining to reduce reflections and standing waves
- Silicone mounts to isolate drivers from enclosure vibrations

### Power & Connectivity
- Auto-on sensing: amp wakes on signal detection to conserve power

### Structural & Assembly
- Internal cable routing channels with molded guides or clips
- Keyed alignment tabs for correct rotational orientation during assembly

### Software & Integration
- Preconfigured DSP profiles for Music Assistant latency compensation
- Custom EQ presets: “Decoraphonic Warm,” “Decoraphonic Clear,” etc.
- Companion app with Decoraphonic-themed UI for DSP control, LED behavior, and EQ settings

### Aesthetic & Branding
- LED in bottom of base creates a glow to indicate power and sync/connection status (can be turned off in app)
- Signature LED ring light near base optionally flashes/pulses or chases with music (colors, patterns configurable in app)
- Modular top/bottom caps (attached via strong magnets) available in:
  - Matte/gloss black, white, and custom colors
  - Standard woods: walnut, birch, black oak
  - Premium/super-premium woods: curly maple, teak, rosewood, cocobolo, Purple Heart, wenge, etc.

### Modularity & Future Expansion
- Battery-powered outdoor variant with rubber gaskets, plugs, and solar charging option

---

## 🗣️ Addendum: Voice Assistant Integration (Decoraphonic Voice)

### 🔧 Architecture Overview
To enable local voice control and smart assistant features, Decoraphonic Voice integrates a small SBC capable of running Home Assistant’s **Voice Assist** stack. This allows for wake-word detection, speech-to-text, and natural language control of smart home devices — all processed locally.

### Core Components
| Component | Role |
|----------|------|
| SBC (e.g., Orange Pi 4, Radxa Zero 2) | Runs Voice Assist, app interface, LED control, and DSP configuration |
| DSP Board (e.g., ADAU1701) | Handles crossover, EQ, gain, and delay |
| Class D Amp (e.g., TPA3255) | High-fidelity amplification |
| Dual MEMS Microphones | Far-field voice capture (e.g., INMP441) |
| Speaker Drivers | Same as base Decoraphonic unit |

### Voice Assist Capabilities
- Wake word detection (via OpenWakeWord)
- Local speech-to-text (Whisper or Piper)
- Natural language parsing (Home Assistant Assist)
- Smart home control via Home Assistant
- Optional LLM-based conversational responses
- OTA updates and app-based configuration

### Design Considerations
- Thermal management: SBC and amp heat dissipation via internal airflow or passive venting
- Mic placement: Discreetly integrated into top cap or upper cylinder with acoustic transparency
- Power: Shared 12V rail with buck converters for SBC and amp
- LED feedback: Voice activity and wake word response indicated via LED ring or base glow

### Budget Impact
| Component | Est. Cost |
|-----------|-----------|
| SBC (Orange Pi or Radxa) | $25–35 |
| DSP Board | $10–20 |
| Upgraded Class D Amp | $20–30 |
| Mics + LED + wiring | $10–15 |
| **Total Add-on Cost** | ~$65–85 |

> Voice-enabled units may exceed the $100 target slightly, but offer premium functionality for flagship placements.
