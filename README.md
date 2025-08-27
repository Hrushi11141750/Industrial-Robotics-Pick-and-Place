# Ball Sorting Robot – Pick and Place

This project implements a **pick-and-place robotic routine** using a **KUKA robot** for sorting colored balls (Red, Green, Blue) into separate palettes.  
The program was **first tested in simulation** and then deployed on the **real robot** successfully.

---

## **1. Project Overview**

The goal of this project is to:
- Detect the presence of a ball in the feeder.
- Identify its color using digital sensors.
- Pick the ball from the feeder.
- Place it into the correct color-specific palette position.
- Repeat until each palette is full (10 balls per color).

---

## **2. Setup and Requirements**

### **Software**
- **KUKA OfficeLite / OfficePC** for simulation
- **KUKA.WorkVisual** (for program editing and deployment)

---

## **3. Program Files**

| File Name | Description |
|-----------|-------------|
| `rwuBallTeach_group3a.src` | Main program that controls pick-and-place logic. |
| `rwuBallTeach_group3a.dat` | Data file that stores persistent counters and variables. |

---

## **4. Workflow**

### **Step 1 – Simulation**
- Program was first written and tested in **KUKA OfficeLite simulation**.
- Verified:
  - Robot path accuracy
  - Signal reading logic
  - Ball detection and sorting flow
  - Collision-free trajectories

### **Step 2 – Real Robot Execution**
- Program deployed to physical robot.
- Real sensor inputs mapped to `$IN[15]–$IN[18]`.
- Fine-tuned positions to match the physical feeder and palettes.
- Successfully ran full cycles for Red, Green, and Blue balls.

---

## **5. Logic Summary**

1. **Wait for ball signal** (`$IN[15]`).
2. **Pick up ball** from feeder position.
3. **Move to sensor** and check signals:
   - `$IN[16]` → Red  
   - `$IN[17]` → Green  
   - `$IN[18]` → Blue  
4. **Move to correct palette position** based on detected color.
5. **Increment counter** for that color.
6. **Repeat** until each counter reaches 10.

---

## **6. Key Points**
- **Safety:** Always run at reduced speed during first live tests.
- **Calibration:** Ensure feeder, sensor, and palette positions are taught accurately.
- **Error Handling:** If no signal is detected, the robot will remain in the wait state.
  
![WhatsApp Image 2025-08-27 at 12 59 04](https://github.com/user-attachments/assets/e058ef65-bd6a-4d09-94c3-158157948b53)
![WhatsApp Image 2025-08-27 at 12 59 04](https://github.com/user-attachments/assets/fb073ebd-fd14-48e1-812c-6881a2cdfae6)
![WhatsApp Image 2025-08-27 at 12 59 04 (2)](https://github.com/user-attachments/assets/f4a8ef96-5832-4936-b89a-fd9b9f81e528)
![WhatsApp Image 2025-08-27 at 12 59 04 (3)](https://github.com/user-attachments/assets/142fbd0a-f659-4136-abed-656de2f40513)
![WhatsApp Image 2025-08-27 at 12 59 04 (3)](https://github.com/user-attachments/assets/bc2a5c28-c743-4f58-bf0f-ca32083f2d99)

https://github.com/user-attachments/assets/a4f21759-b5c8-42f8-af36-e17a14b33bfd





