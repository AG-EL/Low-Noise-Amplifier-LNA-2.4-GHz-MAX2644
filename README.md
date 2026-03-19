# Low Noise Amplifier (LNA) 2.4 GHz – MAX2644

## 📌 Overview

This project presents the design, simulation, fabrication and measurement of a **low-noise amplifier (LNA)** operating in the **2.4 GHz ISM band**, based on the **MAX2644** SiGe amplifier.

The goal was to achieve low noise figure, proper impedance matching and stable gain using **microstrip technology on Rogers 5870 substrate**.

---

## 🎯 Design Goals

* Frequency: **2.4–2.485 GHz**
* Gain: ~15 dB
* Noise Figure (target): ≤ 2.5 dB
* Input/output matching: S11, S22 < -10 dB

---

## 🧠 Key Design Decisions

### Amplifier Selection

MAX2644 was selected due to:

* relatively high gain (~17 dB)
* availability of full S-parameter and noise data
* возможность projektowania external matching network

---

### Matching Strategy

* Input: optimized for **noise matching (Γopt)**
* Output: optimized for **power transfer (50 Ω)**
* Implemented using **microstrip L-type networks**

Trade-off:

> Minimum noise figure vs. gain vs. stability

---

### Filter Integration

A **2.4–2.5 GHz band-pass filter (Johanson 2450BP15B100)** was added:

* improves selectivity
* suppresses out-of-band noise

Final topology:

> **LNA → Filter** (better NF according to Friis equation)

---

## 🧱 PCB Design

* Substrate: **Rogers 5870**
* εr = 2.4, low loss tangent
* Microstrip-based matching networks
* Full ground plane on bottom layer
* Via stitching for low inductance grounding

⚠️ PCB manufactured using **photochemical method (manual process)**

---

## 📊 Simulation Results

* Gain: ~14.8 dB
* NF: ~1.8–2 dB (simulation)
* Good matching (S11 < -20 dB)

---

## 🧪 Measured Results

### Key Observations:

* **Gain peak shifted to ~2.37 GHz**
* S-parameters also shifted toward lower frequencies
* Input matching improved after adding **series inductor (3.6 nH)**

### Measured Performance:

* Gain ≈ 10 dB (peak)
* S11, S22 ≈ -12 dB
* Noise Figure:

  * measured: **~2.9–3.9 dB**
  * expected: ~2 dB

---

## ⚠️ Discrepancies (Simulation vs Measurement)

Main causes:

### 1. PCB fabrication limitations

* photochemical process → geometry inaccuracies
* critical at 2.4 GHz (λ/20 scale effects)

### 2. Microstrip tolerances

* small changes in width/length → frequency shift
* explains shift from **2.4 GHz → 2.37 GHz**

### 3. Parasitics

* vias, solder, connectors
* manual assembly

### 4. Filter interaction

* filter slightly detuned system
* affected matching + gain peak

---

## 📸 Layout

(Simplified view for clarity – real PCB used in measurements)

---

## 🔧 What I would improve

* industrial PCB fabrication (controlled impedance)
* EM simulation instead of ideal microstrip models
* better component models (parasitics)
* precise matching (no post-tuning coil needed)

---

## 🚀 What this project demonstrates

* RF design at GHz frequencies
* impedance & noise matching
* microstrip PCB design
* practical measurement (VNA + noise figure)
* debugging real-world vs simulation mismatch

---

## 📎 Files

* schematic (AWR)
* layout (Gerber)
* measurement results
* thesis: 

---
