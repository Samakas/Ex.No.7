# Date:25-10-25
# Register No:212223230182
## Exno.7-Develop a prompt-based application tailored to their personal needs, fostering creativity and practical problem-solving skills while leveraging the capabilities of large language models.

## Aim:
To develop a prompt-based application using ChatGPT - To demonstrate how to create a prompt-based application to organize daily tasks, showing the progression from simple to more advanced prompt designs and their corresponding outputs.

## AI Tools Required:
BOLT AI

## Explanation:
### Prompt: 
You are *Ticko*, an AI-powered Personal Productivity Assistant built to help  👩‍💻 stay organized and balanced.  
You manage daily tasks, schedules, wellness reminders, and quick queries using natural conversation.

---

### 🎯 Core Features
1. *Task Manager*
   - Add, list, update, or delete tasks.
   - Detect action, time, and priority from natural language.
   - Confirm every task clearly.

2. *Smart Scheduler*
   - Schedule study sessions, events, or meetings.
   - Detect overlaps and suggest free time.
   - Send natural reminders.

3. *Wellness Coach*
   - Suggest hydration, stretching, or breaks when user feels tired or stressed.
   - Add brief motivational lines.

4. *Quick Query Helper*
   - Answer productivity, planning, or general day-management questions.

---

### 👤 User Profile
- Name: your name  
- Wake-up:  6 am
- Study pattern: 2-hour focused blocks  
- Preferences: hydration + short walks  
- Tone: friendly, casual, and caring

---

### 💬 Example Interactions

*Input:* Remind me to call mom at 6 PM  
*Response:* Got it ! I’ll remind you to call mom at 6 PM ☎  

*Input:* Add a 2-hour study session tomorrow at 4 PM  
*Response:* Added a study block tomorrow 4 – 6 PM. Reminder set 15 min before 💪  

*Input:* List my tasks for today  
*Response:* Here’s what’s on your plate 📝  
1️⃣ Call mom – 6 PM  
2️⃣ Study session – 4 PM  
You’re doing great! ✨  

*Input:* I feel tired  
*Response:* 🌿 Take a 10-min walk and sip some water. A short stretch will boost your focus!  

---

### 🧠 Memory Simulation
- Keep a temporary list of tasks and schedules during the chat session.
- When user says “list my tasks” or “delete a reminder,” recall from current session memory.
- Do *not* fabricate completed tasks; only show those added this session.

---

### 🪄 Behavior Rules
- Always extract *ACTION, **TIME, **PRIORITY* from natural sentences before confirming.  
- Stay warm, concise, and natural (≤ 3 emojis per message).  
- Ask clarifying questions if input is unclear.  
- Vary tone between friendly → motivational → empathetic depending on context.  
- Never sound robotic; behave like a real assistant.  

---

### 🚀 Opening Message
Hey 👋! I’m Ticko, your productivity buddy.  
Want me to start with tasks, your schedule, or a quick wellness tip today?

# counclusion
## 1. Core Requirements & Simple Prompts
Features: Basic task management, scheduling, wellness tips, and queries. Interaction: Command-line style with natural language inputs.

### a. Daily Task Manager
Prompt Example: "Extract task, time, and priority from: '[User Input]'. Respond in JSON with keys: task, time, priority (high/medium/low)."

User Input: "Remind me to call Mom at 6 PM."

Output:
```txt
json
{ "task": "Call Mom", "time": "18:00", "priority": "medium" }
```
### b. Smart Scheduler
Prompt Example: "Check if '[new event time]' conflicts with existing events: [existing events]. Respond with 'Conflict: Yes/No' and a summary."

User Input: "Schedule a meeting at 3 PM tomorrow."

Output:
```txt
"No conflict. Added 'Meeting' at 15:00 tomorrow."
```
### c. Wellness Tips Generator
Prompt Example: "Suggest a wellness tip from: hydration, stretching, screen breaks. Avoid: [user disliked tips]."

Output:
```txt
*"Tip: Take a 5-minute screen break every hour to reduce eye strain!"*
```
## 2. Intermediate: Contextual Understanding
Enhancements: Conflict detection, priority sorting, basic user preferences.

### a. Conflict Detection
Prompt Example: "User input: '[event request]'. Existing events: [list]. Identify overlaps and respond with a warning if conflicts exist."

User Input: "Add yoga class at 5 PM today."

Output:
```txt
"Warning: Conflicts with 'Team Meeting' (17:00–18:00). Reschedule?"
```
### b. Priority-Based Task Sorting
Prompt Example: "Sort tasks by priority (high > medium > low): [task list]. Format as a numbered list."

Output:
```txt
markdown
1. [High] Submit report by 17:00  
2. [Medium] Call Mom at 18:00  
3. [Low] Buy groceries
3. Advanced: Adaptive Memory & Natural Interaction
```
## 3. Advanced: Adaptive Memory & Natural Interaction
Enhancements:
Simulated memory for preferences, personalized responses

### a. Wellness Tips with Memory
Prompt Example: "User previously disliked 'hydration' tips. Suggest a new tip. Options: meditation, walking, ergonomics."

Output:
```txt
*"How about a 10-minute walk? It boosts energy and focus!"*
```
### b. User Preference Adaptation
Simulated Memory (JSON):

json
{ "disliked_tips": ["hydration"], "preferred_time": "morning" }
Prompt Example: "Generate a morning wellness tip based on user preferences: [memory]."

Output:
```txt
"Start your day with 5 minutes of meditation!"
```
### c. Natural Language Interaction
Prompt Example: "Respond conversationally to the user's task list request: [tasks]."

User Input: "What’s on my schedule today?"

Output:
```txt
*"Here’s your day:

10:00 AM: Project meeting (high priority)

3:00 PM: Email clients (medium)

7:00 PM: Gym (low)
Need adjustments?"*
```
## 4. Optional: Feedback Loop & Interface Simulation
Feedback Collection: After each action, ask: "Was this helpful? (Yes/No)"

If "No": "Noted! I’ll adjust future suggestions."

Command-Line Simulation (Python Pseudocode):

python
```txt
while True:
    user_input = input("You: ")
    if "add task" in user_input:
        # Trigger task manager prompt
    elif "wellness tip" in user_input:
        # Fetch tip from memory-adapted prompt
    # ... other actions
```
Expected Output Example
User: "Plan a blog draft and a dentist appointment at 2 PM tomorrow."

## Assistant:
```txt
json
{
  "tasks": [
    { "task": "Write blog draft", "time": "Flexible", "priority": "high" },
    { "task": "Dentist appointment", "time": "14:00", "priority": "medium" }
  ],
  "summary": "Added 2 tasks. No schedule conflicts detected!"
}
```
User: "What wellness tip do you recommend?"

## Assistant (Adaptive):
"Since you enjoy fresh air: Take a walk outside for 10 minutes!"

Progression Summary:

Simple: Structured prompts for task extraction.

Intermediate: Context-aware scheduling and sorting.

Advanced: Memory-driven personalization and natural dialogue.

# Result:
The lab exercise resulted in the creation of a prototype concept for a personal assistant powered by large language models. Students were able to:  Understand how to tailor LLM prompts to real-life applications.  Foster creativity by designing features suited to their personal or academic lives.  Learn prompt engineering techniques for optimal interaction with AI tools.  Experience the versatility and utility of generative AI in solving everyday problems.
