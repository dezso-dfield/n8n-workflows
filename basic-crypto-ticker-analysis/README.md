# 📊 Basic Crypto Ticker Analysis Workflow

![Workflow Diagram](./image.png)

This workflow automates **crypto market preprocessing, analysis, decision-making, and trade logging** using a mix of:

- HTTP API calls  
- Python technical analysis  
- AI-assisted reasoning  
- Database write-back for trades and portfolio updates  

---

## 🚀 Overview

This system performs:

1. **Preprocessing #1**  
   - Loops over crypto tickers  
   - Fetches market data from an API  
   - Cleans/transforms the values in JavaScript  

2. **Preprocessing #2**  
   - Another loop over tickers  
   - Python tool performs technical/quantitative analysis  
   - Outputs indicators into memory  

3. **AI-Powered Decision Making**  
   - An **Ollama chat model** receives market context  
   - The agent interprets indicators and market state  
   - Produces decisions such as:  
     - Enter trade  
     - Close position  
     - Hold  
     - Update portfolio expectations  

4. **Trade Logging**  
   - Creates/updates the trade history  
   - Inserts rows into data tables  
   - Updates portfolio values  
   - Stores the final decision/output  

---

## 🧩 Components

### 🔁 Loop Over Items  
Iterates through the list of cryptocurrencies.

### 🌍 HTTP Request Block  
Fetches real-time ticker data.

### 🧮 Python Analysis  
Performs quantitative evaluations (RSI, EMA, ATR, trend checks, etc.)

### 🧠 AI Agent  
Uses an Ollama model to:
- Combine technical data + market data
- Make trade recommendations
- Output human-readable explanations or structured decisions

### 🧾 Multiple Data Table Inserts  
Stores:
- Active trades  
- Trade history  
- Portfolio updates  
- Final trade results  

---

## ▶️ How To Use

### **1. Configure API Key & Tickers**
Edit your HTTP request block to include:
- API base URL  
- Crypto symbols (e.g., `BTCUSDT`, `ETHUSDT`)  
- Headers / Auth Keys  

### **2. Run Preprocessing Workflows**
This populates the temporary variables used by the AI model.

### **3. Configure Ollama**
Install your preferred model:

```bash
ollama pull llama3
ollama pull mistral
```