# AI Project Analyst Agent

## Project Overview
The AI Project Analyst Agent is a web application that allows users to input a project idea and receive a complete, structured analysis from an LLM. The system evaluates the project’s difficulty, suggests a development pipeline, recommends a tech stack, estimates timeline and resources, outlines team roles and responsibilities, identifies risks, and provides a structured feasibility report.

This tool helps startups, developers, and project managers quickly assess the scope and requirements of any project.

Live URL: https://projectanalysisapplicationfrontend.vercel.app

---

## Features

- **Project Difficulty Analysis:** Categorizes project complexity (Easy, Medium, Hard, Enterprise).  
- **Project Pipeline / Roadmap:** Step-by-step phases with deliverables for each phase.  
- **Tech Stack Recommendation:** Suggestions for frontend, backend, AI/ML, database, and cloud/devops technologies.  
- **Timeline Estimation:** Total project duration and breakdown by phase.  
- **Team Structure & Roles:** Number of people required, domain expertise, time commitment, and responsibilities.  
- **Risk Assessment:** Identifies potential challenges in execution.  
- **Structured Report:** Summary including feasibility, complexity score, and probability of success.

---

## Backend

- **Framework:** FastAPI  
- **LLM API:** Groq API using `llama-3.1-8b-instant`  
- **Endpoint:**
  
- **Request Body:**  
```json
{
  "project_description": "Your project idea here"
}
```
- **Response:** 
  - Returns structured JSON analysis (difficulty, pipeline, tech stack, timeline, team structure, risks, cost, structured report).
  - Deployment: Hosted on Render
  - CORS: Configured for frontend integration

## Frontend

- UI: Accepts project idea input, sends POST request to backend, and displays the structured analysis.
- Results Display:
- Difficulty Level
- Project Pipeline with phases, durations, deliverables
- Tech Stack categories
- Timeline and sub-phase durations
- Team Structure with roles, counts, time commitment, responsibilities
- Risks & Challenges
- Cost Estimate
- Structured Report
- Deployment: Hosted on Vercel

## JSON Response Structure
```json
{
  "difficulty_level": "",
  "project_pipeline": [
    {
      "phase": "",
      "duration": "",
      "deliverables": [""]
    }
  ],
  "tech_stack": {
    "frontend": [""],
    "backend": [""],
    "ai_ml": [""],
    "database": [""],
    "cloud_devops": [""]
  },
  "timeline": {
    "total_duration": "",
    "phases": [
      {
        "phase": "",
        "duration": ""
      }
    ]
  },
  "team_structure": [
    {
      "role": "",
      "count": 0,
      "time_commitment": "",
      "responsibilities": [""]
    }
  ],
  "risks_challenges": [""],
  "cost_estimate": "",
  "structured_report": {
    "project_feasibility": "",
    "complexity_score": 0,
    "success_probability": ""
  }
}
```
