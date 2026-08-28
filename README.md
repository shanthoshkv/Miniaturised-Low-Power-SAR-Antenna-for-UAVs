# Miniaturised Low-Power SAR Antenna for UAVs

### L-Band Microstrip Patch Antenna Design for UAV-Based Synthetic Aperture Radar

This project presents the **design and theoretical analysis of a compact microstrip patch antenna for a miniaturised, low-power Synthetic Aperture Radar (SAR) system intended for UAV platforms**.

The motivation behind the project is straightforward. SAR provides high-resolution remote sensing independent of daylight and, within suitable operating conditions, weather. However, conventional SAR systems can require large antennas, significant power, and substantial payload capacity.

Putting SAR onto a small UAV changes the engineering problem.

The antenna now needs to be:

* Compact
* Lightweight
* Low profile
* Efficient
* Sufficiently directional
* Compatible with limited UAV payload capacity
* Suitable for low-power RF systems
* Practical to manufacture

This project explores that tradeoff through the design of an **L-band microstrip patch antenna operating around 2 GHz**, with the antenna geometry and substrate selected specifically with UAV integration in mind.

The final theoretical design uses **RT/Duroid 6006** as the substrate and produces a compact antenna with dimensions of approximately:

```text
40.09 mm × 27.0 mm
```

Theoretical analysis predicts a resonant frequency of approximately:

```text
1.945 GHz
```

with an expected gain of:

```text
6 to 8 dBi
```

and radiation efficiency above:

```text
96%
```

The project also extends beyond the antenna itself by examining the **SAR link budget and UAV power budget**, connecting the antenna design to the requirements of an actual airborne sensing system.

---

# Project Website

**Website:** https://aboutkvs.vercel.app/

---

# Why UAV-Based SAR?

Synthetic Aperture Radar is particularly valuable for remote sensing because it can produce high-resolution imagery without depending on optical visibility.

Traditional SAR systems are often associated with:

* Satellites
* Large aircraft
* Military reconnaissance platforms

The development of compact electronics and digital signal processing has made it increasingly practical to investigate smaller UAV-based SAR systems.

UAVs offer several advantages:

* Rapid deployment
* Flexible flight paths
* Lower operating costs
* Frequent revisits
* Reduced human exposure to hazardous environments
* Mission-specific flight planning

However, miniaturising SAR introduces several constraints.

A UAV has limited:

```text
Payload Mass
     +
Available Power
     +
Physical Space
```

The antenna therefore becomes an important part of the overall system-level design problem.

---

# Design Problem

The central engineering problem can be expressed as:

> **How can an antenna be made small enough for a UAV while still providing the electromagnetic performance required by an L-band SAR system?**

The project focuses on an operating frequency of:

```text
2 GHz
```

This places the design in the L-band region.

The antenna must balance:

```text
┌──────────────────────────────┐
│       UAV Constraints        │
├──────────────────────────────┤
│ Small Size                   │
│ Low Mass                     │
│ Low Power                    │
│ Low Profile                  │
│ Manufacturability            │
└──────────────┬───────────────┘
               │
               ▼
       Antenna Optimization
               │
               ▼
┌──────────────────────────────┐
│ Electromagnetic Performance  │
├──────────────────────────────┤
│ Resonant Frequency           │
│ Gain                         │
│ Bandwidth                    │
│ Efficiency                   │
│ Radiation Pattern            │
└──────────────────────────────┘
```

The project therefore treats antenna design as a compromise between electromagnetic performance and aerospace platform constraints.

---

# Project Objectives

The study was built around six primary objectives:

1. Design a microstrip patch antenna operating at 2 GHz for UAV-based SAR.
2. Select an appropriate substrate based on electromagnetic and manufacturing considerations.
3. Develop mathematical models for antenna dimensional calculations.
4. Analyse gain, bandwidth, and radiation characteristics.
5. Validate the design through theoretical analysis and parameter optimisation.
6. Provide recommendations for future fabrication and experimental testing.

---

# Design Workflow

The complete design process follows:

```text
SAR System Requirements
          ↓
UAV Constraints
          ↓
Operating Frequency Selection
          ↓
Substrate Comparison
          ↓
Substrate Thickness Selection
          ↓
Patch Dimension Calculations
          ↓
Feed / Geometry Design
          ↓
Electromagnetic Analysis
          ↓
Performance Estimation
          ↓
Thermal Analysis
          ↓
Power Budget
          ↓
Link Budget
          ↓
Final Antenna Design
          ↓
Future Fabrication + Testing
```

The workflow combines electromagnetic theory with practical aerospace integration considerations.

---

# SAR Fundamentals

Synthetic Aperture Radar uses coherent signal processing to achieve high-resolution imaging.

Unlike optical systems, SAR does not fundamentally depend on sunlight for image acquisition.

This makes it useful for applications such as:

* Earth observation
* Environmental monitoring
* Agricultural assessment
* Disaster monitoring
* Ocean observation
* Reconnaissance

The move toward UAV platforms creates an opportunity to deploy SAR closer to the area of interest while reducing platform size and operational complexity.

The antenna is therefore a critical component because it directly influences:

* Radiation
* Gain
* Beamwidth
* Bandwidth
* Power requirements
* Physical integration

---

# Why Microstrip Patch Antennas?

Microstrip patch antennas are particularly attractive for UAV applications because they provide several characteristics that align well with small airborne platforms.

### Low Profile

The planar geometry reduces the physical envelope of the antenna.

### Lightweight

The antenna adds relatively little payload mass compared with larger antenna architectures.

### UAV Integration

A planar antenna can be integrated into the UAV structure.

### Manufacturing

Microstrip antennas can be fabricated using PCB-style manufacturing processes.

### Cost

The manufacturing process is comparatively accessible.

### Polarization

The geometry can be configured to provide the required polarization characteristics.

These properties make microstrip patch antennas a practical candidate for miniaturised UAV-SAR systems.

---

# Substrate Selection

Substrate selection is one of the most important decisions in the design.

The substrate affects:

* Resonant frequency
* Physical dimensions
* Radiation efficiency
* Bandwidth
* Dielectric losses
* Manufacturing feasibility
* Thermal behaviour

After comparing candidate materials, the project selected:

## RT/Duroid 6006

with:

```text
Relative Dielectric Constant = 6.0
Loss Tangent                  = 0.0019
Substrate Thickness           = 3.2 mm
```

The relatively high dielectric constant helps reduce the physical size of the patch, which is useful for a compact UAV payload.

The low loss tangent also supports efficient electromagnetic operation.

## The report identifies RT/Duroid 6006 as the preferred material based on its combination of electrical properties, manufacturing feasibility, and cost considerations.

# Antenna Design

The antenna is based on a rectangular microstrip patch configuration.

The final design parameters are:

| Parameter                      |          Value |
| ------------------------------ | -------------: |
| Operating frequency            |        2.0 GHz |
| Patch length                   |        27.0 mm |
| Patch width                    |       40.09 mm |
| Substrate thickness            |         3.2 mm |
| Substrate                      | RT/Duroid 6006 |
| Dielectric constant            |            6.0 |
| Loss tangent                   |         0.0019 |
| Effective dielectric constant  |           5.29 |
| Extension length               |        1.40 mm |
| Effective length               |        29.8 mm |
| Theoretical resonant frequency |      1.945 GHz |
| Expected bandwidth             |           3.3% |
| Predicted gain                 |     6 to 8 dBi |
| Radiation efficiency           |           >96% |

These values represent the final theoretical antenna design reported in the study.

---

# Mathematical Design

The patch dimensions were obtained using electromagnetic design equations rather than arbitrary geometric optimisation.

The methodology accounts for the effect of the dielectric substrate on the effective wavelength and therefore on the physical patch dimensions.

The basic design process is:

```text
Operating Frequency
        ↓
Free-Space Wavelength
        ↓
Dielectric Properties
        ↓
Effective Dielectric Constant
        ↓
Patch Width
        ↓
Fringing-Field Correction
        ↓
Effective Patch Length
        ↓
Physical Patch Length
```

This allows the physical antenna dimensions to be derived from the desired operating frequency and substrate properties.

---

# Effective Dielectric Constant

A microstrip patch does not behave as though all of its electromagnetic fields are contained entirely inside the dielectric.

Some of the fields extend into the surrounding air.

This creates an effective dielectric constant that lies between the substrate dielectric constant and that of free space.

For the selected substrate, the calculated effective dielectric constant is:

```text
εeff = 5.29
```

This value is then used when determining the effective electrical length of the patch.

---

# Fringing Fields

The open edges of a microstrip patch cause electromagnetic fields to extend beyond the physical dimensions of the patch.

This is known as the fringing-field effect.

As a result:

```text
Effective Electrical Length
            >
Physical Patch Length
```

The design accounts for this through an extension length of approximately:

```text
1.40 mm
```

giving an effective patch length of:

```text
29.8 mm
```

This correction is important when predicting the resonant frequency of a compact patch antenna.

---

# Resonant Frequency

The target operating frequency is:

```text
2.0 GHz
```

The final theoretical design predicts:

```text
1.945 GHz
```

The report considers this to be in good agreement with the target frequency and uses the result as evidence that the analytical design methodology produces a suitable initial antenna geometry.

The remaining difference between the nominal target and theoretical result also highlights why electromagnetic simulation and physical measurement are important in the next stage of development.

---

# Antenna Performance Targets

The design was evaluated against several performance requirements.

| Parameter          |     Target |
| ------------------ | ---------: |
| Resonant frequency |    2.0 GHz |
| Return loss        |   < -20 dB |
| Gain               | 6 to 8 dBi |
| Bandwidth          |    >60 MHz |
| Efficiency         |       >90% |

The report proposes measurement methods for each parameter, including:

* S11 measurement
* Vector Network Analyzer measurements
* Radiation-pattern integration
* Wheeler cap method

These form the basis of a future experimental validation campaign.

---

# Radiation Performance

The antenna is intended to provide sufficient directivity and gain for integration into a compact SAR payload.

The predicted gain is:

```text
6 to 8 dBi
```

The theoretical radiation efficiency is expected to exceed:

```text
96%
```

The design therefore aims to maintain useful electromagnetic performance while keeping the physical footprint small enough for UAV integration.

---

# Bandwidth

The theoretical design predicts a fractional bandwidth of approximately:

```text
3.3%
```

At a nominal frequency of 2 GHz, this corresponds to a bandwidth on the order of tens of megahertz.

The project establishes a future verification target of:

```text
>60 MHz
```

with S11 analysis proposed as the measurement method.

---

# Thermal Analysis

Because the antenna is intended for an airborne platform, environmental effects cannot be ignored.

UAV operation exposes the antenna and substrate to:

* Temperature variations
* Vibration
* Aerodynamic loading
* Manufacturing tolerances

The project therefore includes thermal considerations as part of the design methodology.

The reported analysis also considers the temperature dependence of the antenna's resonant behaviour.

A temperature coefficient of approximately:

```text
45 kHz/°C
```

is reported for the design.

This provides an indication of how changes in operating temperature can shift the antenna's resonant characteristics.

---

# UAV SAR Link Budget

The project extends beyond the antenna itself by considering the RF link budget of the overall SAR system.

The basic received-power relationship is expressed as:

```text
Pr = Pt + Gt + Gr
     - Lpath
     - Latmospheric
     - Lsystem
```

where the system accounts for:

* Transmit power
* Transmit antenna gain
* Receive antenna gain
* Free-space path loss
* Atmospheric losses
* System losses

For a representative UAV altitude of:

```text
1000 m
```

and an operating frequency of:

```text
2 GHz
```

the reported free-space path loss is approximately:

```text
96.5 dB
```

This demonstrates the importance of antenna gain and overall RF efficiency in maintaining a viable airborne radar link.

---

# UAV SAR Power Budget

Power availability is another major constraint for small UAV platforms.

The project therefore estimates the average power requirement of the SAR system.

| Component           |    Power | Duty Cycle |
| ------------------- | -------: | ---------: |
| RF Transmitter      |     50 W |        10% |
| Receiver            |     15 W |        90% |
| Signal Processing   |     25 W |       100% |
| Antenna             |  Passive |        0 W |
| Control Electronics |      5 W |       100% |
| **Total Average**   | **35 W** |            |

The antenna itself is passive and therefore does not consume electrical power.

The power budget provides a system-level context for the antenna design by showing how the RF subsystem interacts with the limited power available on a UAV.

---

# System-Level Architecture

The antenna is only one component of the proposed UAV-SAR system.

A simplified architecture is:

```text
                    UAV
                     │
       ┌─────────────┼─────────────┐
       │             │             │
       ▼             ▼             ▼
   Navigation    Processing      Power
       │             │             │
       │             ▼             │
       │        SAR Electronics    │
       │             │             │
       │             ▼             │
       └────────── RF System ──────┘
                     │
                     ▼
               Patch Antenna
                     │
                     ▼
              Ground / Target
```

The antenna must therefore fit within the mechanical, electrical, and operational constraints of the entire aircraft.

---

# Design Tradeoffs

The project highlights several important antenna-design tradeoffs.

## Size vs Frequency

Increasing the dielectric constant can reduce the physical size of the patch, but dielectric properties also affect bandwidth and efficiency.

## Gain vs Beamwidth

Increasing directivity can improve radar performance but narrows the radiation pattern.

## Thickness vs Bandwidth

Substrate thickness influences bandwidth and radiation characteristics while also affecting the physical profile.

## Performance vs UAV Payload

An antenna that performs well electromagnetically may not necessarily be suitable if it introduces excessive mass, size, or aerodynamic penalties.

## Electrical Performance vs Manufacturability

A theoretically optimized geometry still needs to be practical to fabricate and integrate.

The project therefore treats antenna design as an engineering optimisation problem rather than simply solving for patch dimensions.

---

# Design Methodology

The project can be summarized through the following workflow:

```text
                  REQUIREMENTS
                       │
                       ▼
              UAV SAR Constraints
                       │
                       ▼
             Select 2 GHz L-Band
                       │
                       ▼
              Compare Substrates
                       │
                       ▼
              Select RT/Duroid 6006
                       │
                       ▼
             Calculate εeff
                       │
                       ▼
             Calculate Patch W
                       │
                       ▼
             Calculate Effective L
                       │
                       ▼
             Apply Fringing Correction
                       │
                       ▼
               Final Dimensions
                       │
                       ▼
              Performance Analysis
                       │
              ┌────────┼────────┐
              ▼        ▼        ▼
            Gain    Bandwidth  Efficiency
              │        │        │
              └────────┼────────┘
                       ▼
                Thermal Analysis
                       │
                       ▼
                 Link Budget
                       │
                       ▼
                 Power Budget
                       │
                       ▼
              Future Fabrication
```

---

# Performance Verification

The project proposes a practical test matrix for future physical validation.

### Resonant Frequency

Target:

```text
2.0 GHz ± 20 MHz
```

Measurement:

```text
S11 using a Vector Network Analyzer
```

### Return Loss

Target:

```text
< -20 dB
```

Measurement:

```text
VNA
```

### Gain

Target:

```text
6 to 8 dBi
```

Measurement:

```text
Radiation-pattern integration
```

### Bandwidth

Target:

```text
>60 MHz
```

Measurement:

```text
S11 analysis
```

### Efficiency

Target:

```text
>90%
```

Measurement:

```text
Wheeler cap method
```

This provides a clear path from theoretical design to experimental validation.

---

# Final Design

The final theoretical antenna has a compact footprint:

```text
40.09 mm × 27.0 mm
```

and uses:

```text
RT/Duroid 6006
```

with a thickness of:

```text
3.2 mm
```

The calculated resonant frequency is:

```text
1.945 GHz
```

while the target system frequency is:

```text
2.0 GHz
```

The design predicts:

```text
Gain       : 6 to 8 dBi
Efficiency : >96%
Bandwidth  : 3.3%
```

The final dimensions represent the project's attempt to balance the electromagnetic requirements of SAR with the physical constraints imposed by UAV platforms.

---

# Engineering Significance

The project is interesting because the antenna cannot be considered independently from the aircraft.

A UAV-SAR antenna has to satisfy several competing requirements simultaneously:

```text
             ELECTROMAGNETICS
                    │
                    ▼
          ┌───────────────────┐
          │     ANTENNA       │
          └───────────────────┘
             ▲      ▲      ▲
             │      │      │
          UAV Size  Power  Mass
             │      │      │
             └──────┼──────┘
                    │
                    ▼
             SYSTEM INTEGRATION
```

The project therefore connects:

* Electromagnetic theory
* Antenna design
* Materials engineering
* RF systems
* Power budgeting
* Thermal analysis
* Aerospace integration

into a single design problem.

---

# Applications

A compact UAV-SAR antenna of this type could support systems intended for:

### Ocean Monitoring

The project specifically considers ocean surface monitoring as one application.

### Disaster Response

SAR can provide useful information when optical imaging is limited.

### Environmental Monitoring

UAV-based sensing can provide localized observations.

### Agriculture

Frequent UAV deployment can provide high temporal resolution.

### Reconnaissance

Compact SAR systems can provide remote sensing capabilities without requiring large aircraft.

The report identifies environmental monitoring, disaster response, agricultural assessment, and reconnaissance as relevant application areas for UAV-based SAR.

---

# What I Learned

The most important lesson from this project was that **antenna design is not just about calculating the patch dimensions**.

The dimensions are only the starting point.

Once the antenna is intended for a UAV, other questions immediately become important:

* How much space does it occupy?
* How much does the substrate affect efficiency?
* What happens when the temperature changes?
* How much gain is actually available?
* What bandwidth is required?
* How much RF power does the system need?
* What is the link loss at operational altitude?
* Can the antenna be manufactured accurately?
* Can it survive the UAV operating environment?

That pushed the project from a basic electromagnetic calculation exercise toward a more complete **aerospace RF system design study**.

---

# Future Work

The current work is primarily theoretical, providing a design framework and calculated performance characteristics.

The next stage would be experimental validation.

## Physical Fabrication

Fabricate the RT/Duroid 6006 antenna using the calculated geometry.

## VNA Characterisation

Measure:

* S11
* Resonant frequency
* Return loss
* Bandwidth

and compare the measurements with the theoretical prediction.

## Anechoic Chamber Testing

Measure:

* Radiation pattern
* Gain
* Beamwidth
* Directivity

## Temperature Testing

Characterise resonant-frequency shift across the expected UAV operating temperature range.

## Manufacturing Tolerance Analysis

Investigate how fabrication deviations affect:

* Resonant frequency
* Return loss
* Bandwidth
* Gain

## UAV Integration

Evaluate the effect of:

* UAV body materials
* Mounting position
* Ground plane
* Nearby electronics
* Aerodynamic configuration

on antenna performance.

## SAR Imaging Validation

The final stage would be integrating the antenna into a complete SAR payload and evaluating actual imaging performance.

---

# Future System Extensions

The report identifies several possible directions for further development:

* Advanced beam-forming
* Multi-frequency operation
* Adaptive antenna systems
* Dynamic beam steering
* AI-based autonomous target recognition

These could eventually transform the antenna from a fixed passive element into part of a more capable intelligent sensing platform.

---

# Project Structure

A suitable repository structure would be:

```text
uav-sar-antenna/
│
├── README.md
│
├── theory/
│   ├── patch_dimensions/
│   ├── effective_dielectric_constant/
│   ├── resonant_frequency/
│   └── fringing_fields/
│
├── substrate/
│   ├── material_comparison/
│   └── rt_duroid_6006/
│
├── antenna_design/
│   ├── geometry/
│   ├── dimensions/
│   └── feed_design/
│
├── analysis/
│   ├── gain/
│   ├── bandwidth/
│   ├── efficiency/
│   ├── radiation_pattern/
│   └── thermal/
│
├── system_analysis/
│   ├── link_budget/
│   └── power_budget/
│
├── validation/
│   ├── vna/
│   ├── radiation_pattern/
│   └── efficiency/
│
└── documentation/
    └── report.pdf
```

---

# Technical Summary

| Category                       | Design                             |
| ------------------------------ | ---------------------------------- |
| Application                    | UAV-based Synthetic Aperture Radar |
| Antenna Type                   | Microstrip Patch                   |
| Operating Frequency            | 2 GHz                              |
| Band                           | L-band                             |
| Substrate                      | RT/Duroid 6006                     |
| Dielectric Constant            | 6.0                                |
| Loss Tangent                   | 0.0019                             |
| Substrate Thickness            | 3.2 mm                             |
| Patch Width                    | 40.09 mm                           |
| Patch Length                   | 27.0 mm                            |
| Effective Length               | 29.8 mm                            |
| Effective Dielectric Constant  | 5.29                               |
| Extension Length               | 1.40 mm                            |
| Theoretical Resonant Frequency | 1.945 GHz                          |
| Expected Bandwidth             | 3.3%                               |
| Predicted Gain                 | 6 to 8 dBi                         |
| Predicted Efficiency           | >96%                               |
| UAV Power Budget               | 35 W average                       |
| Example UAV Altitude           | 1000 m                             |
| Free-Space Path Loss           | 96.5 dB                            |

The values above are based on the theoretical design and system analysis presented in the project report.

---

# Conclusion

This project developed a theoretical design methodology for a **compact L-band microstrip patch antenna intended for miniaturised UAV-based SAR systems**.

The final design uses RT/Duroid 6006 and achieves a compact footprint while targeting the electromagnetic requirements of a 2 GHz SAR system.

The study goes beyond basic patch calculations by considering:

```text
Antenna Geometry
       +
Substrate Selection
       +
Electromagnetic Performance
       +
Thermal Behaviour
       +
Manufacturing Considerations
       +
Link Budget
       +
Power Budget
       +
UAV Integration
```

The resulting design provides a foundation for physical fabrication, VNA characterisation, radiation-pattern measurements, and eventual integration into a complete UAV-SAR payload.

The broader goal is to demonstrate how conventional antenna theory can be adapted to the very different constraints of **small airborne sensing platforms**.

---

# Team

**Sanskar Verma**
1RV23AS049

**Sarthak Sharma**
1RV23AS050

**Shambhavi Shukla**
1RV23AS052

**Shanthosh K V**
1RV23AS053

**Department of Aerospace Engineering**
RV College of Engineering, Bengaluru

The project was completed as an experiential learning project for the Fundamentals of Avionics course during 2024-2025, under the guidance of Dr. H. V. Kumaraswamy and Dr. Nagaraju.

---

# Project Website

Explore the project and other aerospace engineering work:

**https://aboutkvs.vercel.app/**

---

## License

© 2025 Project Team. All rights reserved.
