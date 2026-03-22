# 🌐 Frontend PRD – LearnWise AI

> Personalized learning platform UI for discovering the *right* resources based on how you learn.

---

## 🧠 Overview

### 🎯 Objective
Build a modern, responsive frontend that:
- Personalizes learning experience  
- Displays smart recommendations  
- Provides intuitive navigation & clean UI  

---

### 👥 Target Users
- Beginner developers  
- Students  
- Self-learners  

---

### 🧩 Core Capabilities
- User onboarding & profiling  
- Resource discovery & filtering  
- Multi-dimensional rating UI  
- Personalized recommendations  
- Learning path visualization  

---

## 🏗️ Tech Stack

- **Framework:** React.js (or Next.js)  
- **Styling:** Tailwind CSS  
- **State Management:** Context API / Redux Toolkit  
- **Routing:** React Router  
- **API Calls:** Axios / Fetch  
- **Optional UI:** Framer Motion (animations)  

---

## 🧱 Application Structure
    src/
    ├── components/       # Reusable UI components
    ├── pages/            # Page components (Home, Profile, Resource Detail)
    ├── services/         # API calls and business logic
    ├── context/          # State management (if using Context API)
    ├── hooks/            # Custom React hooks
    ├── utils/            # Utility functions
    └── App.js            # Main application component


---

## 📱 Core Pages

---

### 🏠 Home Page

#### Purpose
- Introduce product  
- Guide user to onboarding  

#### Features
- Hero section  
- CTA: “Start Learning”  
- Brief explanation  

---

### 🧠 Onboarding / Profile Setup

#### Purpose
Collect user preferences

#### Inputs
- Skill level  
- Learning style  
- Learning speed  

#### Output
- Save profile → used for recommendations  

---

### 🔍 Explore Page

#### Purpose
Discover resources

#### Features
- Search bar  
- Filters:
  - Topic  
  - Type (video/blog/course)  
  - Learning type  

- Resource cards  

---

### 📄 Resource Details Page

#### Purpose
Show detailed information

#### Features
- Title + link  
- Ratings breakdown  
- Tags (Beginner, Visual, etc.)  
- “Why recommended” section  
- Add rating  

---

### 👤 Profile Page

#### Purpose
User dashboard

#### Features
- User preferences  
- Saved resources  
- Progress tracking  

---

### ➕ Add Resource Page

#### Purpose
Allow users to contribute

#### Inputs
- Title  
- Link  
- Topic  
- Tags  

---

## 🧩 Components

---

### 🔹 Core Components

- `Navbar`  
- `Footer`  
- `Loader`  
- `SearchBar`  

---

### 🔹 Feature Components

- `ResourceCard`  
- `RatingStars`  
- `FilterBar`  
- `RecommendationCard`  

---

### 🔹 UI Components

- Buttons  
- Modals  
- Inputs  
- Dropdowns  

---

## ⭐ Multi-Dimensional Rating UI

### 🎯 Goal
Capture meaningful feedback

### UI Elements
- Slider / stars for:
  - Beginner Friendly  
  - Depth  
  - Practical  
  - Speed  

---

## 🤖 Recommendation UI

### Features
- Highlight “Best for YOU”  
- Show tags:
  - “Good for Visual Learners”  
- Ranking system  

---

## 🧭 Learning Path UI

### Input
- User goal (e.g., “Learn Backend in 2 weeks”)

### Output
- Timeline view  
- Step-by-step cards  
- Progress tracking  

---

## 🔄 Data Flow
1. User inputs preferences → saved in profile
2. User explores resources → API call to fetch filtered resources
User Input → API Call → Backend → Response → UI Update


---

## 🔌 API Integration

---

### Auth
- Register / Login  
- Store token  

---

### Resources
- Fetch all resources  
- Filter resources  

---

### Ratings
- Submit rating  
- Fetch ratings  

---

### Recommendations
- Fetch personalized resources  

---

## 🎨 UX Requirements

- Clean, minimal UI  
- Dark theme preferred 🌙  
- Mobile responsive 📱  
- Fast loading ⚡  
- Easy navigation  

---

## ⚡ Performance Requirements

- Lazy loading components  
- Optimized API calls  
- Caching (optional)  

---

## 🧪 Testing

- Component testing (React Testing Library)  
- API integration testing  

---

## 🚀 Deployment

- Frontend: Vercel / Netlify  

---

## 📊 Success Metrics

- Time spent on platform  
- Resource click rate  
- User engagement  

---

## 🔮 Future Scope

- Voice-based learning assistant 🎤  
- Real-time collaboration  
- AI chat tutor  
- Chrome extension  

---

## 💯 Summary

LearnWise AI frontend is:
- ✅ Clean & modern  
- ✅ User-focused  
- ✅ Scalable  
- ✅ Hackathon-ready  

---

> “Good UI doesn’t just look good — it helps users learn faster.” 🚀