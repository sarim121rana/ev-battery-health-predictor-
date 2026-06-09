# EV Battery Health Predictor 🔋🏎️

An end-to-end Machine Learning web application designed to predict the remaining capacity and State of Health (SoH) of Electric Vehicle (EV) Lithium-ion batteries. This project is built using a **Random Forest Regressor** trained on the benchmark **NASA Li-ion Battery Dataset**, providing highly realistic and physics-aligned predictions.

---

## 🚀 Live Demo
🌐 **Web Application Link:** [ https://exageg3ye5pafwm6odpngu.streamlit.app/]

---

## 📊 Project Overview
Battery degradation in Electric Vehicles is highly non-linear and depends on multiple operational factors. This project aims to solve the problem of underfitting and flat predictions often found in basic models by training a fine-tuned Random Forest model on dynamic sensor data. 

The app successfully models real-world battery phenomena like the **Capacity Recovery Effect** (where voltage relaxes and capacity temporarily rises under low/zero load conditions) and **Linear Degradation Phases**.

### Key Features:
* **Interactive UI:** Dynamic sliders to adjust real-time sensor parameters.
* **Smart Scaling:** Real-world mapping where the absolute worst-case scenario dynamically flags a **Red/Yellow Alert** instead of displaying unrealistic high health scores.
* **Lightweight & Production-Ready:** Optimized model size (< 25 MB) ensuring instant deployment and zero lag on cloud servers.

---

## 📑 Dataset Details
* **Source:** NASA Prognostics Center of Excellence (Li-ion Battery Dataset).
* **Data Scale:** Over 7.6 Lakh data rows capturing continuous charging and discharging cycles.
* **Target Features:** `Cycle_Num`, `Voltage`, `Current`, and `Temperature`.
* **Output:** Remaining `Capacity` (Ah) and `State of Health` (SoH %).

---

## 🛠️ System Architecture & Tech Stack
* **Language:** Python
* **Machine Learning:** Scikit-Learn (Random Forest Regressor)
* **Data Processing:** Pandas, NumPy
* **Deployment/UI:** Streamlit Cloud
* **Version Control:** GitHub

---

## 📈 Sample Test Cases For Evaluation

To test the reliability and realistic behavior of the model, you can evaluate the following extreme scenarios on the web interface:

### 🍏 1. Brand New Battery (Excellent Condition)
* **Inputs:** Cycle: `2` | Voltage: `4.00V` | Current: `-2.00A` | Temp: `24°C`
* **Expected Output:** Capacity ~`1.81 Ah` | SoH ~`97.80%` (Green/Stable Status)

### 🚨 2. Extreme Dead Battery (Absolute Worst Case)
* **Inputs:** Cycle: `450` | Voltage: `2.80V` | Current: `-2.00A` | Temp: `45°C`
* **Expected Output:** Capacity drops to absolute floor ~`1.71 Ah` | SoH drops significantly triggering a **Danger/Red Alert** due to high cycle count, high temperature, and heavy load degradation.

---

## 💻 Local Installation & Setup

If you want to run this project locally on your machine, follow these steps:

1. **Clone the repository:**
```bash
   git clone [https://github.com/sarim121rana/ev-battery-health-predictor-.git](https://github.com/sarim121rana/ev-battery-health-predictor-.git)
   cd ev-battery-health-predictor-
