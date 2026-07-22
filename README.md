# AI Tuition Support Agent

An AI-powered automation that instantly responds to student inquiries via webhook, understanding their request and generating a professional, personalized reply — built for tuition centers to reduce response time and manual workload.

## Business Problem
Tuition centers receive repetitive inquiries daily (subject, class level, timing) that require manual, time-consuming replies — delaying response time and costing staff hours.

## Solution
This automation instantly captures student inquiry data via webhook, uses Google Gemini AI to understand the request, and sends back a personalized, professional reply — all within seconds, without human involvement. If the AI fails for any reason, a fallback message ensures the student is never left without a response.

## Architecture
Webhook Trigger → Google Gemini AI → Success/Error Check (IF Node) → Respond to Webhook
## Tech Stack
- n8n (workflow automation)
- Google Gemini AI (gemini-2.5-flash)
- Webhook / REST API
- Postman (for testing)

## How It Works
1. Student inquiry data is sent to the webhook (name, subject, class level, preferred time)
2. Webhook receives and passes data to Gemini AI
3. AI generates a professional, contextual reply in Roman Urdu
4. If AI fails, an IF node detects the error and triggers a fallback message — ensuring the student always gets a response
5. Reply is sent back instantly via Respond to Webhook

## Error Handling
This workflow includes built-in error handling. If the AI model fails (e.g., server issue, invalid request), the system automatically sends a professional fallback message instead of crashing — a critical requirement for production-ready client systems.

## Future Improvements
- WhatsApp Business API integration for real-time messaging
- Google Sheets logging for inquiry tracking and analytics
- Automated fee calculation based on subject/class level
- Multi-language support
