# Water-Tank-Problem---Visualizer Using HTML, CSS & JavaScript  
*(Trapping Rain Water Problem)*
---
App : https://mounicasrinivasan163.github.io/Water-Tank-Problem---Visualizer/
---

A fully interactive frontend project that visualizes how much rainwater can be trapped between elevations (blocks). This implementation follows industry-standard coding practices and includes a clean SVG-based visualization.

---

# 📌 **1. Problem Statement**

You are given an array of non-negative integers where each integer represents the height of a block.  
Water is trapped between blocks when a block is shorter than the tallest blocks on its left and right sides.

### **Input**
An array of block heights:  
```
[0, 4, 0, 0, 0, 6, 0, 6, 4, 0]
```

### **Output**
Total trapped water:  
```
18 Units
```

### **Goal**
Build a **frontend web application** (Vanilla JS + HTML + CSS) that:  
✔ Takes block heights as input  
✔ Calculates trapped rainwater  
✔ Visualizes blocks + trapped water using SVG  

---

# 📊 **2. Data Table Example**

| Index | Block Height | Left Max | Right Max | Water Above |
|------|--------------|-----------|------------|--------------|
| 0 | 0 | 0 | 6 | 0 |
| 1 | 4 | 4 | 6 | 0 |
| 2 | 0 | 4 | 6 | 4 |
| 3 | 0 | 4 | 6 | 4 |
| 4 | 0 | 4 | 6 | 4 |
| 5 | 6 | 6 | 6 | 0 |
| 6 | 0 | 6 | 6 | 6 |
| 7 | 6 | 6 | 6 | 0 |
| 8 | 4 | 6 | 4 | 0 |
| 9 | 0 | 6 | 0 | 0 |

Total water = **18 units**

---

# 🧠 **3. How to Think About the Problem**

The trapped water above any block depends on:  
- **Tallest bar on the left**
- **Tallest bar on the right**
- **Current block height**

Water above index `i` is:

```
water[i] = min(maxLeft[i], maxRight[i]) − height[i]
```

If the result is negative → water[i] = 0.

---

# 🛠️ **4. Available Techniques / Algorithms**

### **A. Brute Force Approach (O(n²))**
For every block:  
- Find tallest block to the left  
- Find tallest block to the right  
- Compute trapped water  

❌ Very slow  
❌ Not scalable  
✔ Easy to understand  

---

### **B. Precomputed Left & Right Max Arrays — (Chosen Method)**
**Time Complexity:** O(n)  
**Space Complexity:** O(n)

We create:  
- `leftMax[i]`: tallest block from 0…i  
- `rightMax[i]`: tallest block from i…end  

Then water[i] = min(leftMax[i], rightMax[i]) – height[i]

✔ Fast  
✔ Simple  
✔ Best for teaching + visualizing

---

### **C. Two-Pointer Method (Optimized O(n))**
No extra space, uses two pointers:

- Move left if leftMax ≤ rightMax  
- Otherwise move right  

✔ Fastest  
✔ Lowest memory  
❌ Harder to visualize  
❌ Code complexity is higher  

---

# 🎯 **5. Why We Chose the Left–Right Max Approach**

✔ Clean + intuitive logic  
✔ Easy to visualize  
✔ Great for front-end demo  
✔ Industry-standard interview solution  
✔ Works well with SVG block rendering  

---

# 🔍 **6. Algorithm Explanation (Step-by-Step)**

### **Step 1 — Precompute Left Max**
```
leftMax[0] = height[0]
leftMax[i] = max(leftMax[i-1], height[i])
```

### **Step 2 — Precompute Right Max**
```
rightMax[n-1] = height[n-1]
rightMax[i] = max(rightMax[i+1], height[i])
```

### **Step 3 — Calculate Water**
```
water[i] = min(leftMax[i], rightMax[i]) - height[i]
if (water[i] < 0) water[i] = 0
```

### **Step 4 — Sum Water**
```
totalWater = sum(water[i])
```

---

# 🧪 **7. Use Case Examples**

## **Use Case 1 — Simple Valley**
Input:
```
[3, 0, 2]
```
Output:
```
2 units
```

---

## **Use Case 2 — Multiple Peaks**
Input:
```
[0,3,0,2,0,4]
```
Output:
```
7 units
```

---

# 🖼️ **8. Screenshots**

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/2550b2cf-c843-4e52-a085-ad0d7db105dd" />


---

# 💻 **9. How to Run Locally**

### **Method 1 — Download ZIP**
1. Click **Code** → **Download ZIP**
2. Extract  
3. Open `index.html` in browser  

---

### **Method 2 — Git Clone**
```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
open index.html
```

---

# 🌐 **10. Deployment (GitHub Pages)**

Enabled via:  
**Settings → Pages → Deploy from Branch → main → /(root)**

URL will be:
```
https://<username>.github.io/<repo-name>/
```

---

# 🎨 **11. UI Enhancements Included**

✔ Modern input card  
✔ Rounded components  
✔ Improved typography  
✔ Hover effects  
✔ Responsive layout  
✔ Centered SVG container  
✔ Transparent water block coloring  
✔ Visual contrast between block + water  

---

# 🏗️ **12. Project Structure**

```
📁 root
│── index.html         # Contains HTML + CSS + JavaScript
│── README.md          # Documentation
└── /screenshots       # (optional)
```

---

# 🧑‍💻 **13. Tech Stack**

- **HTML5**  
- **CSS3 (inline styles)**  
- **Vanilla JavaScript (ES6)**  
- **SVG Graphics**

---

# 🤝 **14. Future Enhancements**

- Add animation for water fill  
- Add drag-and-drop block builder  
- Export SVG as PNG  
- Add selectable algorithms (Two-pointer vs DP)  
- Add automatic example generator  

---


