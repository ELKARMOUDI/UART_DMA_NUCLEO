# STM32F411 Nucleo UART DMA Communication

![STM32F411](https://img.shields.io/badge/STM32F411-Nucleo-blue) 
![UART](https://img.shields.io/badge/USART1-DMA_Mode-green)

<img src="https://github.com/user-attachments/assets/95dd7076-3239-4f3b-b07d-2a8f3b468817" width="650" alt="1AF5445C-9632-47A7-80C5-8D6F1A053D33">


High-performance UART communication using DMA on STM32F411 Nucleo.

## Features
- **USART1** at 115200 baud
- **DMA-Enabled** TX/RX
- **Zero CPU Overhead** during transfers
- **10-byte Buffers** (tx_buffer/rx_buffer)
- **Completion Callbacks** with counters
- **84MHz System Clock** (HSI-based PLL)

## Hardware Setup
| Signal | Nucleo Pin | Connection |
|--------|------------|------------|
| USART1_TX | PA9 (D8)  | → External RX |
| USART1_RX | PA10 (D2) | ← External TX |
| GND       | GND       | ↔ External GND |


## Technical Details
### UART/DMA Configuration 
```c
Baud Rate: 115200 (84MHz clock)
DMA Channels:
  - TX: DMA2 Stream7
  - RX: DMA2 Stream2
Buffer Size: 10 bytes
Transfer Mode: Circular (continuous)
