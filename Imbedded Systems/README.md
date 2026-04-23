# Imbedded Systems

As a result of my previous Dac project and for preperation for my antenna project i am learning how to code a STM32 microcontroller in Bare-Metal C. I chose Bare-Metal C as it is the level above assembly. This allows the code to be as efficent as possible as well as taking up small amounts of memory. Additionally, I already have extensive knowledge on assembly coding due to my other custom CPU project. This allows for me to, rather than have to learn C from scratch i am able to use my knowledge on CPU architecture and assembly to my advantage. The work here spans from simple GPIO control to PWM generation, timing systems, and real‑time signal generation.  
Each project builds on the previous one, forming a structured learning path that gradually increases in complexity and capability.

---

## Impetus for this Project

### Replacing an outdated USB-to-I2S chip
This entire embedded journey started because I wanted to stop relying on an expensive, outdated USB‑to‑I2S chip for my audio DAC.  
Instead of depending on legacy hardware, I decided to learn how to generate the required digital signals myself using a modern microcontroller.

### Future antenna project
I also plan to use these skills for a future antenna project, which will require precise timing, signal generation, and real‑time control.  
Building a strong foundation now ensures I can design the hardware and firmware myself later without relying on black‑box modules.

### Why bare metal
I chose bare‑metal programming because:

- I already designed a custom CPU and wrote a Python assembler for it  
- I have experience writing assembly, so low‑level control feels natural  
- I don’t know much about high‑level languages, but I understand hardware deeply  
- Working directly with registers is simply more fun  
- It avoids the overhead and abstraction of HAL libraries  

Bare‑metal development lets me treat the STM32 like a machine I fully control.

---

## Project Structure and Learning Path
This section is intentionally structured from simple to advanced, with each project building on the previous one.  
The final goal is a pendulum stabilization system using PWM and an IMU.

### Planned structure
1. Basic GPIO – LED blinking, output control, register basics  
2. SysTick timing – clock‑independent millisecond timer  
3. Button input and debouncing – stable mechanical input handling  
4. PWM generation (TIM2) – LED brightness control, waveform generation  
5. Smooth LED fading – combining PWM and SysTick for animations  
6. Servo‑ready PWM base – 50 Hz PWM with precise pulse widths  
7. MPU6050 integration – I2C communication and sensor reading  
8. Real‑time control – mapping sensor data to PWM output  
9. Final project: pendulum stabilization – closed‑loop control using IMU and PWM  

---

## Current Architecture (STM32F4 Bare‑Metal Framework)

### SysTick timing system
- Clock‑independent millisecond timing using SystemCoreClock  
- Interrupt‑driven counter for precise delays  
- Supports debouncing, animations, and real‑time tasks  

### PWM engine (TIM2)
- Direct register configuration of PSC, ARR, CCR, and PWM mode  
- Supports LED fading and servo‑compatible pulse widths  
- Uses GPIO alternate function mapping (AF1 on PA0–PA3)  

### GPIO subsystem
- Fast, deterministic bitwise operations  
- Input/output configuration using MODER, IDR, ODR  
- Debounced button input using SysTick timestamps  

### Clocking and system initialization
- Uses CMSIS SystemInit and SystemCoreClock  
- Ensures consistent behavior across power cycles  
- Supports variable CPU frequencies without code changes  

---

## Timeline and Evolution

### V1 — Basic GPIO and LED control
- Enabled GPIO clocks using RCC  
- Configured pins as outputs using MODER  
- Created simple LED blink loops  
- Learned memory‑mapped register access  

### V2 — SysTick timing system
- Implemented a millisecond timer using SysTick  
- Converted to a variable‑clock version using SystemCoreClock  
- Added accurate delay functions  
- Enabled debouncing and real‑time timing logic  

### V3 — PWM generation (TIM2)
- Configured TIM2 for PWM mode using direct register access  
- Mapped PA0 to TIM2_CH1 using AFR registers  
- Implemented LED brightness control via duty cycle changes  
- Debugged cold‑boot flickering by ensuring full timer initialization  

### V4 — Smooth LED fading
- Created smooth brightness transitions using PWM and SysTick  
- Implemented variable‑speed fading and strobe effects  
- Learned how ARR, PSC, and CCR interact to shape waveforms  

### V5 — Servo‑ready PWM base
- Built a 50 Hz PWM configuration compatible with hobby servos  
- Ensured stable pulse widths across power cycles  
- Created a reusable PWM initialization module  

---

## Key Features

### Clock‑independent SysTick timer
- Automatically adapts to any CPU frequency  
- Provides accurate millisecond timing  
- Enables debouncing, animations, and real‑time tasks  

### Direct register PWM engine
- Full control over prescaler, ARR, CCR, and PWM mode  
- Supports LED fading, strobing, and servo‑compatible pulses  
- No HAL or abstraction layers  

### GPIO input/output system
- Fast, deterministic bitwise operations  
- Clean input handling with debouncing  
- Supports buttons, LEDs, and alternate‑function peripherals  

### Reusable bare‑metal modules
- systick_init  
- delay_ms  
- pwm_init  
- GPIO configuration templates  

---

## Design Evolution

### SysTick improvements
- Moved from fixed‑frequency timing to SystemCoreClock‑based timing  
- Eliminated hardcoded MHz assumptions  
- Improved reliability across power cycles  

### PWM stability fixes
- Ensured ARR, PSC, and CCR are configured before enabling TIM2  
- Added preload enable bits to prevent mid‑cycle glitches  
- Corrected AFR mappings to avoid flicker after cold boot  

### GPIO refinements
- Standardized bit‑masking patterns for clarity  
- Improved debouncing logic using SysTick timestamps  
- Ensured consistent behavior across resets  

---

## Engineering Insight
Working at the register level forces a deep understanding of:

- clock trees and prescalers  
- timer update events  
- GPIO alternate functions  
- interrupt timing  
- hardware reset states  

Debugging PWM flicker after power‑cycling highlighted the importance of:

- initializing every relevant register  
- understanding default reset states  
- enabling preload registers  
- configuring AFR before enabling outputs  

---

## Lessons Learned
- How to configure SysTick for variable CPU frequencies  
- How PWM works at the hardware level (ARR, PSC, CCR, preload)  
- How to debounce mechanical buttons using timing logic  
- How to structure embedded projects for clarity and reuse  
- The importance of understanding hardware reset states  
- How to debug timing‑related issues in real‑time systems  

---

## Future Work
- Integrate the MPU6050 via I2C  
- Map IMU angle data to PWM output  
- Implement a simple PID controller  
- Final goal: pendulum stabilization system  

This will combine everything learned so far into a complete embedded engineering project.
