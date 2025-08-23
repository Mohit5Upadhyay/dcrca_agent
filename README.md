
# 🚨 DCRCA Agent (Disaster Chaos Response Coordination AI Agent)

<div align="center">

![Emergency Response](https://img.shields.io/badge/Emergency-Response-red?style=for-the-badge&logo=ambulance)
![AI Powered](https://img.shields.io/badge/AI-Powered-blue?style=for-the-badge&logo=google-gemini)
![Hackathon](https://img.shields.io/badge/AgentHack-WeMakeDevs-green?style=for-the-badge&logo=github)

**An intelligent AI agent that monitors, prioritizes, and coordinates emergency responses in real-time**

Built for **AgentHack Hackathon by WeMakeDevs** using **Portia AI Framework**

[🚀 Demo](#demo) • [📖 Features](#features) • [🏗️ Architecture](#architecture) • [🛠️ Installation](#installation) • [📊 Workflow](#workflow)

</div>

---

## 🎯 Project Overview

DCRCA (Disaster Chaos Response Coordination AI Agent) is an intelligent emergency response coordination system that leverages AI to monitor, analyze, prioritize, and dispatch emergency responses across New York City. The system combines real-time data gathering, human validation, and automated notification systems to ensure rapid response to critical incidents.

### 🏆 Built for AgentHack by WeMakeDevs

This project was developed as part of the AgentHack hackathon, showcasing the power of AI agents in emergency response coordination using the Portia AI framework.

## ✨ Key Features

### 🔍 **Intelligent Emergency Detection**
- Real-time monitoring of emergency incidents across NYC
- AI-powered categorization of emergencies (Fire, Flood, Medical, Accident)
- Automatic GPS coordinate extraction and validation

### 📊 **Smart Prioritization System**
- AI-driven priority scoring (1-5 scale) based on:
  - Severity of incident
  - Number of people affected
  - Location criticality
  - Resource availability

### 👤 **Human-in-the-Loop Validation**
- Interactive approval process for emergency dispatch
- Human oversight ensures accuracy and prevents false alarms
- Rejection tracking with detailed reasoning

### 📧 **Multi-Channel Alert System**
- **Gmail Integration**: Detailed emergency dispatch emails
- **Slack Integration**: Real-time team notifications
- Rich formatting with GPS coordinates and Google Maps links

### 🗺️ **Location Intelligence**
- Precise GPS coordinate tracking
- Automatic Google Maps integration
- Location-based resource allocation

---

## 🏗️ System Architecture

```mermaid
graph TB
    A[🔍 Emergency Data Gathering] --> B[🤖 AI Processing & Analysis]
    B --> C[📍 Location Validation]
    C --> D[📊 Priority Assignment]
    D --> E[👤 Human Validation]
    E --> F{Approval Decision}
    F -->|✅ Approved| G[📧 Email Dispatch]
    F -->|❌ Rejected| H[📝 Log Rejection]
    G --> I[💬 Slack Notification]
    H --> J[📋 Report Generation]
    I --> J
    J --> K[🚨 Emergency Response Teams]
    
    style A fill:#ff9999
    style B fill:#99ccff
    style E fill:#ffcc99
    style G fill:#99ff99
    style I fill:#cc99ff
    style K fill:#ff6666
```

## 🔄 Emergency Response Workflow

```mermaid
sequenceDiagram
    participant S as 🔍 Search System
    participant AI as 🤖 DCRCA AI Agent
    participant H as 👤 Human Operator
    participant E as 📧 Email System
    participant SL as 💬 Slack
    participant R as 🚑 Response Teams

    S->>AI: Raw Emergency Data
    AI->>AI: Parse & Structure Data
    AI->>AI: Generate GPS Coordinates
    AI->>AI: Calculate Priority Scores
    AI->>H: Present for Validation
    H->>AI: Approval/Rejection Decision
    
    alt Emergency Approved
        AI->>E: Send Detailed Dispatch Email
        AI->>SL: Send Slack Alert
        E->>R: Email Notification
        SL->>R: Instant Alert
        R->>R: Deploy Response Teams
    else Emergency Rejected
        AI->>AI: Log Rejection Reason
        AI->>AI: Update System Learning
    end
```

## 📊 Data Flow Architecture

```mermaid
flowchart LR
    subgraph "🔍 Data Input"
        A1[Web Search APIs]
        A2[Emergency Feeds]
        A3[Social Media]
    end
    
    subgraph "🤖 AI Processing"
        B1[Data Parsing]
        B2[Location Extraction]
        B3[Priority Scoring]
        B4[Classification]
    end
    
    subgraph "👤 Human Validation"
        C1[Review Interface]
        C2[Approval Decision]
        C3[Rejection Logging]
    end
    
    subgraph "📡 Dispatch System"
        D1[Gmail API]
        D2[Slack API]
        D3[Response Coordination]
    end
    
    A1 --> B1
    A2 --> B1
    A3 --> B1
    
    B1 --> B2
    B2 --> B3
    B3 --> B4
    
    B4 --> C1
    C1 --> C2
    C2 --> D1
    C2 --> D2
    C2 --> D3
```

## 🛠️ Technology Stack

### 🧠 **AI & Framework**
- **Portia AI**: Advanced AI agent framework for complex workflows
- **Google AI**: LLM provider for intelligent processing
- **Pydantic**: Data validation and serialization

### 🔗 **Integrations**
- **Gmail API**: Email dispatch system
- **Slack Web API**: Team communication
- **Google Maps**: Location services
- **Web Search APIs**: Real-time data gathering

### 🐍 **Core Technologies**
- **Python 3.8+**: Primary programming language
- **Requests**: HTTP client for API integration
- **Python-dotenv**: Environment configuration
- **Enum**: Type-safe emergency categorization

---

## 📥 Installation & Setup

### 1️⃣ **Clone the Repository**
```bash
git clone https://github.com/yourusername/dcrca-agent.git
cd dcrca-agent
```

### 2️⃣ **Install Dependencies**
```bash
pip install -r requirements.txt
```

### 3️⃣ **Environment Configuration**
Create a `.env` file with the following variables:

```env
# API Keys
GOOGLE_API_KEY=your_google_api_key
PORTIA_API_KEY=your_portia_api_key
SLACK_BOT_TOKEN=xoxb-your-slack-bot-token

# Email Configuration
DISPATCH_EMAIL=your-emergency-email@example.com
```

### 4️⃣ **Slack Bot Setup**
1. Create a Slack App at https://api.slack.com/apps
2. Add Bot Token Scopes: `chat:write`, `channels:read`
3. Install app to your workspace
4. Create `#all-emergency-response-bot` channel
5. Invite the bot to the channel

### 5️⃣ **Gmail API Setup**
1. Enable Gmail API in Google Cloud Console
2. Create credentials (Service Account or OAuth2)
3. Download credentials file
4. Set up authentication

---

## 🚀 Usage

### **Run the Emergency Response System**
```bash
python main.py
```

### **Interactive Process Flow**
1. **🔍 Data Gathering**: System searches for NYC emergency incidents
2. **🤖 AI Processing**: Creates structured emergency data with GPS coordinates
3. **📊 Priority Scoring**: Assigns priority levels (1-5) based on severity
4. **👤 Human Validation**: Interactive approval for each emergency
5. **📧 Dispatch**: Sends detailed emails and Slack notifications
6. **📋 Reporting**: Generates comprehensive response summaries

---

## 📋 Emergency Data Structure

```python
class Emergency(BaseModel):
    id: str                 # Unique identifier
    description: str        # Detailed incident description
    type: EmergencyType     # FIRE, FLOOD, MEDICAL, ACCIDENT
    location: str          # Human-readable address
    gps_lat: float         # GPS latitude
    gps_lon: float         # GPS longitude
    priority: float        # Priority score (1.0-5.0)
    people_affected: int   # Number of people involved
```

## 🎯 Emergency Types & Priority Matrix

```mermaid
graph LR
    subgraph "🔥 Fire Emergencies"
        F1[Building Fire - Priority 5]
        F2[Vehicle Fire - Priority 3]
        F3[Grass Fire - Priority 2]
    end
    
    subgraph "🌊 Flood Emergencies"
        FL1[Flash Flood - Priority 4]
        FL2[Street Flooding - Priority 3]
        FL3[Basement Flood - Priority 2]
    end
    
    subgraph "🚑 Medical Emergencies"
        M1[Cardiac Arrest - Priority 5]
        M2[Accident Injury - Priority 4]
        M3[Minor Injury - Priority 2]
    end
    
    subgraph "🚗 Accident Emergencies"
        A1[Multi-car Crash - Priority 4]
        A2[Single Vehicle - Priority 3]
        A3[Fender Bender - Priority 1]
    end
    
    style F1 fill:#ff4444
    style FL1 fill:#ff4444
    style M1 fill:#ff4444
    style A1 fill:#ff4444
```

## 📧 Sample Dispatch Output

### **Email Alert Format**
```
🚨 URGENT EMERGENCY DISPATCH ALERT 🚨
==========================================

📋 HUMAN-VALIDATED EMERGENCIES FOR IMMEDIATE RESPONSE
- Total Approved Emergencies: 2
- Human Validation: COMPLETED ✅
- GPS Coordinates: VERIFIED ✅
- Dispatch Status: ACTIVE 🚨

📍 DETAILED EMERGENCY INCIDENTS:
==========================================

INCIDENT #1 - NYC-FIRE-001
🔴 PRIORITY: 4.5/5.0 (CRITICAL)
🔥 TYPE: FIRE EMERGENCY
📍 LOCATION: 123 Broadway, Manhattan
🗺️ GPS COORDINATES: 40.7589, -73.9851
👥 PEOPLE AFFECTED: 15 individuals
📝 SITUATION: Apartment building fire on 5th floor

🎯 Google Maps Link: https://maps.google.com/?q=40.7589,-73.9851
⚡ RESPONSE REQUIRED: Immediate dispatch to GPS location
```

### **Slack Alert Format**
```
🚨 *URGENT EMERGENCY DISPATCH ALERT* 🚨

📋 *2 CRITICAL EMERGENCIES* - Human Validated ✅

*EMERGENCY INCIDENTS:*

*INCIDENT #1* - `NYC-FIRE-001`
🔴 *Priority 4.5/5.0* (CRITICAL)
🔥 *FIRE EMERGENCY*
📍 *Location:* 123 Broadway, Manhattan
🗺️ *GPS:* `40.7589, -73.9851`
👥 *People Affected:* 15

@channel - Immediate response coordination required!
```

---

## 🎯 Future Enhancements

### 🔮 **Planned Features**
- **Real-time IoT Integration**: Sensor data from fire alarms, flood sensors
- **Machine Learning**: Predictive emergency modeling
- **Mobile App**: Field responder mobile application
- **Voice Integration**: Voice-activated emergency reporting
- **Drone Integration**: Aerial reconnaissance and assessment

### 🌐 **Scalability Roadmap**
- Multi-city support beyond NYC
- Integration with 911 systems
- Real-time traffic optimization for response routes
- Resource allocation optimization
- Historical data analysis and reporting

---

## 🤝 Contributing

We welcome contributions to improve DCRCA Agent! Here's how you can help:

1. **🍴 Fork the repository**
2. **🌿 Create a feature branch** (`git checkout -b feature/amazing-feature`)
3. **💻 Make your changes** and add tests
4. **📝 Commit your changes** (`git commit -m 'Add amazing feature'`)
5. **🚀 Push to the branch** (`git push origin feature/amazing-feature`)
6. **🎯 Open a Pull Request**

### 🐛 **Bug Reports**
Found a bug? Please open an issue with:
- Detailed description
- Steps to reproduce
- Expected vs actual behavior
- Environment details

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

### 🏆 **AgentHack Hackathon**
- **WeMakeDevs** for organizing an amazing hackathon
- **Portia AI** for providing the powerful agent framework
- **Google AI** for LLM capabilities
- **Emergency Response Community** for inspiration

### 🎯 **Special Thanks**
- NYC Emergency Services for real-world insights
- Open source community for tools and libraries
- Fellow hackers for collaboration and feedback

---

## 📞 Contact & Support

<div align="center">

**Built with ❤️ for AgentHack by WeMakeDevs**

### 👥 Team Members

**Anuj Kumar Upadhyay**

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/anuj123upadhyay)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:anuju760@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/anuj1upadhyay)
[![Hashnode](https://img.shields.io/badge/HashNode-007?style=for-the-badge&logo=hashnode&logoColor=pink)](https://anuj1.hashnode.dev)
[![Twitter](https://img.shields.io/badge/twitter-100000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/anuj123upadhyay)

**Mohit Upadhyay**

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/mohit5upadhyay)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:mu.pqr.123@gmail.com.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/mohit5upadhyay)[![Hashnode](https://img.shields.io/badge/HashNode-007?style=for-the-badge&logo=hashnode&logoColor=pink)](https://mohit5upadhyay.hashnode.dev)
[![Twitter](https://img.shields.io/badge/twitter-100000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/mohit5upadhyay)

**🚨 Making Emergency Response Smarter, Faster, and More Coordinated 🚨**

</div>

---

<div align="center">
<sub>⭐ Star this repo if you found it helpful! ⭐</sub>
</div>