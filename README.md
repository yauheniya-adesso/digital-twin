# Digital Twin Frontend

A fun interactive demo created for colleagues in the Data & Analytics (DNA) department at adesso. As new colleagues, we were invited to submit a creative video presentation with a max length of 40 seconds introducing ourselves. Being an AI engineer, I added some AI elements to my video presentation and built this web interface to make it interactive.

## Demo

🔗 **Live Demo**: [https://yauheniya-adesso.github.io/digital-twin](https://yauheniya-adesso.github.io/digital-twin)

## AI Components

This project demonstrates several AI techniques working together:

### 1. Portrait Matting
<div align="center">
  <figure>
    <img src="docs/portrait-matting.png" alt="Portrait Matting Process" />
    <figcaption>Figure 1: Background removal using rmbg-2.0 model</figcaption>
  </figure>
</div>

Used the pretrained **rmbg-2.0 model** from Hugging Face to remove the background and extract the body outline. This creates the moving avatar for the digital twin.

### 2. Wireframe Face Animation
<div align="center">
  <figure>
    <img src="docs/face-wireframe.png" alt="Face Wireframe Animation" />
    <figcaption>Figure 2: Real-time face tracking using MediaPipe</figcaption>
  </figure>
</div>

Implemented face tracking using **OpenCV and MediaPipe** to make the digital twin follow lip and face movements when talking, creating a more lifelike interaction.

### 3. Text-to-Speech (TTS)
<div align="center">
  <figure>
    <img src="docs/tts-demo.png" alt="Text-to-Speech" />
    <figcaption>Figure 3: Voice synthesis using Coqui TTS</figcaption>
  </figure>
</div>

Integrated a pretrained **Coqui TTS model** from Hugging Face to give voice to the digital twin, enabling natural spoken responses.

### 4. Agentic AI System
<div align="center">
  <figure>
    <img src="langgraph_visualization.png" alt="LangGraph Workflow" />
    <figcaption>Figure 4: Multi-agent RAG system with intelligent routing</figcaption>
  </figure>
</div>

Built a multi-agent AI system using **LangGraph** that:
- Intelligently routes questions to appropriate data sources (LinkedIn, GitHub, Medium)
- Uses RAG (Retrieval-Augmented Generation) with vector search for accurate responses
- Optimizes answers for natural text-to-speech output
- Handles multi-language queries with automatic translation to English

See the [backend repository](https://github.com/yauheniya-adesso/digital-twin-backend) for technical details.

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
- React 18

**Backend:**
- LangGraph (multi-agent orchestration)
- LangSmith (monitoring)
- OpenAI GPT-4 (language model)
- ChromaDB (vector store)
- Coqui TTS (text-to-speech)
- FastAPI (REST API)

**Deployment:**
- GitHub Pages (frontend)
- Hugging Face Spaces (backend)

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

**Animated DNA Background** - Custom CSS animation representing the DNA department DNA Strand 🧬 from Konstantin Denerz @[CodePen](https://codepen.io/konstantindenerz/pen/ExJZPZO)

## License

MIT