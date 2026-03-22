# ⚙️ Backend PRD – LearnWise AI

> Scalable backend system for personalized learning resource recommendations

---

## 🧠 Overview

### 🎯 Objective
Build a backend system that:
- Stores users, resources, and ratings  
- Generates personalized recommendations  
- Supports filtering, searching, and ranking  
- Optional: Generates learning paths based on user goals

---

### 👥 Target Users
- Beginner developers  
- Students  
- Self-learners  
- Professionals looking to upskill

---

### 🧩 Core Capabilities
- Authentication & user profiling  
- Resource management  
- Multi-dimensional rating system  
- Recommendation engine  
- Optional: Learning path generation

---

## 🏗️ System Architecture

### ⚙️ Tech Stack
- **Runtime:** Node.js  
- **Framework:** Express.js  
- **Database:** MongoDB (Mongoose)  
- **Authentication:** JWT + bcrypt  
- **Optional AI:** OpenAI API / Custom logic  

---

### 🧱 High-Level Flow
    Client (React)
        ↓
    API Layer (Express)
        ↓
    Controllers
        ↓
    Services (Business Logic)
        ↓
    Database (MongoDB)

---

## 🧑‍💻 Modules & Responsibilities

---

### 🔐 Auth Module

#### Responsibilities
- Register users  
- Login users  
- Return authenticated user  

#### Endpoints
- POST /api/auth/register
- POST /api/auth/login
- GET /api/auth/me


#### Features
- Password hashing (bcrypt)  
- JWT token generation  
- Protected routes  

---

### 👤 User Module

#### Responsibilities
- Store user profile  
- Update learning preferences  

#### Schema
```js
{
  name,
  email,
  password,
  level: "beginner | intermediate | advanced",
  learningType: "visual | practical | theory",
  speed: "fast | slow",
  createdAt
}

```
#### 📚 Resource Module
 Responsibilities
  -Add resources
  -Fetch resources
  -Filter resources
#### Endpoints
  - POST /api/resources
  - GET /api/resources
  - GET /api/resources/:id
#### Schema
```js
{
  title,
  description,
  url,
  topic: "React | Node.js | DSA",
  type: "video | article | course",
  ratings: {
    beginnerFriendliness: Number,
    depth: Number,
    practicality: Number,
    speedSuitability: Number
  },
  createdAt
}
```
---### 🌟 Rating Module
#### Responsibilities
- Allow users to rate resources
  -Store multi-dimensional ratings
  -Aggregate ratings
#### Endpoints
- POST /api/ratings
- GET /api/ratings/resource/:resourceId
#### Schema 
```js
{
  userId,
  resourceId,
  beginnerFriendliness: Number,
  depth: Number,
  practicality: Number,
  speedSuitability: Number,
  createdAt
}
```
---### 🤖 Recommendation Module
#### Responsibilities
- Generate personalized recommendations
- Use user profile and ratings
- Match user profile with resources
- Rank resources
#### Endpoints
- GET /api/recommendations/:userId

### 🧠 Recommendation Logic
- 🎯 Goal
- Return best-fit resources, not just top-rated ones
- Match user profile with resource attributes
- Consider multi-dimensional ratings
- Rank resources based on relevance to user profile
- Optional: Use AI for advanced recommendations

### 🧮 Algorithm (MVP)

- Step 1: Filter
    Match:
        1. user.learningType ∈ resource.tags
        2. user.level ∈ resource.tags

- Step 2: Score
    score =
  (rating.beginner * weight1) +
  (rating.practical * weight2) +
  (rating.speed * weight3)

- Step 3: Rank
    Sort resources by score in descending order
    Highest score first

- SStep 4: Return Top Results
    Return top N resources (e.g., top 10)

## 🧠 Future Enhancements
- Machine learning recommendations
- Collaborative filtering
- User feedback loop for improving recommendations
- Learning path generation based on user goals

## 🗂️ Database Design
### 📌 Collections
- Users
 ```js
{
  _id,
  name,
  email,
  password,
  preferences: {
    level,
    learningType,
    speed
  }
}
```
- Resources
```js
{
  _id,
  title,
  description,
  url,
  topic,
  type,
  ratings: {
    beginnerFriendliness,
    depth,
    practicality,
    speedSuitability
  }
}
```
- Ratings
```js
{
  _id,
  userId,
  resourceId,
  beginnerFriendliness,
  depth,
  practicality,
  speedSuitability
}
```
### 🔌 API Design
- 🔐 Auth APIs
   - POST /api/auth/register
{
  "name": "Tanish",
  "email": "test@mail.com",
  "password": "123456"
}
   - POST /api/auth/login
{
  "email": "test@mail.com",
  "password": "123456"
}
- 📚 Resource APIs
    - POST /api/resources
    {
      "title": "Learn React in 2024",
      "description": "Comprehensive guide to learn React",
      "url": "https://example.com/react-course",
      "topic": "React",
      "type": "course"
    }
    - GET /api/resources
    - GET /api/resources/:id

    Get Resources
    GET /api/resources?topic=react&type=video

- Add Resource
POST /api/resources
{
  "title": "Learn React in 2024",
  "description": "Comprehensive guide to learn React",
  "url": "https://example.com/react-course",
  "topic": "React",
  "type": "course"
}

- 🌟 Rating APIs
    - POST /api/ratings
    {
      "userId": "123",
      "resourceId": "456",
      "beginnerFriendliness": 4,
      "depth": 5,
      "practicality": 4,
      "speedSuitability": 3
    }
    - GET /api/ratings/resource/:resourceId

- 🤖 Recommendation API
    - GET /api/recommendations/:userId

### 🧠 Recommendation Logic
- 🎯 Goal
    Return best-fit resources, not just top-rated ones
- Match user profile with resource attributes
- Consider multi-dimensional ratings
- Rank resources based on relevance to user profile
- Optional: Use AI for advanced recommendations

### 🔐 Security
- Password hashing (bcrypt)
- JWT authentication
- Input validation (Joi / express-validator)
- Rate limiting (optional)

### ⚡ Performance
- Response time < 500ms
- Indexed queries (topic, tags)
- Pagination support

### 🧪 Testing
- Unit testing for:
- Auth module
- Recommendation logic
- API testing:
- Postman / Jest + Supertest

## 🚀 Deployment
- Backend: Render / Railway
- Database: MongoDB Atlas

## 📊 Success Metrics
- User engagement
- Resource click rate
- Recommendation accuracy

## 🔮 Future Scope
- AI mentor chatbot
- Resume-based recommendations
- Chrome extension integration
- Advanced analytics

## 💯 Summary

LearnWise AI backend is:

✅ Modular
✅ Scalable
✅ AI-ready
✅ Hackathon optimized

