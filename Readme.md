# **Ollama Complete Models Guide**

---

## **1. OLLAMA (Local - 100% Free)**

### **Popular Models & Details**

| Model | Parameters | Size on Disk | Context | Speed (tokens/sec) | Hardware Required | Response Time |
|-------|-----------|--------------|---------|-------------------|-------------------|---------------|
| **Phi-3 Mini** | 3.8B | 2.3 GB | 128K | 50-80 | 4GB RAM, CPU only | 2-4 sec |
| **Llama 3.2** | 3B | 2 GB | 128K | 45-75 | 4GB RAM, CPU only | 2-5 sec |
| **TinyLlama** | 1.1B | 637 MB | 2K | 80-120 | 2GB RAM, CPU only | 1-2 sec |
| **Mistral 7B** | 7B | 4.1 GB | 32K | 30-50 | 8GB RAM, CPU | 4-6 sec |
| **Gemma 2 9B** | 9B | 5.5 GB | 8K | 25-40 | 8GB RAM, CPU/GPU | 5-8 sec |
| **Llama 3.1 8B** | 8B | 4.7 GB | 128K | 30-45 | 8GB RAM, CPU/GPU | 4-7 sec |
| **Qwen 2.5 7B** | 7B | 4.4 GB | 32K | 28-45 | 8GB RAM, CPU | 5-7 sec |
| **DeepSeek Coder 7B** | 6.7B | 3.8 GB | 16K | 32-48 | 8GB RAM, CPU | 4-6 sec |
| **Llama 3.1 70B** | 70B | 40 GB | 128K | 5-10 | 32GB RAM + GPU 24GB | 15-30 sec |
| **Qwen 2.5 72B** | 72B | 41 GB | 32K | 4-8 | 32GB RAM + GPU 24GB | 20-40 sec |

### **Best For <10 Seconds Response**

**CPU Only:**
- Phi-3 Mini (3.8B) - 2-4 sec
- TinyLlama (1.1B) - 1-2 sec
- Llama 3.2 (3B) - 2-5 sec
- Mistral 7B - 4-6 sec

**With GPU (8GB+ VRAM):**
- Mistral 7B - 2-3 sec
- Llama 3.1 8B - 2-4 sec
- Gemma 2 9B - 3-5 sec
- Qwen 2.5 7B - 3-5 sec

### **Hardware Requirements Summary**

| Hardware | Recommended Models | Expected Speed |
|----------|-------------------|----------------|
| **Laptop (4GB RAM, CPU)** | Phi-3, TinyLlama, Llama 3.2 | 1-5 sec |
| **Normal PC (8GB RAM, CPU)** | Mistral 7B, Llama 3.1 8B, Qwen 7B | 4-7 sec |
| **Gaming PC (16GB RAM, 8GB GPU)** | All 7B-9B models | 2-5 sec |
| **High-end (32GB RAM, 24GB GPU)** | 70B models | 15-30 sec |

### **Installation & Usage**

---

## **2. TOGETHER AI (Cloud - Paid with Free Tier)**

### **Free Models (3 Months Free Access)**

| Model | Parameters | Context | Speed | Input Price | Output Price | Best For |
|-------|-----------|---------|-------|-------------|--------------|----------|
| **Llama 3.3 70B Turbo Free** | 70B | 128K | Fast | FREE | FREE | General chat, reasoning |
| **FLUX.1 Schnell Free** | Image Gen | N/A | 315ms | FREE | FREE | Image generation |

### **Popular Paid Models**

| Model | Parameters | Context | Input ($/1M) | Output ($/1M) | Best Use |
|-------|-----------|---------|--------------|---------------|----------|
| **DeepSeek-R1** | 671B MoE | 128K | $2.20 | $10.50 | Advanced reasoning |
| **Llama 3.1 8B** | 8B | 128K | $0.18 | $0.18 | Fast general tasks |
| **Mistral 7B** | 7B | 32K | $0.20 | $0.20 | Quick responses |
| **Qwen 2.5 72B** | 72B | 32K | $0.60 | $0.60 | Multilingual |
| **Gemma 2 9B** | 9B | 8K | $0.20 | $0.20 | Coding |

### **Key Features**
- **Free Tier**: Limited free calls/month
- **Speed**: Optimized inference (4x faster than vLLM)
- **Pay-per-token**: No subscription required
- **Hardware**: Cloud-based (no local hardware needed)

### **Response Time Estimate**
- 7B-8B models: 1-3 seconds
- 70B models: 3-8 seconds
- Image generation: <1 second

---

## **3. OPENROUTER (Cloud - Unified Gateway)**

### **Free Models Available**

| Model | Parameters | Context | Provider | Input Price | Output Price |
|-------|-----------|---------|----------|-------------|--------------|
| **Llama 4 Maverick** | 17B MoE | 128K | Meta | FREE | FREE |
| **DeepSeek R1 70B** | 70B | 128K | DeepSeek | FREE | FREE |
| **DeepSeek Chat V3** | 671B MoE | 64K | DeepSeek | FREE | FREE |
| **Gemini 2.0 Flash** | N/A | 1M | Google | FREE | FREE |
| **Gemma 2 9B** | 9B | 8K | Google | FREE | FREE |
| **Gemma 3 27B** | 27B | 8K | Google | FREE | FREE |
| **Llama 3.3 70B** | 70B | 128K | Meta | FREE | FREE |
| **Mistral Nemo** | 12B | 131K | Mistral | FREE | FREE |
| **QwQ 32B** | 32B | 32K | Qwen | FREE | FREE |

### **Rate Limits**
- **<10 credits**: 50 free requests/day
- **≥10 credits** ($10): 1000 requests/day

### **Key Features**
- **200+ models** from all major providers
- **Unified API**: OpenAI-compatible
- **Auto-fallback**: If one model fails, routes to another
- **No subscription**: Pay only for what you use
- **Zero completion insurance**: Only pay for successful runs

### **Paid Models (Popular)**

| Model | Parameters | Input ($/1M) | Output ($/1M) |
|-------|-----------|--------------|---------------|
| GPT-5 | N/A | $3.00 | $15.00 |
| Claude Opus 4.1 | N/A | $15.00 | $75.00 |
| Claude Sonnet 4 | N/A | $3.00 | $15.00 |
| Gemini 2.5 Pro | N/A | $2.50 | $10.00 |

### **Response Time Estimate**
- Free models: 3-10 seconds (depends on server load)
- Paid models: 1-5 seconds
- Rate-limited during peak times

---

## **Quick Comparison**

| Feature | Ollama | Together AI | OpenRouter |
|---------|--------|-------------|------------|
| **Cost** | 100% Free | Free tier + Paid | Free tier + Paid |
| **Hardware Needed** | YES (Local) | NO (Cloud) | NO (Cloud) |
| **Internet Required** | NO | YES | YES |
| **Privacy** | 100% Private | Cloud-based | Cloud-based |
| **Response Speed** | 1-30 sec (hardware dependent) | 1-8 sec | 3-10 sec |
| **Model Count** | 100+ | 200+ | 200+ |
| **Best For** | Privacy, offline use | Speed, reliability | Model variety, experimentation |

---

## **Recommendations**

### **For <10 Second Responses:**

**Ollama (Local):**
- Use 3B-9B models with good hardware
- Phi-3 Mini, Mistral 7B, Llama 3.1 8B
- Requires 8GB RAM minimum

**Together AI (Cloud):**
- Free 70B model responds in 3-8 seconds
- No hardware needed
- Best for occasional use

**OpenRouter (Cloud):**
- Free Llama 3.3 70B responds in 4-8 seconds
- Free Gemini 2.0 Flash very fast
- Good for testing multiple models

### **Best Choice by Use Case:**

- **Privacy-first**: Ollama
- **Best performance**: Together AI (paid)
- **Most variety**: OpenRouter
- **Budget-friendly**: Ollama > OpenRouter Free > Together AI Free
