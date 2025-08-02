# Robotic Arm Torque Analysis and Servo Selection

This project analyzes the torque requirements of a 3-DOF robotic arm. It calculates the torque needed at each joint based on the arm's geometry and recommends suitable servo motors accordingly.



## Table of Contents
- [Arm Configuration](#arm-configuration)
- [Torque Calculations](#torque-calculations)
- [Servo Motor Selection](#servo-motor-selection)




## Arm Configuration

<img width="580" height="463" alt="Screenshot 2025-08-01 213938" src="https://github.com/user-attachments/assets/1653fd5a-e54d-4cba-9f54-4c7a6de685fd" />



## Torque Calculations

Torque at each joint is calculated using:

Torque (Nm) = Force (N) × Distance (m)

Force(N) = mass (m) x acceleration due to gravity (g)

m= 1 kg

g= 9.81 m/s^2

So F = m x g = 1kg x 9.81 m/s^2 = 9.81 N

### Torque per Joint:

- **Joint 0 (Base)**  
  Torque = 9.81N x Full arm = 9.81N x (4+10+15)cm = 9.81N x 29 cm = 9.81N x 0.29m = 2.8449 N.m
  
- **Joint 1(Joint 1 to Joint 2)**  
  Torque = 9.81N x (4+10)cm = 9.81N x 14cm = 9.81N x 0.14m= 1.3734 N.m

- **Joint 2(Joint 2 to End Effector)**  
  Torque = 9.81N X 4cm = 9.81N x 0.04m = 0.3924 N.m

### Conversion to kg·cm (1 Nm ≈ 10.197 kg·cm):

- **Joint 0**: 2.8449 Nm × 10.197 = **29 kg·cm**  
- **Joint 1**: 1.3734 Nm × 10.197 = **14 kg·cm**  
- **Joint 2**: 0.3924 Nm × 10.197 = **4 kg·cm**

## Servo Motor Selection

### Joint 2 (Joint 2 to End Effector)
- **Required Torque**: ≥ 4 kg·cm  
- **Suggested Motor**: **MG995 Servo** (12 kg·cm)  
- Suitable with a good safety margin  
- Buy locally (Saudi Arabia): [iElectrony](https://ielectrony.com/product/%D8%B3%D9%8A%D8%B1%D9%81%D9%88-%D9%85%D9%88%D8%AA%D8%B1-12%D9%83%D8%AC%D9%85-3)  
- Buy internationally: [AliExpress](https://ar.aliexpress.com/item/1005005061251086.html)

---

### Joint 1 (Joint 1 to Joint 2)
- **Required Torque**: ≥ 14 kg·cm  
- **Suggested Motor**: **DS3218MG Servo** (20 kg·cm)  
- Offers high torque and performance  
- Buy from: [AliExpress](https://ar.aliexpress.com/item/1005007495298378.html)

---

### Joint 0 (Base)
- **Required Torque**: ≥ 29 kg·cm  
- **Suggested Motor**: **TD-8135 Servo** (35 kg·cm)  
- Recommended for high-load base movement  
- Buy from: [AliExpress](https://ar.aliexpress.com/item/1005007463297677.html)

---

## Could the same motors selected from the previous mission lift a weight of 2 kilograms instead of 1 kilogram by adding some gears? What are the drawbacks that the user of this arm will face? What are the alternatives to address these drawbacks?
Yes

Joint 2 (Joint 2 to End Effector)
- No gears are needed. The torque requirement becomes 8 kg·cm, and the selected servo (e.g., MG995 with 12 kg·cm) is sufficient.

Joint 1 (Joint 1 to Joint 2)
- Gears are required. The required torque is now 28 kg·cm, but the servo can handle only 20 kg·cm.

Joint 0 (Base)
- Gears are required. The required torque increases to 58 kg·cm, while the servo can handle up to 35 kg·cm.

Drawbacks of using gears with the same motors:

1- Slower movement
- Gear reduction trades speed for torque → arm becomes slower.

2- Increased mechanical complexity
= Gears need precise alignment and mounting → more parts, more failure points.

3- Backlash
- Gears introduce play in movement → less precise positioning.

4- Noise & friction
- More moving parts = more friction and audible noise.

5- Larger size
= Gears take space → bulkier arm design.

6- Higher power consumption
- Lifting heavier loads strains motors, increases current draw → possible overheating.

Alternatives to using gears: 

Instead of relying on gear systems, I recommended to use stronger servo motors that meet the torque requirements directly. This simplifies design, improves speed and accuracy, and reduces long-term maintenance.






نسخ
تحرير
