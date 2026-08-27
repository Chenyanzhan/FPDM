# FDPM: Frenet-Referenced Deformable Policy Model

<div align="center">

# 🚗 A Frenet-referenced Deformable Policy Model for Rule-compliant Trajectory and Control Prediction in Complex Traffic Networks

**Yanzhan Chen · Linhuan Zhong · et al.**

College of Automobile and Traffic Engineering, Nanjing Forestry University
Department of Aeronautical and Aviation Engineering, The Hong Kong Polytechnic University

<br>

[![Paper](https://img.shields.io/badge/Paper-Coming%20Soon-red?style=for-the-badge\&logo=arxiv)](#)
[![Code](https://img.shields.io/badge/Code-Coming%20Soon-blue?style=for-the-badge\&logo=github)](#)
[![CARLA](https://img.shields.io/badge/Simulator-CARLA-green?style=for-the-badge)](https://carla.org/)
[![License](https://img.shields.io/badge/License-TBD-lightgrey?style=for-the-badge)](#)

</div>

---

## 🔥 News

* **[2026]** The FDPM project repository is released.
* **[2026]** Visualization examples for trajectory and control prediction are available.
* 🚧 **Training and evaluation code is coming soon.**
* 🚧 **Pretrained models and complete experimental configurations will be released soon.**

---

## 📖 Introduction

Accurate trajectory prediction for autonomous driving requires more than forecasting future positions in a Cartesian coordinate system. Vehicle motion in complex traffic networks is jointly constrained by **lane geometry, lane connectivity, traffic signals, route intentions, surrounding vehicles, and low-level control behavior**.

We propose **FDPM**, a **Frenet-referenced Deformable Policy Model** for joint prediction of future vehicle trajectories and control commands.

Instead of treating road geometry merely as auxiliary contextual information, FDPM represents vehicle motion in a **lane-centered Frenet coordinate system**, explicitly separating longitudinal progress along the road from lateral deviation relative to candidate lane centerlines.

The proposed framework integrates:

* 🛣️ **Frenet-referenced scene representation**
* 🧩 **Deformable lane-centerline encoding**
* 🚘 **Change-point gated vehicle encoding**
* 🕸️ **Hierarchical road-road and vehicle-vehicle interaction**
* 🔄 **Bidirectional vehicle-road cross-modal attention**
* 🧠 **Mixture-of-Experts routing**
* 🎯 **Lane-conditioned probabilistic decoding**
* 🎮 **Joint trajectory and low-level control prediction**

FDPM is evaluated across **five CARLA maps** covering diverse urban roads, highways, intersections, roundabouts, and campus-like traffic environments.

---

# 🎬 Visualization

The following examples provide qualitative demonstrations of the trajectory dataset and the prediction capability of FDPM.

---

## 🌐 Trajectory Dataset Examples

<div align="center">

**Examples sampled from approximately 20,000 trajectory segments covering diverse road geometries and traffic interactions.**

</div>

<table align="center">
<tr>
<td align="center" width="25%">
<img src="images1/1.gif" width="100%"><br>
<b>Example 01</b>
</td>
<td align="center" width="25%">
<img src="images1/2.gif" width="100%"><br>
<b>Example 02</b>
</td>
<td align="center" width="25%">
<img src="images1/3.gif" width="100%"><br>
<b>Example 03</b>
</td>
<td align="center" width="25%">
<img src="images1/4.gif" width="100%"><br>
<b>Example 04</b>
</td>
</tr>

<tr>
<td align="center" width="25%">
<img src="images1/5.gif" width="100%"><br>
<b>Example 05</b>
</td>
<td align="center" width="25%">
<img src="images1/6.gif" width="100%"><br>
<b>Example 06</b>
</td>
<td align="center" width="25%">
<img src="images1/7.gif" width="100%"><br>
<b>Example 07</b>
</td>
<td align="center" width="25%">
<img src="images1/8.gif" width="100%"><br>
<b>Example 08</b>
</td>
</tr>

<tr>
<td align="center" width="25%">
<img src="images1/9.gif" width="100%"><br>
<b>Example 09</b>
</td>
<td align="center" width="25%">
<img src="images1/10.gif" width="100%"><br>
<b>Example 10</b>
</td>
<td align="center" width="25%">
<img src="images1/11.gif" width="100%"><br>
<b>Example 11</b>
</td>
<td align="center" width="25%">
<img src="images1/12.gif" width="100%"><br>
<b>Example 12</b>
</td>
</tr>
</table>

These examples illustrate the diversity of the trajectory segments used in our experiments, including vehicle motion under different **road geometries, lane configurations, turning movements, intersections, highways, and surrounding traffic conditions**.

---

## 🚗 Single-Vehicle Trajectory Prediction

<div align="center">

**Qualitative examples of single-vehicle trajectory prediction under different traffic and road conditions.**

</div>

<table align="center">

<tr>
<td align="center" width="33.33%">
<img src="images2/1.gif" width="100%"><br>
<b>Single-Agent Case 01</b>
</td>
<td align="center" width="33.33%">
<img src="images2/2.gif" width="100%"><br>
<b>Single-Agent Case 02</b>
</td>
<td align="center" width="33.33%">
<img src="images2/3.gif" width="100%"><br>
<b>Single-Agent Case 03</b>
</td>
</tr>

<tr>
<td align="center" width="33.33%">
<img src="images2/4.gif" width="100%"><br>
<b>Single-Agent Case 04</b>
</td>
<td align="center" width="33.33%">
<img src="images2/5.gif" width="100%"><br>
<b>Single-Agent Case 05</b>
</td>
<td align="center" width="33.33%">
<img src="images2/6.gif" width="100%"><br>
<b>Single-Agent Case 06</b>
</td>
</tr>

</table>

FDPM generates **multimodal future trajectories conditioned on lane structure and traffic context**, while simultaneously predicting behavior-related control commands. The Frenet-referenced representation enables the model to distinguish between **longitudinal progress** and **lateral motion**, particularly in curved roads, intersections, and lane-changing situations.

---

## 🚙🚕 Multi-Vehicle Trajectory Prediction

<div align="center">

**Joint visualization of trajectory prediction in multi-vehicle interaction scenarios.**

</div>

<table align="center">

<tr>
<td align="center" width="50%">
<img src="images3/1.gif" width="100%"><br>
<b>Multi-Agent Case 01</b>
</td>
<td align="center" width="50%">
<img src="images3/2.gif" width="100%"><br>
<b>Multi-Agent Case 02</b>
</td>
</tr>

<tr>
<td align="center" width="50%">
<img src="images3/3.gif" width="100%"><br>
<b>Multi-Agent Case 03</b>
</td>
<td align="center" width="50%">
<img src="images3/4.gif" width="100%"><br>
<b>Multi-Agent Case 04</b>
</td>
</tr>

</table>

These examples demonstrate FDPM's capability to model **vehicle-vehicle interactions and vehicle-road dependencies** in complex traffic environments. Hierarchical interaction modeling allows the predicted motions of neighboring vehicles to remain consistent with both surrounding traffic behavior and the underlying road topology.

---

# 🧠 Method Overview

FDPM formulates trajectory prediction from a **transportation-oriented perspective**, where the road network serves not only as contextual information but also as the geometric reference of vehicle motion.

The overall architecture consists of the following major components:

### 1. Frenet-Referenced Scene Representation

Vehicle states and lane-centerline information are transformed into a local Frenet coordinate system. Vehicle motion is represented by longitudinal progress along a candidate lane and lateral deviation from the corresponding lane centerline.

This representation reduces irrelevant geometric variations caused by curved roads and provides an explicit description of lane-following and lane-changing behavior.

### 2. Deformable Lane-Centerline Encoder

A deformable attention mechanism is introduced to encode vectorized lane centerlines. Instead of uniformly attending to all lane points, each lane feature adaptively attends to informative neighboring locations, improving the representation of local geometry and topology.

### 3. Change-Point Gated Vehicle Encoder

The vehicle encoder explicitly emphasizes behavior transitions in historical motion, including:

* acceleration and deceleration,
* braking,
* lateral displacement,
* steering changes,
* lane-change onset.

This allows behaviorally important temporal changes to receive greater attention during historical-state encoding.

### 4. Hierarchical Interaction Modeling

FDPM progressively models:

**Road ↔ Road interaction**
→ lane connectivity and road topology

**Vehicle ↔ Vehicle interaction**
→ dynamic multi-agent dependencies

**Vehicle ↔ Road interaction**
→ bidirectional cross-modal reasoning between traffic participants and road structures

### 5. Mixture-of-Experts Routing

A Mixture-of-Experts module dynamically routes heterogeneous traffic states toward specialized prediction experts, allowing different experts to capture distinct driving regimes and road configurations.

### 6. Lane-Conditioned Probabilistic Decoder

The decoder produces multiple candidate future trajectories conditioned on feasible lane structures and predicts corresponding uncertainty, route probability, and low-level vehicle control behavior.

---

# ✨ Highlights

### 🛣️ Road-referenced motion representation

Unlike conventional Cartesian prediction, FDPM uses lane centerlines as the reference coordinate system of vehicle motion, explicitly distinguishing along-lane progress from lateral deviation.

### 🔗 Topology-aware prediction

Road-road attention learns meaningful lane connectivity and reachability information, improving route-consistent prediction at intersections, roundabouts, and complex lane structures.

### 🚘 Interaction-aware motion forecasting

Hierarchical vehicle-vehicle and vehicle-road interactions enable FDPM to model surrounding traffic and map constraints jointly.

### 🎛️ Trajectory + control prediction

FDPM goes beyond position-only forecasting by jointly predicting future trajectories and normalized control commands as behavior descriptors.

### 🚦 Rule-compliant prediction

The evaluation considers not only conventional displacement errors but also:

* **Average Displacement Error (ADE)**
* **Final Displacement Error (FDE)**
* **Miss Rate (MR)**
* **Off-Road Probability (ORP)**
* **Traffic-Rule Violation Rate (VR)**

### 🔁 Closed-loop robustness

FDPM is additionally evaluated through continuous rolling prediction, where prediction errors are recursively propagated through repeated prediction-execution cycles.

Closed-loop experiments evaluate cumulative displacement error and distance-to-collision to investigate long-horizon prediction stability.

---

# 🌍 Experimental Environments

Experiments are conducted across **five CARLA maps** containing diverse traffic environments, including:

| Environment                 | Representative Characteristics                    |
| :-------------------------- | :------------------------------------------------ |
| 🏙️ Urban roads             | Dense intersections and complex lane connectivity |
| 🚦 Signalized intersections | Traffic-light-dependent motion                    |
| 🛣️ Highways                | High-speed longitudinal motion                    |
| 🔄 Roundabouts              | Strong topology and interaction constraints       |
| 🏫 Campus-like networks     | Irregular local road structures                   |

The evaluation includes:

* Quantitative comparison
* Qualitative trajectory prediction
* Control prediction
* Ablation study
* Expert specialization analysis
* Road-topology reconstruction
* Signalized-intersection behavior analysis
* Closed-loop rolling prediction
* Closed-loop stress testing

---

# 📊 Main Findings

The experiments indicate that FDPM improves trajectory prediction from three complementary perspectives:

**Geometric Accuracy**

FDPM achieves strong performance on conventional displacement-based trajectory prediction metrics.

**Behavioral Feasibility**

Lane-referenced representation and structured interaction modeling reduce off-road predictions and traffic-rule violations.

**Closed-loop Stability**

Under continuous prediction-execution feedback, FDPM exhibits slower error accumulation and stronger long-horizon robustness than representative prediction baselines.

---

# 🛠️ Code

> 🚧 **Code is coming soon.**

The complete implementation will be released after the paper publication process.

The repository will include:

* [ ] Data preprocessing
* [ ] Frenet coordinate transformation
* [ ] FDPM model implementation
* [ ] Deformable lane-centerline encoder
* [ ] Change-point gated vehicle encoder
* [ ] Interaction modules
* [ ] Mixture-of-Experts routing
* [ ] Lane-conditioned decoder
* [ ] Training scripts
* [ ] Evaluation scripts
* [ ] Visualization tools
* [ ] Pretrained checkpoints
* [ ] Closed-loop CARLA evaluation

⭐ **Please star this repository to receive future updates.**

---


# 📝 Citation

If you find this project useful for your research, please consider citing our work.

```bibtex
@article{chen2026fdpm,
  title   = {A Frenet-referenced deformable policy model for rule-compliant trajectory and control prediction in complex traffic networks},
  author  = {Chen, Yanzhan and Zhong, Linhuan and others},
  year    = {2026}
}
```

The complete citation information will be updated after publication.

---

# 🙏 Acknowledgement

This project is developed using the **CARLA autonomous driving simulator** and builds upon the broader research community in vectorized trajectory prediction, graph-based interaction modeling, map-aware motion forecasting, and autonomous-driving simulation.

We thank the developers and researchers who have contributed to these open-source platforms and research tools.

---

<div align="center">

### 🚗 FDPM

**Frenet-referenced · Interaction-aware · Rule-compliant · Closed-loop evaluated**

<br>

⭐ **If you find this project interesting, please consider giving it a star!** ⭐

</div>
