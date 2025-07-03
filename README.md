# SPI to I2C Protocol Conversion using Verilog 🔄

This project implements a **Protocol Conversion Unit (PCU)** that enables seamless communication between two widely used serial protocols: **SPI (Serial Peripheral Interface)** and **I2C (Inter-Integrated Circuit)**. It is designed entirely in **Verilog HDL**, simulated using **Xilinx ISE Design Suite 14.7**, and verified using **ISim**.

This work is a part of my personal hardware design portfolio and showcases my ability to handle RTL coding, protocol-level logic design, and simulation in Verilog.

---

## 🎯 Project Objective

- To design a converter that receives data from an **SPI Master** and transmits it to an **I2C Slave**
- To simulate and verify functionality of all protocol stages
- To demonstrate the working of a **unified communication system** in mixed-protocol embedded environments

---

## 🛠️ Tools & Technology

| Item                | Details                          |
|---------------------|----------------------------------|
| HDL Language        | Verilog                          |
| Simulation Tool     | Vivado 24.2                      |
| Target              | RTL-level simulation             |
| Design Scope        | One SPI master → One I2C slave   |

---

## 📁 Repository Contents

| File Name                | Description                              |
|--------------------------|------------------------------------------|
| `spi_receiver.v`         | SPI master-side logic to receive data    |
| `i2c_master.v`           | I2C protocol controller (transmitter)    |
| `protocol_converter.v`   | Core protocol conversion logic           |
| `clock_divider.v`        | Clock divider for I2C slower clock       |
| `top_module.v`           | Top-level integration                    |
| `testbench.v`            | Verilog testbench for simulation         |
| `README.md`              | This documentation                       |
| `SoC to I2P Output.png`  | Simulation Output Image                  |

---

## 🧠 How It Works

1. **SPI Side**:  
   The PCU receives serial data bits from the SPI master in full-duplex mode.

2. **Protocol Conversion**:  
   Data is buffered and reformatted into an I2C-compatible transmission frame.

3. **I2C Side**:  
   The PCU transmits the converted data to an I2C slave using a 2-wire protocol, complete with start/stop conditions and ACK/NACK handling.

> ⚡ This design supports one slave and is scalable for multiple devices using a FIFO and addressing logic.

---

## 🔍 Why This Project Matters

In embedded systems where **both SPI and I2C devices coexist**, protocol bridging is essential. SPI offers high-speed communication but requires more I/O lines. I2C saves I/O but is slower. This converter bridges that gap — allowing an SPI-based master to talk to I2C peripherals without changing the underlying bus architecture.

---

## 📊 Testbench Simulation

- The testbench simulates SPI transmission and verifies I2C output
- Functional correctness is validated through waveform inspection (via ISim)

---

## 🚀 Future Scope

- Integrate FIFO for multi-slave I2C addressing
- Add control logic to dynamically switch baud rates
- Implement RTL synthesis and FPGA deployment (e.g., on Spartan-6)

---

## 👩‍💻 Author

**Ritika Roy**  
Electronics & Communication Engineer  
🔧 VLSI Design • RTL Coding • Embedded Protocols  
[GitHub](https://github.com/ritikaroy01) • [LinkedIn](https://www.linkedin.com/in/ritikaroy01)

---

## 📜 License

This project is open-source and free to use for educational or research purposes. Attribution is appreciated.

