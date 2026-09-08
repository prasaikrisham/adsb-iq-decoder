# ADS-B IQ Decoder

Real-time ADS-B / Mode S decoder built from raw RTL-SDR IQ samples, not a wrapper around an existing decoder (e.g. dump1090). Every stage of the signal-processing pipeline is implemented directly: preamble detection, PPM demodulation, Mode S frame parsing, and CRC validation.

## Status

🚧 Early development. The core capture and signal-processing pipeline is being built first; see the roadmap below.

## Pipeline

```
RTL-SDR → Raw IQ Samples → Signal Processing → 1090 MHz Preamble Detection
        → PPM Demodulation → Mode S Frame Parsing → CRC Validation
        → Aircraft Data → Visualization
```

## What I Implemented

- [ ] IQ sample capture & processing
- [ ] Signal filtering / preprocessing
- [ ] ADS-B / Mode S preamble detection
- [ ] PPM demodulation
- [ ] Mode S frame parsing (ICAO address, message type, callsign, altitude, position)
- [ ] CRC validation
- [ ] Aircraft data extraction
- [ ] Real-time visualization (live aircraft map, decoder stats)
- [ ] Performance profiling and targeted C/C++ optimization of hot paths

## What I Used

- RTL-SDR hardware interface
- Python / NumPy / SciPy for prototyping and signal analysis
- C/C++ only where profiling identifies an actual bottleneck
- Standard plotting/mapping libraries for visualization

## Tech Stack

| Layer | Tools |
|---|---|
| Hardware | RTL-SDR dongle, 1090 MHz antenna |
| Prototyping | Python, NumPy, SciPy, Matplotlib |
| Optimization | C/C++ |
| Visualization | Python plotting → live map/GUI |
| Dev | Git/GitHub, Linux, unit/integration tests |

## Development Philosophy

Build a correct, understandable Python implementation first. Profile it, identify the actual performance bottleneck, and move that hot path into C/C++.

## Signal-Stage Visualizations (planned)

Raw IQ → Magnitude → Filtered Signal → Detected Preamble → PPM Pulses → Decoded Bits → Mode S Frame

## Setup

Instructions will be added once the capture pipeline is functional.

## License

MIT
