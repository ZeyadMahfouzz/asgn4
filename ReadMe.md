# Weather Chatbot with Groq API

## Overview
This project implements an AI-powered chatbot that provides weather updates, mathematical calculations, and general knowledge search. The chatbot supports three reasoning strategies:

1. **Basic**: Directly returns responses.
2. **Chain of Thought (CoT)**: Breaks down responses into logical steps.
3. **ReAct**: Uses iterative reasoning and tool-based actions.

## Features
- **Live Weather Updates**: Uses WeatherAPI to fetch real-time weather conditions and forecasts.
- **Mathematical Evaluations**: Computes arithmetic expressions dynamically.
- **Knowledge Search Simulation**: Provides predefined responses for general inquiries.
- **Multi-Mode Reasoning**: Users can select between Basic, CoT, and ReAct models.

## Setup Instructions

### 1. Install Dependencies
Ensure you have Python 3.8+ installed, then install required libraries:
```sh
pip install groq python-dotenv requests
```

### 2. Configure API Keys
Create a `.env` file in the project directory and add:
```
API_KEY=your_groq_api_key
WEATHER_API_KEY=your_weather_api_key
LLM_MODEL=your_llm_model
```

### 3. Running the Chatbot
Execute the script and select an agent type:
```sh
python chatbot.py
```
Choose an agent:
- `1` for Basic
- `2` for Chain of Thought (CoT)
- `3` for ReAct

## Example Conversations

### **Basic Mode**
```
User: What's the weather in London?
Chatbot: It's 15°C and cloudy in London.
```

### **Chain of Thought Mode**
```
User: What's the weather like?
Chatbot: First, I need to get the current weather. Fetching data...
Chatbot: It's 20°C and sunny in New York.
```

### **ReAct Mode**
```
User: Compare New York and Tokyo weather.
Chatbot: Thinking... I need to fetch weather for both cities.
Chatbot: New York is 22°C and sunny. Tokyo is 18°C and rainy.
```

## Analysis of Reasoning Strategies
| Strategy | Accuracy | Clarity | Response Time |
|----------|----------|---------|--------------|
| **Basic** | Medium | Low | Fast |
| **CoT** | High | Medium | Medium |
| **ReAct** | Very High | High | Slow |

## Challenges and Solutions
| Challenge | Solution |
|-----------|----------|
| Handling API failures | Added exception handling and retries |
| Extracting structured responses | Used defined response formatting |
| Enhancing accuracy | Used reasoning strategies for complex queries |

## Future Improvements
- Optimize response speed for ReAct mode.
- Expand knowledge database for search functionality.
- Integrate real-time streaming for interactive conversations.

## References
- [Groq API Documentation](https://console.groq.com/docs/quickstart)
- [WeatherAPI Documentation](https://www.weatherapi.com/)
