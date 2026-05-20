# Digital Clock Simulation using Multisim

A fully functional **24-hour digital clock** designed and simulated in **National Instruments Multisim 14**. The project demonstrates the practical application of sequential and combinational logic using TTL ICs.

![Digital Clock]()  


## ✨ Features

- **Seconds Counter**: 00 to 59 with automatic rollover
- **Minutes Counter**: 00 to 59 with automatic rollover from seconds
- **Hours Counter**: 00 to 23 with proper 24-hour reset logic
- **Manual Time Setting**: Push buttons to fast-forward minutes and hours
- **7-Segment LED Displays** for HH:MM:SS
- **Progressive Design Files** – from basic JK flip-flop counters to full integrated system

## 🛠️ Components Used

- **IC 7490** – Decade Counters (Mod-10)
- **IC 7447** – BCD to 7-Segment Decoder/Driver
- **IC 7408** – Quad 2-Input AND Gates (for reset logic)
- **IC 7432** – Quad 2-Input OR Gates (for manual + auto clocking)
- **7-Segment Displays** (Common Anode)
- Push Buttons + 10kΩ Pull-down Resistors
- 1 Hz Clock Source

## 📁 Project Structure
Digital Clock/
├── 01_JK_FF_...                  # Basic JK Flip-Flop Counter
├── 02_JK_FF_counter_...          # Asynchronous Counter
├── 03_7490_IC_TO_7segment...     # Single Digit with Display
├── 04_SECOND_counter_upto_59...  # Seconds Stage
├── 05_SECOND_counter_upto_99...
├── 06_minute+second_clock...     # Seconds + Minutes
├── 07_minute+second_clock...
├── 08_hr+min+second_clock...     # Full Clock
├── 09_hr+min+second_clock_+_Manual_button...  # Final Version with Manual Set
├── Digital Clock Explanation.pdf # Detailed Theory & Wiring Guide
└── README.md

## 🔧 How It Works

### Seconds & Minutes (00-59)
- Uses two 7490 ICs per stage (Units + Tens)
- Tens digit resets at 6 using AND gate logic (QB & QC)
- Carry signal passed to the next stage

### Hours (00-23)
- Special combined reset logic
- Resets when Hours Tens = 2 **and** Hours Units = 4 (detected using AND gate on QC of units and QB of tens)

### Manual Adjustment
- OR gates combine automatic carry signal with manual button pulses
- Allows setting time without disturbing the main clock chain

## 🚀 How to Simulate

1. Open **Multisim 14** (or compatible version)
2. Open the file: `09_hr+min+second_clock_+_Manual_button.ms14`
3. Run the simulation
4. Use the **1 Hz clock** for real-time behavior or increase frequency for fast testing
5. Press manual buttons to set time

## 📸 Screenshots



## 📚 Learning Outcomes

- Asynchronous counter design using JK Flip-Flops
- Cascading of 7490 decade counters
- Custom modulus counter design (mod-60 and mod-24)
- Integration of combinational logic for reset and control
- Simulation best practices in Multisim

## Future Enhancements

- 12/24 hour format selection
- Alarm functionality
- Stopwatch mode
- Real hardware implementation on breadboard/PCB

---

**Made with ❤️ for Digital Electronics Learning**
