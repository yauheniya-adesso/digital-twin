# Digital Twin Frontend

A fun interactive demo created for colleagues in the Data & Analytics (DNA) department at adesso SE. As new colleagues, we were invited to submit a creative video presentation with a max length of 40 seconds introducing ourselves. Being an AI engineer, I added some AI elements to my video presentation and built this web interface to make it interactive.

## Demo

✨ **Live Demo**: [https://yauheniya-adesso.github.io/digital-twin](https://yauheniya-adesso.github.io/digital-twin)

## AI Components

This project demonstrates several AI techniques working together:

### 1. Portrait Matting
<div style="text-align: center;">
  <img src="digital_twin_portrait_matting.png" alt="Portrait Matting Process" />  
  <br><strong>Figure 1: Background removal using rmbg-2.0 model</strong>
</div>

<br>Used the pretrained **rmbg-2.0 model** from Hugging Face to remove the background and extract the body outline. This creates the moving avatar for the digital twin. Before finding this model, I experimented with several other portrait matting solutions including MODNet and rembg, but none of them preserved fine details like hair strands or achieved the high-quality edge definition needed for a professional result. 

### 2. Wireframe Face Animation
<div style="text-align: center;">
  <img src="digital_twin_face_wireframe.png" alt="Face Wireframe Animation" />  
  <br><strong>Figure 2: Real-time face tracking using MediaPipe </strong>
</div>

<br>Implemented face tracking using **OpenCV and MediaPipe** to make the digital twin follow lip and face movements when talking, creating a more lifelike interaction. This was achieved by processing a pre-recorded video, which makes the implementation straightforward and efficient. MediaPipe detects facial landmarks (478 key points on the face) in real-time, while OpenCV handles video frame processing and rendering, allowing the wireframe to accurately track facial expressions and mouth movements frame by frame.

### 3. Agentic AI System
<div style="text-align: center;">
  <img src="langgraph_visualization.png" alt="LangGraph Workflow" />  
  <br><strong>Figure 3: Multi-agent RAG system with intelligent routing</strong>
</div>

<br>Built a multi-agent AI system using **LangGraph** that:
- Intelligently routes questions to appropriate data sources (LinkedIn, GitHub, Medium)
- Uses Retrieval-Augmented Generation (RAG) with vector search for accurate responses
- Handles multi-language queries with automatic translation to English
- Optimizes answers for natural text-to-speech output

See the [backend repository](https://github.com/yauheniya-adesso/digital-twin-backend) for technical details.

### 4. Text-to-Speech (TTS)
<div style="text-align: center;">
  <img src="digital_twin_audio_output.png" alt="Text-to-Speech" />  
  <br><strong>Figure 4: Voice synthesis using Coqui TTS</strong>
</div>

<br>Integrated a pretrained **Coqui TTS model** from Hugging Face to give voice to the digital twin, enabling natural spoken responses. The digital twin was originally designed to provide audio output, and the local model successfully generates voice responses. However, due to deployment constraints on platforms like Render and Hugging Face Spaces, the current live demo returns text-only responses. The full audio functionality remains available when running the backend locally.

## Features

**Interactive Chat Interface** - Ask questions about my professional background and projects  
**Mobile-Optimized** - Responsive design for QR code access  
**Smart Suggestions** - Rotating placeholder questions to guide users  
**Voice Responses** - Text-to-speech output for accessibility (when enabled)

##  Monitoring

The system integrates with LangSmith for complete observability:

- Query routing decisions
- Context retrieval results
- LLM prompts and responses
- Token usage and latency
- Error tracking

## Technology Stack

**Frontend:**  
- <img src="https://api.iconify.design/logos:react.svg" alt="React" width="12" height="12" /> React 18

**Backend:**
- <img src="https://api.iconify.design/simple-icons:langgraph.svg?color=%231C3C3C" alt="LangGraph" width="12" height="12" /> LangGraph (multi-agent orchestration)
- <img src="https://api.iconify.design/simple-icons:langchain.svg?color=%231C3C3C" alt="LangSmith" width="12" height="12" /> LangSmith (monitoring)
- <img src="https://api.iconify.design/simple-icons:openai.svg" alt="OpenAI" width="12" height="12" /> OpenAI GPT-4 (language model)
- ChromaDB (vector store)
- Coqui TTS (text-to-speech)
- <img src="https://api.iconify.design/logos:fastapi-icon.svg" alt="FastAPI" width="12" height="12" /> FastAPI (REST API)

**Deployment:**
- <img src="https://api.iconify.design/mdi:github.svg" alt="GitHub" width="12" height="12" /> GitHub Pages (frontend)
- <img src="hf-icon.svg" alt="Hugging Face" width="12" height="12" /> Hugging Face Spaces (backend)

## Future Enhancements

**Advanced Voice Cloning & Facial Animation:**
- Record a video sample with voice to capture authentic wireframe movements and facial expressions
- Clone my voice using state-of-the-art voice synthesis models for a personalized speech pattern
- Synchronize the digital twin's lip movements and facial animations with the cloned voice in real-time
- Replicate my typical speaking mannerisms and facial expressions for a more natural interaction

**Infrastructure Improvements:**
- Migrate backend to a platform that supports hosting custom voice models
- Enable real-time streaming of voice responses for lower latency
- Implement GPU acceleration for faster speech synthesis

## Acknowledgements

- **Animated DNA Background** – Custom CSS animation representing the DNA department DNA Strand 🧬 from Konstantin Denerz @[CodePen](https://codepen.io/konstantindenerz/pen/ExJZPZO)  
- **Portrain Matting** – [briaai/RMBG-2.0](https://huggingface.co/briaai/RMBG-2.0)
- **Audio Output** – [coqui-ai/TTS](https://github.com/coqui-ai/TTS)

## License

MIT