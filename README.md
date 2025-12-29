<h1>
  🤖 AI-Powered Contact Form Automation
</h1>

<h3>
Intelligent contact form system using n8n, OpenAI, and modern web stack
</h3>

<img width="1366" height="594" alt="Screenshot (234)" src="https://github.com/user-attachments/assets/eb77fae0-bea8-4b7e-9cb1-20955d9288ac" />


<img width="1366" height="673" alt="Screenshot (232)" src="https://github.com/user-attachments/assets/026d4e42-cb6b-4774-9f9c-0be710c700b9" />


<div style="margin-bottom: 1rem;">
<img width="1366" height="544" alt="Screenshot (233)" src="https://github.com/user-attachments/assets/33c78f03-8a5d-4196-9248-accbac264617" />
</div>

<img width="1215" height="492" alt="Screenshot (237)" src="https://github.com/user-attachments/assets/c9af90ac-e000-48e6-afd3-ea502ad76216" />

<img width="1366" height="430" alt="Screenshot (238)" src="https://github.com/user-attachments/assets/32775e24-38e1-4a1c-81b2-5a9937e06d6a" />


<h1>
📋 Overview
</h1>

<h3>
An automated workflow that analyzes contact form submissions using AI, categorizes them by priority, sends intelligent email notifications, and stores everything in MongoDB - all for $0.0002 per submission.
</h3>

<h1>
✨ Features
</h1>

<h1>
🤖 AI-Powered Analysis - OpenAI GPT-3.5 categorizes and prioritizes messages
</h1>

<h1>
📧 Smart Email Notifications - Beautiful, actionable email alerts
</h1>

<h1>
💾 Database Storage - All submissions saved to MongoDB
</h1>

<h1>
⚡ Real-time Processing - Sub-2-second response time
</h1>

<h1>
💰 Cost-Effective - $0.0002 per submission (~$0.20 per 1,000 contacts)
</h1>

<h1>
🚀 Production Ready - Deployed on Railway, 24/7 uptime
</h1>

<h1>
🏗️ Architecture
</h1>

Contact Form (Next.js)
        ↓
    Webhook Trigger
        ↓
OpenAI Analysis (GPT-3.5)
    ├─ Priority Detection
    ├─ Category Classification
    └─ Summary Generation
        ↓
Custom JavaScript Processing
        ↓
    ├─ Email Notification (Resend)
    └─ Database Storage (MongoDB)

    
<h1>
🛠️ Tech Stack
</h1>

<h3>
Core
</h3>

n8n - Workflow automation platform
OpenAI API - AI analysis (GPT-3.5-turbo)
Next.js 15 - Frontend framework
MongoDB - Database
Resend - Email delivery
Railway - Hosting platform

<h1>
Languages
</h1>

TypeScript/JavaScript
Node.js

<h3>
📊 Workflow Breakdown
</h3>
1. Webhook Trigger
javascript// Receives POST requests with:
{
  name: string,
  email: string,
  message: string
}
2. AI Analysis
javascript// OpenAI prompt
Analyze this contact form:
- Detect priority (High/Medium/Low)
- Categorize (Project/Job/Question/Spam)
- Provide summary

Response format: JSON
3. Data Processing
javascript// Custom node code
const analysis = JSON.parse(aiResponse);
return {
  ...webhookData,
  priority: analysis.priority,
  category: analysis.category,
  priorityEmoji: getPriorityEmoji(analysis.priority),
  timestamp: new Date()
}
4. Multi-Channel Actions

Email: HTML formatted with AI insights
Database: MongoDB document with full context
Logging: Execution history tracked


<h2>
💰 Cost Analysis
</h2>

ComponentCostRailway Hosting$5-10/monthOpenAI API~$0.0002/submissionMongoDB AtlasFree tier (or $0)Resend EmailFree tier (100/day)Total per 1,000 submissions~$0.20
🚀 Deployment
Prerequisites

Railway account
OpenAI API key
Resend API key
MongoDB connection string

Setup

Deploy n8n on Railway

bash# Use Railway's n8n template
railway init
railway add -d postgres

Environment Variables

envN8N_BASIC_AUTH_USER=admin
N8N_BASIC_AUTH_PASSWORD=your_password
OPENAI_API_KEY=sk-...
RESEND_API_KEY=re_...
MONGODB_URI=mongodb+srv://...

Import Workflow


Access your n8n instance
Import workflow.json from this repo
Activate the workflow


Get Webhook URL

https://your-n8n.railway.app/webhook/contact-form
📖 Usage
Frontend Integration
typescript// app/api/contact/route.ts
export async function POST(req: Request) {
  const { name, email, message } = await req.json();
  
  await fetch('https://your-n8n.railway.app/webhook/contact-form', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({ name, email, message })
  });
  
  return Response.json({ success: true });
}
cURL Test
bashcurl -X POST https://your-n8n.railway.app/webhook/contact-form \
  -H "Content-Type: application/json" \
  -d '{
    "name": "John Doe",
    "email": "john@example.com",
    "message": "I need a developer for a $50k project"
  }'
📈 Performance Metrics

Average Response Time: 1.6 seconds
AI Analysis Time: 0.8 seconds
Email Delivery: 0.5 seconds
Database Write: 0.3 seconds
Uptime: 99.9%

🔒 Security

✅ Environment variables for all secrets
✅ Basic auth for n8n instance
✅ HTTPS only
✅ Rate limiting on webhook
✅ Input validation
✅ No API keys in code

<h1>
📚 Lessons Learned
</h1>

AI integration is accessible - You don't need ML expertise
Automation saves time - 14+ hours/week recovered
Cost-effectiveness - AI doesn't have to be expensive
Speed matters - From zero to production in 48 hours
Documentation is key - Good docs = faster debugging

🎯 Future Enhancements

 Add sentiment analysis
 Multi-language support
 Slack notifications
 Auto-reply to sender
 Analytics dashboard
 A/B testing for email templates

🤝 Contributing
Contributions welcome! Please feel free to submit a Pull Request.
📝 License
MIT License - see LICENSE file for details
👤 Author
<h4>
Abdulsalam Abdulhamid (Lanre)
</h4>

Portfolio: <a href="https://codedbylanre.dev" target="_blank">codedbylanre.dev</a>
LinkedIn: <a href="[[https://codedbylanre.dev](https://www.linkedin.com/in/abdulhamid-abdulsalam-ba3634331](https://www.linkedin.com/in/abdulhamid-abdulsalam-ba3634331)" target="_blank">@abdulhamid-abdulsalam</a>
Twitter: <a href="https://x.com/Abdul_Lanre001" target="_blank">@Abdul_Lanre001</a>
GitHub:  <a href="[https://codedbylanre.dev](https://github.com/Abdulsalam001Arnold)" target="_blank">@Abdulsalam001Arnold</a>


<h3>
🙏 Acknowledgments
</h3>

n8n community for amazing documentation
OpenAI for accessible AI APIs
Railway for seamless deployment

⭐ If this project helped you, please star it!
📧 Need help with automation? Get in touch
🚀 Building something similar? I'd love to see it - tag me!

Built during the 2024 holiday season - because real developers don't take breaks, they level up. 💪
