# Hush
Hush is a suite of privacy-focused, zero-telemetry audio processing plugins and modules built with a clean, native C++ architecture.
## **Design Pillars**
 * **Zero Telemetry & Analytics**: Designed from the ground up to operate completely offline with an absolute absence of analytics, tracking SDKs, or external network calls.
 * **High-Performance C++ Architecture**: Engineered for low-latency, real-time audio execution and multi-track scalability.
 * **Robust Verification**: Backed by automated test harnesses, continuous integration support, and rigorous sample verification.
## **Core Modules & Effects**
The suite includes a comprehensive collection of modular DSP components and corresponding plugin wrappers:
 * **AB** (HushAB / HushABPlugin): A/B comparison and switching utilities for quick reference validation.
 * **Album** (HushAlbum / HushAlbumPlugin): Album-level processing and macro-dynamic management.
 * **Edges** (HushEdges / HushEdgesPlugin): Transient shaping and edge definition controls.
 * **Hum** (HushHum / HushHumPlugin): Targeted harmonic hum removal and frequency cleaning.
 * **Level** (HushLevel / HushLevelPlugin): Precision level control, balancing, and loudness management backed by HushLoudnessMeter.h.
 * **Match** (HushMatch / HushMatchPlugin): Spectral and tonal matching tools.
 * **Noise** (HushNoise / HushNoisePlugin): Advanced spectral noise reduction.
 * **Peak** (HushPeak / HushPeakPlugin): Peak control and true peak limiting powered by HushTruePeakLimiter.h.
 * **Sibilance** (HushSibilance / HushSibilancePlugin): Dedicated de-essing and sibilance management.
 * **Smooth** (HushSmooth / HushSmoothPlugin): Audio smoothing utilities for signal stabilization.
## **Repository Layout**
```text
Hush/
├── CMakeLists.txt          # Main build system configuration[span_15](start_span)[span_15](end_span)
├── dsp/                    # Core DSP utilities, meters, and limiters[span_16](start_span)[span_16](end_span)
├── modules/ & src/         # Core audio processing module business logic[span_17](start_span)[span_17](end_span)
├── plugins/                # Individual plugin implementations & factory[span_18](start_span)[span_18](end_span)
├── wrapper/                # Plugin processor and editor interface wrappers[span_19](start_span)[span_19](end_span)
├── ui/                     # Custom user interface panels, credits, and notes[span_20](start_span)[span_20](end_span)
├── scripts/                # Test mains (`effect_test_main.cpp`, `null_test_main.cpp`) & test automation (`run_ab_tests.sh`)[span_21](start_span)[span_21](end_span)
└── docs/                   # Supplemental documentation (e.g., `AB_MATRIX.md`)[span_22](start_span)[span_22](end_span)

```
## **Build & Development Instructions**
### **Prerequisites**
 * A modern C++ compiler supporting C++20.
 * CMake (3.20 or higher).
 * Platform-specific audio dependencies (e.g., PortAudio).
### **Building with CMake**
To configure and build the project from the repository root:
```bash
mkdir build
cd build
cmake .. -DCMAKE_BUILD_TYPE=Release
cmake --build . --config Release

```
### **Automated Testing & Verification**
The repository includes automated test runners and shell scripts in the scripts/ directory to verify signal integrity, perform null tests, and run A/B processing validation:
 * Execute null tests:
   ```bash
   ./scripts/null_test_main
   
   ```
 * Run effect validation tests:
   ```bash
   ./scripts/effect_test_main
   
   ```
 * Run automated batch A/B evaluations:
   ```bash
   ./scripts/run_ab_tests.sh
   
   ```
## **Licensing & Credits**
 * **License**: Distributed under the project terms specified in the LICENSE file.
 * **Third-Party Code**: Incorporates components and algorithms licensed under open-source terms, including the Airwindows MIT License and WavMasta MIT License. Refer to CREDITS.txt and the LICENSES/ directory for full attribution details.
