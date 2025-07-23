# STM32F411 Nucleo UART DMA Communication

![STM32F411](https://img.shields.io/badge/STM32F411-Nucleo-blue) 
![UART](https://img.shields.io/badge/USART1-DMA_Mode-green)


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

*Note: Requires external USB-TTL converter or second UART device*

## Technical Details
### UART/DMA Configuration 
```c
Baud Rate: 115200 (84MHz clock)
DMA Channels:
  - TX: DMA2 Stream7
  - RX: DMA2 Stream2
Buffer Size: 10 bytes
Transfer Mode: Circular (continuous)
