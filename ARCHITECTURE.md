# 📡 Open-Sonar Architecture Plan

> **Vision:** A modular, event-driven ecosystem optimized for full-duplex real-time speech-to-speech (S2S) with sub-second resonance and natural barge-in.

---

### 🌐 High-Level Architecture Overview
*   **Core Engine:** Asynchronous Python core optimized for **sub-second resonance**.
*   **Orchestration:** Pipeline-based layer built directly upon **OpenAgent’s** multi-model framework.
*   **Transport:** **WebRTC-first** bidirectional audio streams with WebSocket synchronization.
*   **Intelligence:** Parallel multimodal path for active screen/data mapping.
*   **Aesthetic:** Synchronized visualization layer enforcing a **Living Minimalist** UI (Pulse glows, Sonar Cyan accents).

---

### 🎙️ 1. Real-Time Voice Pipeline Core
*   **Framework:** `Pipecat` (Primary orchestration) integrated with `FastRTC` or `LiveKit`.
*   **Live Voice Core:** **Gemini 3.1 Flash Live Preview** (`gemini-3.1-flash-live-preview`).
    *   Native audio-to-audio for ultra-low-latency.
    *   Built-in acoustic nuance detection and tool calling.
*   **VAD & Barge-In:** Native Gemini Live interruption support; supplemented by `Silero VAD` for local preprocessing.

> **📍 Placement:** Central audio processing pipeline; replaces traditional cascaded STT/TTS stages with direct audio-to-audio streaming.

---

### 🧠 2. Agent & Multimodal Orchestration Layer
*   **Core Integration:** Direct Python hook into the **OpenAgent** framework for multi-model reasoning.
*   **Environmental Mapping:** Parallel vision models (e.g., `Qwen2-VL` or open multimodal LLMs) fed by live screen streams.
*   **Context Management:** Combined Gemini Live API output with OpenAgent’s native function/tool calling for persistent state.

> **📍 Placement:** Central hub receiving streamed audio + visual context; generates reasoned responses and steers downstream audio output concurrently.

---

### ⚡ 3. Real-Time Transport & Concurrency Layer
*   **Backend:** `FastAPI` serving WebSocket endpoints and integrating with `Pipecat/FastRTC`.
*   **Transport Protocols:** 
    *   **WebRTC:** Primary bidirectional audio streaming.
    *   **WebSockets:** Primary channel for Gemini Live API and control-plane synchronization.
*   **Concurrency:** `Asyncio`-based event-driven runtime with non-blocking processors.

> **📍 Placement:** Boundary layer between client I/O (Mic/Speaker/Screen) and the Python core; handles all data ingress/egress.

---

### 🎨 4. Living Minimalist UI & Visualization Layer
*   **Frontend Stack:** `Next.js` (React) for modern web-based reactivity and API proxying.
*   **Real-Time Rendering:** `Three.js` (WebGL) for:
    *   **3D Isometric Elements:** Translucent frosted-glass materials.
    *   **Echo Rings:** Concentric circles and glowing pulse waveforms.
    *   **Gradients:** `Solar White` to `Sonar Cyan` high-key lighting.
*   **Data Visualization:** `Chart.js` / `Plotly.js` with Web Audio API shaders.

> **📍 Placement:** Parallel synchronized subscriber layer; renders "living intelligence" visuals in real-time without impacting audio latency paths.

---

### 🚀 5. Inference & Optimization Layer
*   **Model Serving:** 
    *   **Cloud:** Google Gemini Live API (`gemini-3.1-flash-live-preview`).
    *   **Local:** Hugging Face Transformers + `Torch 2.x` (CUDA/Torch Compile).
*   **Acceleration:** Optional `ONNX`, `TensorRT`, or `vLLM` backends for auxiliary components.
*   **Deployment:** Hybrid local-first open-source stack with Gemini Live as the high-performance flagship.

> **📍 Placement:** Underpinning the pipeline; ensures end-to-end resonance while maintaining extensibility for model swapping.

---

### 🛠️ 6. Extensibility & Modularity Decisions
*   **Plugin Architecture:** Enables swapping components (e.g., falling back from Gemini Live to fully open models) without disruption.
*   **2025-2026 Ready:** Native preference for streaming-native models and frameworks.
*   **Unified Language:** Python core (`FastAPI` + `Pipecat`) ensures zero-friction **OpenAgent** integration.
*   **Modern Frontend:** `Next.js` chosen for WebRTC support and alignment with Apple/Google-style aesthetics.

---
*Open Sonar Architecture Plan | v1.0 | Licensed under AGPL-3.0*
