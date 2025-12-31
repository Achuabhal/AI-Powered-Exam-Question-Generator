# AI-Powered Exam Question Generator

An intelligent system that analyzes syllabus PDFs and previous year question papers to generate important exam questions using Google Gemini AI. Built specifically for educational institutions to help students prepare for exams by identifying repeated concepts and important topics.

## 🚀 Tech Stack

### Backend (Python)
- **Flask** - Web framework
- **LangChain** - LLM orchestration framework
- **Google Gemini AI** - AI model for question generation
- **FAISS** - Vector database for semantic search
- **PyPDF2** - PDF text extraction
- **Flask-CORS** - Cross-origin resource sharing

### Frontend (React + Vite)
- **React 19** - UI framework
- **Vite** - Build tool and dev server
- **Tailwind CSS 4** - Styling framework
- **Axios** - HTTP client
- **React Router DOM** - Client-side routing
- **Recharts** - Data visualization
- **Lucide React** - Icon library
- **jsPDF & html2canvas** - PDF generation

## 📁 Project Structure

```
erp/
├── backend/
│   ├── app.py              # Flask API with AI integration
│   ├── requirements.txt    # Python dependencies
│   ├── .env               # Environment variables (API keys)
│   └── uploads/           # PDF storage folder
└── front end/
    ├── src/               # React source code
    ├── public/            # Static assets
    ├── package.json       # Node dependencies
    └── vite.config.js     # Vite configuration
```

## 🛠️ Installation & Setup

### Prerequisites
- Python 3.8+
- Node.js 16+
- Google Gemini API key ([Get it here](https://makersuite.google.com/app/apikey))

### Backend Setup

1. Navigate to backend directory:
```bash
cd backend
```

2. Create virtual environment (recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Create `.env` file and add your Google API key:
```env
GOOGLE_API_KEY=your_gemini_api_key_here
```

5. Run the Flask server:
```bash
python app.py
```

The backend will run on `http://localhost:5000`

### Frontend Setup

1. Navigate to frontend directory:
```bash
cd "front end"
```

2. Install dependencies:
```bash
npm install
```

3. Run the development server:
```bash
npm run dev
```

The frontend will run on `http://localhost:5173` (Vite default)

## 🎯 Features

### AI-Powered Question Generation
- Upload syllabus PDFs and previous year question papers
- Automatically extracts text from multiple PDF files
- Uses RAG (Retrieval Augmented Generation) with FAISS vector store
- Generates 10 important questions each from Part A and Part B
- Identifies repeated questions from previous years
- Focuses on key concepts, definitions, and problem-solving patterns

### Technical Features
- **Semantic Search**: Uses Google's embedding model for intelligent document retrieval
- **Context-Aware Generation**: Analyzes patterns across multiple documents
- **Temperature Control**: Set to 0.3 for consistent, focused output
- **Chunk Processing**: Splits large PDFs into manageable chunks (1000 chars with 100 char overlap)

## 📡 API Endpoints

### `GET /generate-questions`
Generates exam questions based on uploaded PDFs in the `uploads/` folder.

**Response:**
```json
{
  "questions": "Generated questions with Part A and Part B sections..."
}
```

**Errors:**
- `400`: No PDF files found
- `500`: Uploads folder not found or processing error

## 🔧 Configuration

### Environment Variables
Create a `.env` file in the `backend/` directory:
```env
GOOGLE_API_KEY=your_google_gemini_api_key
```

### Frontend Environment
The frontend uses Vite and is configured for Vercel deployment (see `vercel.json`).

## 📦 Dependencies

### Backend (Python)
- flask & flask-cors
- langchain, langchain-google-genai, langchain-community
- google-generativeai
- faiss-cpu
- PyPDF2
- python-dotenv

### Frontend (Node.js)
- react & react-dom (v19)
- vite (v7)
- tailwindcss (v4.1)
- axios, react-router-dom, recharts
- lucide-react, jspdf, html2canvas

## 🚀 Deployment

### Frontend
- Configured for Vercel deployment
- Build command: `npm run build`
- Output directory: `dist`

### Backend
- Can be deployed on Render, Railway, or similar Python hosting platforms
- Ensure environment variables are set
- Create `uploads/` folder in production environment

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

## 📄 License

This project is licensed under the MIT License.

## 👨‍💻 Author

**Abhal Benny**
- GitHub: [@Achuabhal](https://github.com/Achuabhal)

## 🔗 Links

- Repository: [https://github.com/Achuabhal/erp](https://github.com/Achuabhal/erp)
- Google Gemini API: [https://makersuite.google.com/app/apikey](https://makersuite.google.com/app/apikey)
