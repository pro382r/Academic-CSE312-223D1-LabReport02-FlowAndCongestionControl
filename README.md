# TCP Reno Congestion and Flow Control Simulator in Java

This Java project simulates the **TCP Reno** congestion control algorithm along with **TCP flow control** using basic console input/output. It's ideal for students and educators seeking to understand how TCP dynamically manages data transmission to avoid congestion and buffer overflow.

---

## ✅ Features

- Implements **TCP Reno Congestion Control**:
  - Slow Start (exponential increase)
  - Congestion Avoidance (linear increase)
  - Fast Recovery (on 3 duplicate ACKs)
  - Timeout handling (slow start reset)

- Simulates **TCP Flow Control**:
  - Respects receiver window size (`rwnd`)
  - Ensures sender doesn’t overflow receiver buffer

- User inputs simulate:
  - Data length to send
  - Initial slow-start threshold (`ssthresh`)
  - Receiver window size (`rwnd`)

---

## 🛠️ How It Works

- The sender transmits data in **rounds (RTTs)**.
- Congestion is randomly simulated via ACK loss.
- Each round:
  - `cwnd` grows (based on TCP Reno rules)
  - `effectiveCwnd = min(cwnd, rwnd)` is used for sending
- If congestion is detected:
  - **Timeout → cwnd reset to 1**
  - **Triple Dup ACK → cwnd halved**

---

## 📥 Getting Started

### Requirements:
- Java JDK 8 or higher
- Any IDE (e.g., IntelliJ, Eclipse) or terminal

### How to Run:
1. Compile the file:
   ```bash
   javac TCPCongestionControl.java
   ```
2. Run the program:

```bash
java TCPCongestionControl
```
3. Follow the prompts:

Input ssthresh
Input total data length
Input receiver window size (rwnd)

📌 Sample Output Snapshot
```sql
Please input the initial ssthresh value:
10
Enter the length of your data:
100
Enter receiver window size (rwnd):
8

RTT 1 - Slow Start phase...
Sending data from 1 to 2
...
RTT 4 - Congestion Avoidance phase...
...Congestion Detected!
Triple Duplicate ACKs received. Entering fast recovery.
Retransmitting lost packet...
```

📚 Concepts Covered:

TCP Flow Control (Receiver Window - rwnd)

TCP Congestion Control (Reno Variant)

cwnd dynamics

Simulated packet loss (randomized ACK behavior)

