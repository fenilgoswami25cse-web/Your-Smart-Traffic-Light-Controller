# 🚦 Smart Traffic Light Controller
### Digital Electronics Mini Project — BTech Computer Science Engineering

---

## 📌 Project Overview

A complete, interactive browser-based simulation of a four-way intersection traffic signal controller, demonstrating core **Digital Electronics** concepts including:

- Finite State Machines (Moore Machine)
- D Flip-Flops and Binary State Registers
- Next-State Logic (XOR, NOT gates)
- State Transition Tables and Truth Tables
- Boolean Algebra and Output Decoder
- Adaptive / "Smart" Traffic Control Simulation

---

## 🚀 How to Run Locally

### Method 1 — Direct Browser (Easiest)
```
1. Navigate to the project folder
2. Double-click index.html
3. It opens in your default browser — no server needed!
```

### Method 2 — VS Code Live Server
```
1. Open the folder in VS Code
2. Install "Live Server" extension (ritwickdey.liveserver)
3. Right-click index.html → "Open with Live Server"
4. App opens at http://127.0.0.1:5500
```

### Method 3 — Node.js http-server
```bash
npm install -g http-server
cd "DE Project 735"
http-server -p 8080
# Open http://localhost:8080
```

### Method 4 — Python
```bash
cd "DE Project 735"
python -m http.server 8080
# Open http://localhost:8080
```

---

## 📁 File Structure

```
DE Project 735/
├── index.html    ← Complete single-file application (HTML + CSS + JS)
└── README.md     ← This file
```

---

## 🖥️ Features

| Feature | Description |
|---|---|
| **4-Way Intersection SVG** | Animated top-view road with lanes, zebra crossings, vehicles |
| **Traffic Light Animation** | Glowing LED-style lights with CSS filter effects |
| **Vehicle Animation** | Vehicles move on green, stop on red — real-time canvas animation |
| **FSM Controller** | 4-state Moore machine: S0→S1→S2→S3→S0 |
| **Binary State Register** | Live Q1/Q0 bits and D1/D0 next-state computation |
| **FSM Diagram Tab** | Interactive state transition diagram with active state highlight |
| **Logic Design Tab** | Circuit diagram SVG — D flip-flops, XOR/NOT gates, output decoder |
| **Truth Table Tab** | State table + output truth table with live row highlighting |
| **Learning Dashboard** | 10 digital electronics concepts with formulas and examples |
| **Smart Mode** | Demand-based timing, emergency vehicle override, pedestrian request |
| **Viva Prep** | 20 Q&A accordion — collapsible answers |
| **About / Results** | Full experiment report (theory, algorithm, observations, conclusion) |
| **Controls** | Start, Pause, Resume, Reset, Next State |
| **Configurable Timers** | Separate green/yellow phase duration sliders |
| **Countdown Ring** | Animated SVG arc countdown timer |
| **Responsive** | Works on mobile, tablet, desktop |

---

## 🔁 FSM State Sequence

```
S0 (Q1Q0=00): NS GREEN,  EW RED     → after Green timer
S1 (Q1Q0=01): NS YELLOW, EW RED     → after Yellow timer
S2 (Q1Q0=10): NS RED,    EW GREEN   → after Green timer
S3 (Q1Q0=11): NS RED,    EW YELLOW  → after Yellow timer → back to S0
```

**Next-State Equations:**
```
D0 = NOT(Q0)       — Q0 complement
D1 = Q1 XOR Q0     — Q1 exclusive-or Q0
```

**Safety Proof:**
```
NS_GREEN = Q1'·Q0'   EW_GREEN = Q1·Q0'
NS_GREEN AND EW_GREEN = Q1'·Q0'·Q1·Q0' = 0  ✅ (always safe)
```

---

## 🌐 Deployment

### Vercel (Recommended)
```bash
# Install Vercel CLI
npm install -g vercel

# From project folder
vercel

# Follow prompts → gets deployed to https://your-project.vercel.app
```

### GitHub Pages
```bash
git init
git add .
git commit -m "Smart Traffic Light Controller - Digital Electronics Mini Project"
git remote add origin https://github.com/YOUR_USERNAME/smart-traffic-light.git
git push -u origin main

# In GitHub repo settings → Pages → Deploy from branch: main → root /
```

### Netlify
```
1. Go to netlify.com
2. Drag and drop the DE Project 735 folder
3. Done! Gets a live URL instantly.
```

---

## ⚠️ Educational Disclaimer

> This is a **software simulation** for educational purposes only.  
> Real road traffic signal controllers require:
> - Government-approved timing plans
> - All-red clearance intervals (ITE/MUTCD standards)
> - Hardware fail-safe mechanisms (flashing red on power loss)
> - Certified traffic engineering review and installation
> - Real inductive loop or video detection sensors

---

## 🎓 Digital Electronics Concepts Demonstrated

1. Finite State Machines (Moore Machine)
2. Moore vs. Mealy Machine classification
3. Sequential vs. Combinational circuits
4. D Flip-Flop operation and state storage
5. Clock pulse synchronization
6. Binary counters (mod-4 Gray counter)
7. State transition table construction
8. Truth tables and Boolean algebra
9. Output decoder logic (AND/NOT gates)
10. Karnaugh map simplification

---

## 👨‍💻 Tech Stack

- **HTML5** — Structure
- **CSS3** — Dark engineering dashboard, animations, responsive layout
- **Vanilla JavaScript** — FSM logic, timer management, SVG rendering
- **SVG** — Intersection diagram, FSM diagram, circuit diagram, countdown arc
- **Zero dependencies** — No frameworks, no build tools, no backend

---

## 📋 Testing Checklist

- [x] Simulation starts only when Start is clicked
- [x] Pause freezes countdown and vehicles
- [x] Resume continues without duplicate timers
- [x] Reset restores S0 and clears countdown
- [x] Next State advances exactly one step
- [x] All four states repeat in correct order
- [x] NS and EW never show green simultaneously
- [x] Timer changes take effect on next phase
- [x] Smart Mode respects min/max green limits
- [x] Emergency override transitions safely
- [x] Pedestrian phase halts all traffic briefly
- [x] Browser tab visibility change handled (no timer accumulation)
- [x] Responsive on mobile screens
- [x] All navigation tabs functional
- [x] FSM diagram highlights active state
- [x] Truth table highlights active row

---

*Built for BTech CSE Digital Electronics Mini Project — 2025*
