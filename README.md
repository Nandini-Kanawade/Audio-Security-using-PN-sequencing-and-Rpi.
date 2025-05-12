# Audio Data Communication Security Using P-N Sequences and Raspberry Pi

## Overview

This project focuses on enhancing the security of audio data communication by leveraging **Pseudo-Noise (P-N) sequences** and the **Raspberry Pi** platform. The goal is to ensure the safe and secure transmission of sensitive audio data, preventing unauthorized access and ensuring data confidentiality during the transfer process.

The system works by using **MATLAB** to record and convert audio into a binary stream, which is then encrypted with a P-N sequence. This encrypted data is transmitted between two Raspberry Pi devices. Upon reception, the data is decrypted using the same P-N sequence, restoring the original audio signal.

## Table of Contents

- [Purpose and Objective](#purpose-and-objective)
- [Methodology](#methodology)
- [Implementation](#implementation)
- [Key Findings](#key-findings)
- [Installation](#installation)
- [Usage](#usage)
- [License](#license)
- [Acknowledgements](#acknowledgements)
- [References](#references)

## Purpose and Objective

The primary objective of this project is to establish a secure communication channel for audio data using P-N sequences, ensuring:
- **Confidentiality**: Prevent unauthorized interception of audio data.
- **Integrity**: Ensure that the data received is exactly what was transmitted.
- **Authentication**: Authenticate communication between devices.

The project aims to implement robust encryption techniques on the Raspberry Pi platform, providing a reliable and cost-effective solution for audio data transmission.

## Methodology

1. **Broad Spectrum Signal**: Utilizes broad-spectrum signal techniques to enhance the reliability and quality of transmitted data.
2. **P-N Sequencing**: Uses Pseudo-Noise (P-N) sequences for secure encryption and decryption of the audio data. The P-N sequences are generated using **Linear Feedback Shift Register (LFSR)** technique.
3. **Secure Communication (SC) Protocols**: Integrates secure communication protocols to protect the transmitted data between the Raspberry Pi devices.

### Experimental Setup

- **MATLAB**: Used for recording and processing audio files.
- **Raspberry Pi**: Two Raspberry Pi units are used to transmit and receive the encrypted audio data.
- **Security Protocols**: Involves XOR encryption and decryption based on P-N sequences.

## Implementation

The implementation involves the following steps:
1. **Audio Recording**: Audio is recorded using MATLAB and converted into a binary stream.
2. **Encryption**: The binary data is encrypted by XORing it with a P-N sequence.
3. **Transmission**: The encrypted data is transmitted from one Raspberry Pi to another.
4. **Reception & Decryption**: The receiving Raspberry Pi uses the same P-N sequence to decrypt the data and restore the original audio signal.
5. **MATLAB Integration**: MATLAB libraries are used for seamless integration with the Raspberry Pi.

## Key Findings

- **Decryption Based on P-N Sequence Matching**: The system ensures that data can only be decrypted if the P-N sequences match between the transmitter and receiver.
- **MATLAB Libraries on Raspberry Pi**: Necessary MATLAB libraries are installed on the Raspberry Pi to handle the audio data transmission and reception efficiently.
- **Security Strength**: The project successfully demonstrates how P-N sequences can be used to ensure the confidentiality and integrity of the transmitted audio data.

## Installation

### Requirements
- **Raspberry Pi** (Model 3B+ or 4B)
- **MATLAB** (for processing and transmitting audio)
- **Raspberry Pi OS (Bullseye)** installed on the Raspberry Pi
- **Required Libraries**: MATLAB support for Raspberry Pi (see installation instructions below)

### Steps to Install

1. **Set up Raspberry Pi**:
   - Install the **Raspberry Pi OS (Bullseye)** on your Raspberry Pi.
   - Ensure you have access to the **GPIO pins**, **Wi-Fi**, and **Ethernet** connections.

2. **Install MATLAB Libraries**:
   - Download and install MATLAB on your local machine.
   - Set up the Raspberry Pi as a target device for MATLAB by following the official MATLAB Raspberry Pi setup guide.
   - Install the necessary libraries on the Raspberry Pi to interface with MATLAB.

3. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/audio-security-pn-sequence.git
   cd audio-security-pn-sequence
   
4. **Run the Code**:
    The code can be run directly from MATLAB. Make sure the Raspberry Pi is connected to the same network as your computer.
   
5. **GPIO Configuration**:
   Make sure to configure the GPIO pins on the Raspberry Pi to work with the system's transmission and reception logic.

## Usage

Once the system is set up, you can:

### Run the Audio Encryption and Transmission Process:

1. Use **MATLAB** to record audio, convert it to binary, and encrypt the data with the P-N sequence.
2. Transmit the encrypted data from one Raspberry Pi to another over the network.

### Decryption and Audio Restoration:

1. The second Raspberry Pi receives the encrypted data, decrypts it using the same P-N sequence, and converts it back into the original audio signal.

### Example Commands (MATLAB):

```matlab
% Record Audio
audioData = audioread('input.wav');

% Convert to Binary Stream
binaryData = audio2binary(audioData);

% Encrypt Data Using P-N Sequence
encryptedData = xor(binaryData, pnSequence);

% Transmit Data (over Raspberry Pi network)
sendDataToRaspberryPi(encryptedData);

% Decrypt Data on Receiver Side
decryptedData = xor(receivedData, pnSequence);

% Convert Back to Audio
outputAudio = binary2audio(decryptedData);
audiowrite('output.wav', outputAudio, 44100);

## 🤝 Authors

- **Kanawade Nandini Rajendra** (nandinikanawade@gmail.com)
- **Dunung Sourabhi Ashwin** (sourabhidunung@gmail.com)


## 📜 License

This project is open-source under the [MIT License](./LICENSE).

---

## 💬 Citation

If you use this project in your research or work, please cite:

> Kanawade, N. R, Dunung,S. A, (2023). *Audio Data Communication Security Using P-N Sequences and Raspberry Pi*.

## Acknowledgements

- Thanks to the **Raspberry Pi Foundation** for providing a powerful and flexible platform for this project.
- Special thanks to the **MATLAB community** for enabling integration with Raspberry Pi.
