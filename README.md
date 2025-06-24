# AI Content Generator

A full-stack application that transforms any topic into engaging AI-generated videos or comprehensive YouTube-based learning paths. Built with React frontend and FastAPI backend.

## 🌟 Features

- **AI Video Generation**: Create educational videos with AI narration on any topic
- **Learning Path Creation**: Curated YouTube video roadmaps organized by skill level
- **Modern UI**: Beautiful, responsive interface with animations and glassmorphism design
- **Real-time Processing**: Live status updates during content generation
- **File Downloads**: Direct download links for generated content

## 🛠️ Tech Stack

### Frontend
- **React** with Hooks
- **Vanilla CSS** with animations
- **Responsive Design** with mobile-first approach

### Backend
- **FastAPI** for REST API
- **Python** for content generation
- **YouTube API v3** for learning path curation
- **MoviePy** for video processing
- **Uvicorn** ASGI server

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v16 or higher)
- **Python** (3.8 or higher)
- **ImageMagick** (required for video generation)
- **YouTube Data API v3 Key**

### Installing ImageMagick

#### Windows
1. Download from [ImageMagick official site](https://imagemagick.org/script/download.php#windows)
2. Install and add to PATH
3. Restart your terminal

#### macOS
```bash
brew install imagemagick
```

#### Ubuntu/Debian
```bash
sudo apt-get install imagemagick
```

## 🚀 Installation

### 1. Clone the Repository
```bash
git clone https://github.com/sandeep210204/AI-content-generator.git
cd ai-content-generator
```

### 2. Backend Setup

#### Install Python Dependencies
```bash
cd backend
pip install -r requirements.txt
```

#### Create Environment File
Create a `.env` file in the backend directory:
```env
YOUTUBE_API_KEY=your_youtube_api_key_here
```

#### Get YouTube API Key
1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project or select existing one
3. Enable YouTube Data API v3
4. Create credentials (API Key)
5. Copy the API key to your `.env` file

### 3. Frontend Setup

#### Install Node Dependencies
```bash
cd frontend
npm install
```

## 🎯 Project Structure

```
ai-content-generator/
├── frontend/
│   ├── src/
│   │   ├── App.jsx          # Main React component
│   │   └── ...
│   ├── package.json
│   └── ...
├── backend/
│   ├── main.py              # FastAPI server
│   ├── video_generator.py   # Video generation logic
│   ├── youtube_api.py       # Learning path creation
│   ├── requirements.txt
│   ├── .env                # Environment variables
│   ├── videos/             # Generated videos directory
│   └── learning_paths/     # Generated HTML files directory
└── README.md
```

## 🏃‍♂️ Running the Application

### 1. Start the Backend Server
```bash
cd backend
python main.py
```
The API will be available at `http://localhost:8000`

### 2. Start the Frontend Development Server
```bash
cd frontend
npm run dev
```
The application will be available at `http://localhost:5173`

## 📖 Usage

1. Open your browser and navigate to `http://localhost:5173`
2. Enter any topic you want to learn about
3. Choose content type:
   - **AI Video**: Generates educational video with AI narration
   - **Learning Path**: Creates structured YouTube video roadmap
4. Click "Generate Content" and wait for processing
5. View or download your generated content

## 🔧 API Endpoints

### POST `/generate`
Generate content based on topic and type.

**Request Body:**
```json
{
  "topic": "Machine Learning",
  "generation_type": "video" // or "learning_path"
}
```

**Response:**
```json
{
  "status": "success",
  "message": "Content generated successfully",
  "file": "filename.mp4",
  "url": "/videos/filename.mp4"
}
```

### GET `/health`
Check API health status.

### GET `/`
API information and available endpoints.

## 📁 Generated Content

- **Videos**: Stored in `backend/videos/` directory
- **Learning Paths**: Stored in `backend/learning_paths/` directory
- **Static Files**: Served via FastAPI static file mounting

## 🎨 Features in Detail

### AI Video Generation
- Automatic script creation based on topic
- AI-powered narration
- Visual elements and animations
- Downloadable MP4 format

### Learning Path Creation
- 6-level structured roadmap (Fundamentals → Expert)
- YouTube video curation via API
- Interactive HTML interface
- Progress tracking
- Responsive design

### UI/UX Features
- Glassmorphism design
- Floating animations
- Hover effects
- Loading states
- Error handling
- Mobile responsive

## ⚠️ Troubleshooting

### Common Issues

**ImageMagick Not Found**
- Ensure ImageMagick is installed and in PATH
- Restart terminal after installation
- Check MoviePy configuration

**YouTube API Quota Exceeded**
- Each API key has daily quota limits
- Create multiple API keys if needed
- Monitor usage in Google Cloud Console

**CORS Issues**
- Ensure frontend runs on `http://localhost:5173`
- Check CORS middleware configuration in `main.py`

**Video Generation Fails**
- Check ImageMagick installation
- Verify write permissions in videos directory
- Check server logs for detailed errors

## 🔐 Environment Variables

Create a `.env` file in the backend directory:
```env
# Required
YOUTUBE_API_KEY=your_youtube_api_key_here

# Optional
OPENAI_API_KEY=your_openai_key_here  # If using OpenAI for narration
MAX_VIDEO_DURATION=300  # Maximum video length in seconds
```

## 📦 Dependencies

### Backend (`requirements.txt`)
```txt
fastapi==0.104.1
uvicorn[standard]==0.24.0
python-multipart==0.0.6
python-dotenv==1.0.0
requests==2.31.0
moviepy==1.0.3
pydantic==2.5.0
```

### Frontend (`package.json`)
```json
{
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0"
  },
  "devDependencies": {
    "@vitejs/plugin-react": "^4.0.3",
    "vite": "^4.4.5"
  }
}
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

If you encounter any issues or have questions:

1. Check the [Troubleshooting](#-troubleshooting) section
2. Look through existing GitHub issues
3. Create a new issue with detailed information
4. Include error logs and system information

## 🚧 Future Enhancements

- [ ] Multiple AI narration voices
- [ ] Custom video templates
- [ ] User authentication
- [ ] Content history/favorites
- [ ] Social sharing features
- [ ] Advanced learning path customization
- [ ] Integration with more video platforms

---

**Made with ❤️ using React and FastAPI**
