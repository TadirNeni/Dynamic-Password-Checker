# ⚡ Dynamic Key Evaluator

A client-side, real-time cryptographic strength analyzer. 

Unlike standard password meters that rely on arbitrary regular expressions (e.g., "must contain one uppercase letter"), this tool mathematically evaluates keys by calculating their **Shannon Entropy** dynamically as the user types. It provides instant visual feedback on cryptographic strength and brute-force vulnerability.

**[🔴 Live Demo: Test the Evaluator Here](https://tadirneni.github.io/Dynamic-Password-Evaluator)** *(Note: Ensure your GitHub Pages link matches the URL above)*

## 🚀 Key Features

* **Real-Time Math:** Calculates Shannon Entropy ($E = L \times \log_2(R)$) on every keystroke, dynamically adjusting the character pool size ($R$) based on the specific character sets present in the input.
* **Brute-Force Estimation:** Translates raw entropy bits into a human-readable "Time-to-Crack" metric, mapped against a theoretical offline GPU cluster capable of 10 billion hashes per second.
* **Zero-Trust Architecture:** Operates 100% locally in the browser via Vanilla JavaScript. No data is ever transmitted over the network, ensuring complete user privacy.
* **Reactive UI/UX:** Features a modern, glassmorphism-inspired interface with a dynamic strength meter that provides immediate visual feedback.

## 🛠️ Tech Stack
* **Frontend:** HTML5, CSS3
* **Logic:** Vanilla JavaScript (No external libraries or dependencies)
* **Hosting:** GitHub Pages

## 🧠 The Cryptographic Logic

The evaluator determines the size of the character pool ($R$) dynamically:
* Lowercase letters (a-z): +26
* Uppercase letters (A-Z): +26
* Numbers (0-9): +10
* Symbols (!@#$ etc.): +32

The total Shannon Entropy ($E$) is then calculated using the pool size and the length of the string ($L$). This accurately demonstrates to users that a long passphrase of simple words (high $L$) is often mathematically stronger than a short password with high complexity (high $R$).

## ⚙️ Local Usage

Since this is a client-side application, no server environment is required.

1. Clone the repository:
   ```bash
   git clone [https://github.com/TadirNeni/Dynamic-Password-Evaluator.git](https://github.com/TadirNeni/Dynamic-Password-Evaluator.git)
