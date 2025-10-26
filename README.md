# **Stress Triggered Aging Recorder (STAR)**  
### *A molecular simulation framework to measure and visualize healthspan from cellular stress history*

---

## **Overview**
The **Stress Triggered Aging Recorder (STAR)** models how engineered biological systems could record cellular stress over time, providing a digital snapshot of biological aging. While the simulation operates at the **cellular level**, its implications extend much further.  

Cells form tissues, tissues form organs, and together they define the body’s overall functional state. By understanding how individual cells accumulate and respond to stress, STAR provides insight into how organs age, giving a measure of how the **healthspan** of the entire organism changes over time.

---

## **Background and Motivation**
The hackathon challenge asked:  
> **"How can we improve healthspan?"**

We realized that before we can improve healthspan, we must first be able to **measure it**. Lifespan is easy to quantify because it simply measures how long we live. Healthspan, however, reflects how long we stay healthy. Currently, there is no reliable molecular tool that tracks the gradual accumulation of stress and damage that drives aging.

STAR addresses this gap by simulating a **synthetic biological recorder** that encodes cellular stress directly into DNA. Through repeated stress pulses, the recorder accumulates "edits," forming a **molecular signature of aging** that can be computationally analyzed to infer biological age.

---

## **Core Concept**
At its core, STAR simulates a network of biological "sensors," each representing a key aging-related stress pathway, and links them to **synthetic DNA cassettes** capable of storing memory through base editing events.  

These stress sensors include:
- **DDR** – DNA Damage Response  
- **ROS** – Reactive Oxygen Species  
- **p16** – Cell cycle arrest and senescence  
- **NFκB** – Inflammation signaling  
- **HSF1** – Heat shock and proteotoxic stress  

Every stress pulse triggers probabilistic edits in the cassettes, mimicking how cumulative stress might leave molecular scars over time.

---

## **Technical Architecture**

### **1. Input Layer – Plasmid Upload**
Users can upload one or more plasmid files (`.gb` or `.fasta`).  
Each plasmid represents a synthetic construct into which a **stress-sensing cassette** is integrated.

### **2. Synthetic Cassette Generator**
A custom DNA cassette is generated for each stress sensor:
- Randomized sequence of defined length  
- Contains editable cytosines (`C`) that represent potential "memory" sites  
- Each stress pathway receives its own cassette

### **3. Stress Simulation Engine**
The system simulates a series of **stress pulses** (like time points or environmental challenges).  
During each pulse:
- Each sensor is activated with a random probability  
- If activated, one or more cytosines are "edited" (mimicking base editing events)

### **4. Data Recording Layer**
Edits are stored cumulatively, creating a digital-like memory within each cassette.  
The code tracks these over multiple cycles, simulating how a real biological recorder would store stress exposure over time.

### **5. Analytical Layer**
After simulation, the model:
- Normalizes the edit counts (0–1 scale)  
- Computes the **Biological Age Index (BAI)** as a weighted sum of all sensors  
- Outputs a time-series dataset showing how BAI evolves

### **6. Visualization Layer**
Two core plots are generated:
1. **BAI Over Time:** A bar chart showing cumulative biological aging across samples.  
2. **Sensor Contribution Chart:** A stacked bar plot showing how each stress pathway contributes to overall aging.

---

## **How It Connects to Healthspan**
Although STAR operates at the **cellular scale**, its design mirrors how real biological systems age:
- As **cells experience stress**, STAR records these molecular events.  
- As **tissues age**, the accumulation of these stressed cells alters organ function.  
- As **organs decline**, healthspan shortens.  

Thus, by modeling cellular stress accumulation, STAR provides a **proxy measure** for overall organismal healthspan.  

This makes STAR not just a simulation, but a **conceptual bridge** between synthetic biology, bioinformatics, and longevity research.

---

## **Features**
✅ Multi-sensor stress simulation  
✅ Synthetic DNA cassette generation  
✅ Base-editing logic modeling  
✅ Weighted Biological Age Index (BAI) computation  
✅ Visualized outputs with sensor contribution breakdown  
✅ Multi-file plasmid integration 

---

## **How to Run**
1. Install dependencies:
   ```bash
   pip install biopython matplotlib pandas numpy
