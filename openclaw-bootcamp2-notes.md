# OpenClaw Bootcamp 2 - Full Notes

Source: `Dropbox\Ai Videos To Watch\openclawbootcamp2.mp4`
Watched: 2025-02-11
Presenter: Alex (OpenClaw creator)
Duration: ~2 hours

## Key Concepts

### AI as an Organization (not a chatbot)
- Stop thinking "send prompt, get response"
- Think of it as a team of specialized AI agents/employees
- Each agent has a role, model, and specialization

### Brain & Muscle Architecture
- **Brain:** Expensive powerful model (Opus) for strategy/decisions
- **Muscles:** Cheap/local models for execution (GLM, Gemini Flash)
- Cost optimization: only use expensive models when you need intelligence

### Reverse Prompting
- Ask AI "what can WE do to solve this?" instead of giving instructions
- Gets AI to suggest its own solutions and systems
- Example: AI creates its own calendar/doc systems to avoid forgetting

### Mission Control Dashboard
- Alex's custom-built local app for managing AI agents
- Tabs: Tasks, Chat, Council, Calendar, Projects, Memory, Captures, Docs, People, Org, Office, Search
- Org chart showing hierarchy: CEO → CSO (Opus) → Engineers/Researchers (local models)

### Local Models
- Run on personal hardware (Mac Studio recommended)
- Benefits: Free, 24/7, Privacy, Education, Fun
- Use LM Studio to host
- GLM 4.7 (355B), GLM 4.7 Flash (38B MoE), Gemma 3, Kimmy K

### Security
- Prompt injection risks from external sources
- Set explicit guardrails: no downloading external skills, no accessing sensitive data
- OpenClaw = admin privileges — be cautious with third-party tools

### Heartbeat Optimization
- Reduce frequency (30 min vs 5 min)
- Use cheaper models for heartbeats (Haiku, Gemini Flash)
- Streamline what AI does during each heartbeat

### The "Opinion Muscle"
- Most underrated skill: forming and expressing strong opinions
- Critical for content creation, product development
- Practice by engaging with social media feeds thoughtfully

## Action Items for Brian
1. Think about AI as an organization, not a chatbot
2. Try reverse prompting with Kosmo
3. Experiment with local models via LM Studio
4. Consider building a Mission Control-style dashboard
5. Implement security guardrails
6. Optimize heartbeat frequency and model usage

## Notable Quotes
- "You're looking at it through the lens of ChatGPT... that's not the lens you look at it through."
- "If you figure out out-of-the-box workflows for different personas, you could start a very profitable business today."
- "AI can develop its own systems to avoid that falling through the gaps."
- "The most underrated skill is the ability to form and express opinions."
- "If you build something that's shitty and you never use, it's still a win."
