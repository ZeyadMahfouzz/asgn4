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
python conversationalAgent.py
```
Choose an agent:
- `1` for Basic
- `2` for Chain of Thought (CoT)
- `3` for ReAct

## Example Conversations

### **Basic Mode**
```
You: Tell me about the weather in egypt for the next 5 days
Chatbot: The weather in Egypt for the next 5 days is expected to be mostly sunny with no chance of rain. 

On March 18th, it's expected to be sunny with a high of 29.7°C and a low of 16.8°C.

On March 19th, it's expected to be sunny with a high of 26.1°C and a low of 14.1°C.

On March 20th, it's expected to be sunny with a high of 20.6°C and a low of 11.9°C.

On March 21st, it's expected to be partly cloudy with a high of 18.4°C and a low of 11.4°C.

On March 22nd, it's expected to be partly cloudy with a high of 20.2°C and a low of 13.2°C.
```

### **Chain of Thought Mode**
```
You: Tell me about the weather in egypt for the next 5 days
Chatbot: The weather in Egypt for the next 5 days is expected to be sunny with no chance of rain. The maximum temperature will range from 20.2°C to 29.7°C, while the minimum temperature will range from 11.4°C to 16.8°C.
```

### **ReAct Mode**
```
You: Tell me about the weather in egypt for the next 5 days
Chatbot: The weather in Egypt for the next 5 days is expected to be mostly sunny with no chance of rain. The maximum temperatures will range from 29.7°C on the 18th to 18.4°C on the 21st, while the minimum temperatures will range from 16.8°C on the 18th to 11.4°C on the 21st. The conditions will be sunny for the first three days, followed by partly cloudy skies on the 21st and 22nd.
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
