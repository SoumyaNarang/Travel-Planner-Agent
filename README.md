# Personal Travel Planner Agent

A travel-planning agent built with Google ADK and Gemini. The agent takes a travel request containing a destination, duration, budget, and user preferences, then generates a personalized day-wise itinerary along with a budget estimate and recommended places to visit.

If essential information such as the destination, duration, or budget is missing, the agent asks a follow-up question before creating the itinerary.

---

## Features

- Understands natural language travel requests
- Estimates travel budget
- Recommends attractions based on user preferences
- Generates detailed day-wise itineraries
- Handles incomplete requests by asking follow-up questions
- Built using Google ADK and Gemini

---

## Setup

```bash
python -m venv venv
venv\Scripts\activate           # Mac/Linux: source venv/bin/activate
pip install -r requirements.txt
```

Create a `.env` file in the project folder:

```env
GOOGLE_GENAI_USE_VERTEXAI=FALSE
GOOGLE_API_KEY=your_api_key_here
```

You can get a free Gemini API key from Google AI Studio.

---

## Run

From the folder that contains `travel_planner_agent/`:

```bash
adk web
```

or

```bash
adk run travel_planner_agent
```

In `adk web`, select `travel_planner_agent` and enter your travel request.

---

## How It Works

The agent is implemented in `agent.py` using Google ADK and Gemini.

Workflow:

1. Understand the travel request
2. Extract destination, duration, budget, and interests
3. Check whether required information is available
4. Estimate a travel budget
5. Recommend places to visit
6. Generate a day-wise itinerary
7. Return practical travel tips

> Note: Budget estimates are approximate and not based on live pricing.

---

## Example Conversation

> **User:** I want to visit Jaipur for 3 days with a budget of ₹15,000. I like history and local food.

> **Agent:**

### Understanding Your Request

You are planning a 3-day trip to Jaipur with a budget of ₹15,000, focusing on history and local food.

### Trip Overview & Highlights

Welcome to the Pink City! This 3-day itinerary is designed to immerse you in Jaipur's royal heritage and vibrant culinary scene while staying within your budget.

### Estimated Budget Breakdown

| Category | Estimated Cost |
|-----------|---------------|
| Accommodation | ₹4,000 |
| Food & Dining | ₹3,500 |
| Sightseeing | ₹2,500 |
| Local Transport | ₹3,000 |
| Miscellaneous | ₹2,000 |

### Recommended Places to Visit

- Amber Fort
- Hawa Mahal
- City Palace
- Jantar Mantar
- Nahargarh Fort

### Day 1: The Heart of the Walled City

**Morning**
- Visit Hawa Mahal
- Explore City Palace

**Afternoon**
- Visit Jantar Mantar
- Enjoy traditional Rajasthani food

**Evening**
- Explore Johri Bazaar and Bapu Bazaar

### Day 2: Forts and Royal Views

**Morning**
- Explore Amber Fort

**Afternoon**
- Visit Jal Mahal

**Evening**
- Watch sunset from Nahargarh Fort

### Day 3: Museums and Local Culture

**Morning**
- Visit Albert Hall Museum

**Afternoon**
- Local shopping and sightseeing

**Evening**
- Departure

### Travel Tips

- Start sightseeing early to avoid crowds.
- Use local transport or ride-sharing apps.
- Book accommodation in advance during peak season.

---

## Screenshots

Screenshots demonstrating the application's functionality are included in the repository.

---
