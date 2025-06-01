# Multi-Agent LLM Interface 🤖

A beautiful, modern web interface for interacting with specialized AI agents powered by TinyLLaMA and TinyDolphin models running locally via Ollama.

✨ Features

4 Specialized AI Agents:

🧠 ResearchBot - Technical and academic questions
💡 CreativeBot - Stories, poems, and creative content
💼 ResumeBot - Resume feedback and career assistance
📝 SummaryBot - Text summarization and analysis

Modern UI/UX:

Dark theme with animated gradients
Floating particle effects
Responsive design for all devices
File upload support (PDF/TXT)
Download responses as PDF

Local AI Processing:

Runs entirely on your machine
No data sent to external services
Privacy-focused approach

🚀 Quick Start
Prerequisites

Ollama installed on your system
Python 3.8+ (for backend server)
Modern web browser

1. Install Ollama Models
bash# Pull the required models
ollama pull tinyllama:latest
ollama pull tinydolphin:latest

# Verify models are installed

ollama list
2. Clone and Setup
bash# Clone the repository
git clone <your-repo-url>
cd multi-agent-llm-interface

# Install Python dependencies

pip install -r requirements.txt
3. Start the Backend Server
bash# Start the Flask backend
python backend/app.py
4. Open the Frontend
Open index.html in your web browser or serve it with a local server:
bash# Option 1: Direct file access
open index.html

# Option 2: Python HTTP server

python -m http.server 8080

# Then visit <http://localhost:8080>


🔧 Configuration
Model Assignments
Edit backend/config.py to customize which models power each agent:
pythonAGENT_MODELS = {
    "ResearchBot": "tinyllama:latest",
    "CreativeBot": "tinydolphin:latest",
    "ResumeBot": "tinyllama:latest",
    "SummaryBot": "tinydolphin:latest"
}
Ollama Settings
pythonOLLAMA_BASE_URL = "<http://localhost:11434>"
MAX_TOKENS = 2048
TEMPERATURE = 0.7


Select an Agent: Click on any agent card to expand it
Upload Files (optional): Upload PDF or TXT files for context
Enter Prompt: Type your question or request
Get Response: Click the agent button to get AI-generated response
Download: Save responses as PDF files

Example Prompts
ResearchBot:
Analyze the latest trends in quantum computing and their potential impact on cryptography
CreativeBot:
Write a short story about a robot learning to paint in a post-apocalyptic world
ResumeBot:
Review my software engineer resume and suggest improvements for FAANG applications
SummaryBot:
Summarize this 50-page research paper on climate change mitigation strategies
🔧 Development
Backend Development
bash# Install development dependencies
pip install -r requirements-dev.txt


🚀 Deployment
Local Network Access
bash# Make accessible on local network
python backend/app.py --host 0.0.0.0 --port 5000
Docker Deployment
bash# Build and run with Docker
docker build -t multi-agent-llm .
docker run -p 5000:5000 -p 8080:8080 multi-agent-llm
🛠️ Troubleshooting
Common Issues
Ollama Connection Error:
bash# Check if Ollama is running
ollama list

# Start Ollama service

ollama serve
Models Not Found:
bash# Re-pull models
ollama pull tinyllama:latest
ollama pull tinydolphin:latest
CORS Issues:

Ensure backend CORS headers are properly configured
Use http:// instead of file:// protocol

Performance Tips

GPU Acceleration: Ensure Ollama uses GPU if available
Memory: Allocate sufficient RAM for model loading
Concurrent Requests: Limit simultaneous agent requests

🤝 Contributing

Fork the repository
Create a feature branch (git checkout -b feature/amazing-feature)
Commit changes (git commit -m 'Add amazing feature')
Push to branch (git push origin feature/amazing-feature)
Open a Pull Request

📝 License
This project is licensed under the MIT License - see the LICENSE file for details.
🙏 Acknowledgments

Ollama for local LLM serving
TinyLLaMA model
TinyDolphin model
Font Awesome for icons
TailwindCSS for styling

📊 Roadmap

 Add more specialized agents
 Implement conversation history
 Add model switching capability
 Create mobile app version
 Add voice input/output
 Implement agent collaboration
 Add plugin system

Made with ❤️ for the local AI community
