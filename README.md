## **Two-Tank System Control Using MATLAB Simulink**  

### **Project Overview**  
This repository contains MATLAB Simulink models and analysis for a **two-tank system** where a robot controls liquid levels using a **PID controller**. The objective is to regulate the liquid levels in two interconnected tanks by adjusting the inflow rate.  

### **Key Features**  
- **System Modeling**: Developed a Simulink model representing the **dynamic behavior** of the two-tank system.  
- **PID Controller Implementation**: Designed a **feedback control system** to maintain desired liquid levels.  
- **Performance Analysis**: Evaluated system stability, response characteristics (step response, Bode plots), and fine-tuned PID parameters.  

### **System Description**  
- **Tank 1 receives an inflow** \( Q_{in}(t) \) controlled by the robot.  
- **Tank 1 outflow** \( Q_{out,1}(t) \) is proportional to its liquid height.  
- **Tank 2 receives outflow** from Tank 1 and drains via its own outlet.  
- **The goal** is to maintain:  
  - \( h_{desired,1} = 1.5m \) (Tank 1 level)  
  - \( h_{desired,2} = 1.0m \) (Tank 2 level)  

### **Mathematical Model**  
The liquid levels in the two tanks are governed by the following differential equations:  

\[
A_1 \frac{dh_1}{dt} = Q_{in} - Q_{out,1}
\]
\[
A_2 \frac{dh_2}{dt} = Q_{out,1} - Q_{out,2}
\]
where the outflows are:  
\[
Q_{out,1} = k_1 \sqrt{h_1}, \quad Q_{out,2} = k_2 \sqrt{h_2}
\]  

### **Implementation Details**  
1. **Simulink Model**:  
   - Implemented system dynamics using Simulink blocks.  
   - Simulated without control to observe natural behavior.  
2. **PID Controller**:  
   - Added a feedback control loop to regulate \( h_1 \) and \( h_2 \).  
   - Tuned PID parameters to achieve stability and minimal overshoot.  
3. **Analysis & Results**:  
   - Examined system response with and without control.  
   - Evaluated step response and frequency response (Bode plot).  

### **Repository Structure**  
```
📂 Two-Tank-System  
 ├── 📁 Simulink_Files        # Simulink models (.slx)  
 ├── 📄 Report.pdf            # Analysis and explanation of results  
 ├── 📄 README.md             # This documentation  
 ├── 📄 PID_Tuning.m          # MATLAB script for PID tuning  
```

### **Getting Started**  
#### **Requirements**  
- MATLAB (R2024 or later)  
- Simulink toolbox  

#### **How to Run**  
1. Clone the repository:  
   ```bash
   git clone https://github.com/yourusername/repo-name.git
   cd repo-name
   ```
2. Open MATLAB and navigate to the project directory.  
3. Open `Simulink_Files/two_tank_system.slx` and run the simulation.  
4. Adjust PID parameters in `PID_Tuning.m` if needed.  

### **Results & Observations**  
- Without control, the liquid levels fluctuate unpredictably.  
- With PID control, the system stabilizes and reaches the desired levels.  
- The controller tuning significantly impacts response time and stability.  

### **Future Improvements**  
- Implement adaptive control strategies for varying inflow conditions.  
- Explore **nonlinear control methods** for better performance.  

### **Acknowledgments**  
This project is part of **Robotic Principles Coursework (5ELEN018W)** at **University of Westminster**...
