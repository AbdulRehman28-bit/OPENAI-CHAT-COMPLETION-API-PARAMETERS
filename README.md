# API Parameters Explained

This document provides a detailed explanation of key terms and parameters used in APIs. Each parameter plays a specific role in defining how requests are processed and responses are generated.

## Parameters and Terms

### **Messages**
- **Description**: Represents the conversation history or input data sent to the model. Typically formatted as an array of JSON objects.
- **Example**:
  ```json
  [
    {"role": "user", "content": "Hello, how are you?"},
    {"role": "assistant", "content": "I'm fine, thank you!"}
  ]
  ```

---

### **Model**
- **Description**: Specifies the AI model to use for generating responses. Different models have varying capabilities and token limits.
- **Example**: `gpt-4`, `gpt-3.5-turbo`.

---

### **Max Completion Tokens**
- **Description**: Defines the maximum number of tokens the model can generate in a response.
- **Purpose**: Helps control the length of the output.
- **Example**: Setting `max_completion_tokens` to `100` limits the response to approximately 100 tokens.

---

### **n**
- **Description**: Determines the number of response completions the model should generate.
- **Purpose**: Useful for comparing multiple response variations.
- **Example**: Setting `n` to `3` will return three different completions for the same input.

---

### **Stream**
- **Description**: If set to `true`, the response is delivered incrementally as a stream rather than as a complete message.
- **Purpose**: Enables real-time updates for applications like chat interfaces.
- **Example**: `"stream": true`.

---

### **Temperature**
- **Description**: Controls the randomness of the model's output. A higher value results in more diverse and creative responses, while a lower value makes the responses more focused and deterministic.
- **Range**: `0.0` to `2.0`.
- **Example**: 
  - `0.2` → More deterministic.
  - `1.5` → Highly creative and diverse.

---

### **Top_p**
- **Description**: An alternative to temperature for controlling randomness. Uses nucleus sampling to consider the smallest possible set of tokens whose cumulative probability exceeds `p`.
- **Range**: `0.0` to `1.0`.
- **Example**: 
  - `0.1` → Focused on the most likely tokens.
  - `0.9` → Allows more creative outputs.

---

### **Tools**
- **Description**: Refers to additional functions or APIs that the model can call during the conversation, such as browsing, code execution, or accessing databases.
- **Purpose**: Extends the model's capabilities beyond generating text.
- **Example**:
  - Browsing for live information.
  - Executing Python scripts.

---

## Notes
- Adjusting parameters like `temperature` and `top_p` simultaneously can result in unpredictable behavior. It is recommended to tweak only one at a time.
- Always consider token limits of the selected model, including tokens from the input (`messages`) and output (`max_completion_tokens`).
