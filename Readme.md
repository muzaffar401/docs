# **Ollama Models Documentation**

## **1. Introduction**

Ollama is a lightweight, local-first platform designed to run Large Language Models (LLMs) efficiently on your machine. It provides an easy way to download, manage, and serve models through simple terminal commands or API usage. This documentation explains how Ollama works, how different models compare, and how to use them in single-agent and multi-agent architectures.

---

## **2. What is Ollama?**

Ollama is a **local inference engine** that:

- Runs LLMs locally (CPU or GPU)
- Provides a simple CLI and REST API
- Handles model downloading, caching, quantization, and execution
- Supports multiple open‑source models

**Why developers use Ollama:**

- No cloud costs
- Full data privacy
- Fast inference due to local hardware
- Simple integration with Python, Node.js, Go, etc.

---

## **3. How Ollama Models Work**

Each model in Ollama is downloaded as a `.gguf` file (quantized format). Ollama optimizes these files for fast runtime and low resource usage.

### **Key components:**

| Component    | Role                                                   |
| ------------ | ------------------------------------------------------ |
| Model file   | Quantized `.gguf` version of the LLM                   |
| Runtime      | Handles prompt parsing, batching, and inference        |
| Template     | Pre-prompt formatting (system prompt style)            |
| Model config | Defines parameters like temperature, stop tokens, etc. |

---

## **4. Popular Ollama Models and Their Use-Cases**

Below is a comparison of the most commonly used models:

### **Table: Model Comparison**

| Model                 | Size   | Strengths                                       | Weaknesses                          | Use-case                 |
| --------------------- | ------ | ----------------------------------------------- | ----------------------------------- | ------------------------ |
| **LLaMA 3.1 8B/70B**  | 8B–70B | Balanced performance, good reasoning            | 8B sometimes weak in deep reasoning | Chatbots, assistants     |
| **Mistral 7B**        | 7B     | Fast, lightweight                               | Not ideal for complex reasoning     | Apps needing speed       |
| **Gemma 2 9B/27B**    | 9B–27B | Very accurate, strong coding                    | Larger models need more RAM         | Coding agents, RAG       |
| **Qwen 2.5 7B/72B**   | 7B–72B | One of the best multilingual & reasoning models | Very large file size for 72B        | Multi-agent systems, RAG |
| **Phi-3 Mini/Medium** | 3B–14B | Very efficient on small hardware                | Limited reasoning                   | Mobile/edge usage        |

---

## **5. How Ollama Performs in Multi-Agent Architectures**

A multi-agent system means:

- Multiple AI agents working together
- Each agent may have a different role
- Agents communicate with each other using messages

### **Does Ollama support multi-agent architectures?**

Yes — **but it depends on hardware and model size**.

### **Latency Considerations**

| Situation                                     | Latency Level                               |
| --------------------------------------------- | ------------------------------------------- |
| Single small model (3B–7B)                    | Low                                         |
| Multiple agents using the same model          | Medium                                      |
| Multiple agents using different 7B–14B models | Medium to high                              |
| Multiple 70B models                           | Very high / Not feasible without strong GPU |

### **Why latency increases?**

1. Models must load into RAM
2. Each agent call is sequential unless you use multi-threading
3. Larger models require more VRAM for each inference

### **How to reduce latency?**

- Use quantized models (`q4_K_M`, `q5_K_M`)
- Use smaller versions (7B or 8B)
- Share the same model instance across agents
- Enable server mode `ollama serve`
- Use batching for message processing

---

## **6. Using Ollama in Real Projects**

### **Set up the server**

```bash
ollama serve
```

### **Pull a model**

```bash
ollama pull llama3.1:8b
```

### **Generate text**

```bash
ollama run llama3.1:8b "Explain quantum computing simply"
```

---

## **7. Using Ollama Through the API**

Ollama exposes a REST API at:

```
http://localhost:11434
```

### **Example: Python Integration**

```python
import requests

response = requests.post(
    "http://localhost:11434/api/generate",
    json={"model": "llama3.1:8b", "prompt": "Write a poem."}
)

print(response.json()["response"])
```

### **Example: Node.js Integration**

```javascript
import fetch from "node-fetch";

const res = await fetch("http://localhost:11434/api/generate", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ model: "llama3.1:8b", prompt: "Hello" })
});

const data = await res.json();
console.log(data.response);
```

---

## **8. Multi-Agent Implementation Example**

### **Architecture Overview**

- **Agent 1:** Retrieval Agent (search + data retrieval)
- **Agent 2:** Reasoning Agent (deep thinking model)
- **Agent 3:** Writer Agent (creates final answer)

### **Best Model Choices**

| Agent Type      | Recommended Model  |
| --------------- | ------------------ |
| Retrieval Agent | Mistral 7B / Phi-3 |
| Reasoning Agent | Qwen 7B / Qwen 32B |
| Writer Agent    | LLaMA 3.1 8B       |

---

## **9. Hardware Requirements**

| Model Size | RAM Needed | Ideal Hardware           |
| ---------- | ---------- | ------------------------ |
| 3B–7B      | 4–8 GB     | Normal laptop            |
| 8B–14B     | 8–16 GB    | Gaming laptop or mid GPU |
| 30B–70B    | 32–64 GB   | High-end GPU (24GB+)     |

---

## **10. When to Use Which Model?**

**Use small models when:**

- You need real-time responses
- Running multiple agents
- Using limited hardware

**Use large models when:**

- You need strong reasoning
- Deep problem solving
- Code generation

---

## **11. Pros & Cons of Ollama**

### **Pros**

- Free & open-source
- Fast local inference
- Easy API
- Secure & private

### **Cons**

- Limited by hardware
- Large models can be slow
- Not ideal for very large-scale apps

---

## **12. Conclusion**

Ollama is powerful for developers who want to run AI locally. With the right model selection and proper architecture design, it can support even complex multi-agent systems. However, model size and hardware significantly impact latency.

