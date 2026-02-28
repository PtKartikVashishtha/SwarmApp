# TravelTrust AI - Risk Management System

<div align="center">

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![Python](https://img.shields.io/badge/python-3.11+-green.svg)
![License](https://img.shields.io/badge/license-MIT-orange.svg)
![Status](https://img.shields.io/badge/status-production--ready-success.svg)

**An Intelligent AI-Powered Risk Assessment System for B2B Travel Agencies**

[Features](#-features) • [Quick Start](#-quick-start) • [Documentation](#-documentation) • [API](#-api) • [Contributing](#-contributing)

</div>

---

## 🎯 Overview

TravelTrust AI is an advanced agentic AI decision-making system that predicts the collapse risk of B2B travel agencies using swarm intelligence and machine learning. Unlike traditional rule-based systems that detect fraud after damage occurs, TravelTrust AI continuously evaluates trust, predicts collapse BEFORE fraud happens, and takes preventive action.

### 💡 Core Philosophy

> **"Trust is static once, but risk is dynamic."**

Traditional risk assessment systems are reactive - they detect fraud after financial damage has already occurred. TravelTrust AI is proactive - it continuously monitors behavioral patterns, predicts future risks, and enables preventive action before losses occur.

### 🌟 Key Differentiators

- **Predictive, Not Reactive**: Anticipates risks before they materialize
- **Multi-Agent Intelligence**: 7 specialized AI agents analyze different risk dimensions
- **Swarm Consensus**: Weighted voting combines multiple perspectives
- **Counterfactual Simulation**: Tests "what-if" scenarios before taking action
- **Continuous Learning**: System improves over time through feedback loops
- **Real-Time Monitoring**: Live updates every 5 seconds via WebSocket

---

## 🚀 Features

### 🤖 AI Agent System (7 Specialized Agents)

| Agent | Function | Signals Analyzed |
|-------|----------|------------------|
| **Drift Agent** | Detects behavioral pattern changes | Booking volume, login patterns, activity spikes |
| **Credit Agent** | Evaluates financial stress | Payment delays, credit utilization, chargebacks |
| **Identity Agent** | Assesses account stability | Device consistency, IP geolocation variance |
| **Memory Agent** | Compares with historical patterns | Past failures, recovery patterns, trends |
| **Peer Agent** | Benchmarks against similar agencies | Peer failure rates, industry benchmarks |
| **Prediction Agent** | Forecasts future trajectory | Time-series analysis, trend extrapolation |
| **Incentive Agent** | Evaluates response to pressure | Credit term responsiveness, booking behavior |

### 🧠 Swarm Negotiation Engine

- **Weighted Consensus**: Combines agent opinions using dynamic weights
- **Disagreement Detection**: Highlights conflicting views and minority warnings
- **Risk Vector**: Outputs comprehensive risk score (0-100)
- **Confidence Scoring**: Provides confidence levels for each assessment

### 🔮 Counterfactual Simulation Engine

Predicts outcomes under 3 potential actions:

1. **Do Nothing** - Maintain current terms
2. **Soft Contract** - Reduce credit limit
3. **Credit Freeze** - Suspend credit entirely

Implements **Minimum Regret Decision Policy** to choose optimal action based on expected outcomes.

### 📊 Data Signals (UEBA - User and Entity Behavior Analytics)

The system monitors 10 real-time behavioral signals:

| Signal | Description | Risk Indicator |
|--------|-------------|----------------|
| `booking_volume_per_day` | Daily booking count | Sudden spikes or drops |
| `payment_delay_days` | Days beyond payment terms | Financial stress |
| `credit_utilization` | Credit limit usage % | Over-leverage risk |
| `chargeback_ratio` | Chargeback rate | Customer disputes |
| `login_time_variance` | Login pattern deviation | Account compromise |
| `device_change_frequency` | Device switching rate | Identity theft risk |
| `ip_geo_variance` | Geographic IP variation | Account sharing/fraud |
| `booking_spike_ratio` | Sudden booking changes | Unusual activity |
| `peer_failure_rate` | Similar agency failure rate | Industry risk |
| `response_to_credit_terms` | Responsiveness to changes | Financial flexibility |

### 🔄 Continuous Learning Loop

- **Outcome Tracking**: Records actual outcomes (stable/collapsed/recovered)
- **Agent Evaluation**: Measures each agent's prediction accuracy
- **Weight Adjustment**: Accurate agents gain weight, inaccurate agents lose weight
- **Consensus Optimization**: Swarm becomes more accurate over time

---

## 🛠️ Tech Stack

### Backend

- **Python 3.11+** - Core language
- **FastAPI** - High-performance web framework
- **PostgreSQL 15** - Data persistence
- **SQLAlchemy 2.0** - ORM
- **WebSocket** - Real-time updates
- **NumPy/Pandas** - Data processing
- **Scikit-learn** - Statistical analysis
- **Pydantic** - Data validation

### Frontend

- **Next.js 14** - React framework
- **TypeScript** - Type safety
- **Tailwind CSS** - Styling
- **Radix UI** - Accessible components
- **Recharts** - Data visualization
- **Lucide React** - Icons
- **Glass Morphism** - Modern UI design

### Infrastructure

- **Docker & Docker Compose** - Containerization
- **PostgreSQL** - Database
- **Nginx** - Reverse proxy (production)
- **Redis** - Caching (optional)

### External Integrations

- **TBO Air API** - Flight booking data
- **TBO India API** - Travel services
- **OpenAI API** - Enhanced AI reasoning
- **SendGrid** - Email notifications
- **Twilio** - SMS alerts
- **Stripe** - Payment processing

---

## 📁 Project Structure

```
traveltrust-ai/
├── backend/
│   ├── agents/              # AI agent implementations
│   │   ├── base_agent.py
│   │   ├── drift_agent.py
│   │   ├── credit_agent.py
│   │   ├── identity_agent.py
│   │   ├── memory_agent.py
│   │   ├── peer_agent.py
│   │   ├── prediction_agent.py
│   │   └── incentive_agent.py
│   ├── swarm/               # Swarm negotiation engine
│   │   └── negotiation_engine.py
│   ├── simulation/          # Counterfactual simulation
│   │   └── counterfactual_engine.py
│   ├── learning/            # Feedback learning loop
│   │   └── feedback_loop.py
│   ├── data_stream/         # Data simulation
│   │   └── simulator.py
│   ├── models/              # Database models & schemas
│   │   ├── database.py
│   │   └── schemas.py
│   ├── config.py            # Configuration management
│   ├── middleware.py        # Security middleware
│   ├── main.py              # FastAPI application
│   ├── requirements.txt
│   ├── Dockerfile
│   └── .env.example         # Environment variables template
├── frontend/
│   ├── app/                 # Next.js pages
│   │   ├── page.tsx         # Dashboard
│   │   ├── agency/[id]/     # Agency detail
│   │   ├── swarm-lab/       # Swarm analysis
│   │   ├── simulation-lab/  # Simulation tools
│   │   └── feedback-logs/   # Learning statistics
│   ├── components/          # React components
│   │   ├── Navbar.tsx
│   │   ├── RiskBadge.tsx
│   │   └── AgentVoteBar.tsx
│   ├── lib/                 # Utilities & API
│   │   ├── utils.ts
│   │   └── api.ts
│   ├── package.json
│   ├── tailwind.config.ts
│   └── Dockerfile
├── database/
│   └── schema.sql           # Database schema
├── docker/
│   └── docker-compose.yml   # Container orchestration
├── README.md                # This file
├── API_INTEGRATION_GUIDE.md # API integration documentation
├── SECURITY.md              # Security policies
├── API_DOCUMENTATION.md     # Complete API reference
├── QUICKSTART.md            # Quick start guide
├── DOCKER_SETUP.md          # Docker troubleshooting
├── CHANGELOG.md             # Version history
├── .gitignore
├── START.sh                 # Linux/Mac startup script
└── START.bat                # Windows startup script
```

---

## 🚀 Quick Start

### ⚡ One-Command Startup (Recommended)

**Linux/Mac:**
```bash
./START.sh
```

**Windows:**
```bash
START.bat
```

That's it! The system will automatically:
1. Build Docker containers
2. Start PostgreSQL database
3. Initialize database schema
4. Start FastAPI backend
5. Start Next.js frontend
6. Create sample agencies

### 📋 Prerequisites

- **Docker** 20.10+ and **Docker Compose** 2.0+
- **Git** (for cloning)
- **4GB+ RAM** available
- **10GB+ disk space**

### 🔧 Manual Setup

#### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/traveltrust-ai.git
cd traveltrust-ai
```

#### 2. Configure Environment Variables

```bash
cd backend
cp .env.example .env
# Edit .env with your configuration
```

#### 3. Start with Docker Compose

```bash
cd docker
docker-compose up --build
```

#### 4. Access the Application

- **Frontend**: http://localhost:3000
- **Backend API**: http://localhost:8000
- **API Documentation**: http://localhost:8000/docs
- **Database**: localhost:5432

---

## 📚 Documentation

### Core Documentation

- **[API Integration Guide](API_INTEGRATION_GUIDE.md)** - Complete guide for integrating external APIs
- **[Security Policy](SECURITY.md)** - Security best practices and policies
- **[API Documentation](API_DOCUMENTATION.md)** - Complete API reference
- **[Quick Start Guide](QUICKSTART.md)** - Detailed setup instructions
- **[Docker Setup](DOCKER_SETUP.md)** - Docker troubleshooting guide

### Key Topics

- **[Configuration](#configuration)** - Environment variables and settings
- **[API Endpoints](#api-endpoints)** - Available API endpoints
- **[Frontend Pages](#frontend-pages)** - Web interface overview
- **[Risk States](#risk-states)** - Risk classification system
- **[How It Works](#how-it-works)** - System architecture and workflow

---

## 🔌 API Endpoints

### Agencies

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/agencies` | List all agencies |
| GET | `/agency/{id}` | Get agency details |
| GET | `/agency/{id}/history` | Get risk history |

### Agent Analysis

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/agents/votes/{agency_id}` | Get agent votes and consensus |

### Simulation

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/simulate` | Run counterfactual simulation |

### Actions

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/apply-action` | Apply action to agency |

### Learning

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/learning/statistics` | Get learning statistics |

### WebSocket

| Method | Endpoint | Description |
|--------|----------|-------------|
| WS | `/ws/live-updates` | Live risk updates (5-second intervals) |

### Health

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/health` | System health check |

---

## 🎨 Frontend Pages

### Dashboard (`/`)

- Overview of all agencies
- Real-time risk status
- Live updates via WebSocket
- Risk distribution statistics
- Quick action buttons

### Agency Detail (`/agency/{id}`)

- Individual agency analysis
- Agent vote visualization
- Risk timeline chart
- Simulation results
- Action recommendations
- Historical data

### Swarm Lab (`/swarm-lab`)

- Detailed agent analysis
- Agent reasoning explanations
- Agent weight adjustments
- Consensus breakdown
- Disagreement analysis

### Simulation Lab (`/simulation-lab`)

- What-if scenario testing
- Signal modification sliders
- Action outcome predictions
- Minimum regret analysis
- Comparative charts

### Feedback Logs (`/feedback-logs`)

- Learning statistics
- Agent performance metrics
- Weight optimization history
- System accuracy tracking
- Trend analysis

---

## 📊 Risk States

| Score Range | State | Color | Description | Action Required |
|-------------|-------|-------|-------------|-----------------|
| 0-25 | 🟢 Stable | Green | Low risk, normal behavior | Monitor only |
| 26-50 | 🟡 Stressed | Yellow | Moderate risk, monitoring needed | Increased monitoring |
| 51-75 | 🟠 Turbulent | Orange | High risk, consider action | Review and plan |
| 76-100 | 🔴 Collapsing | Red | Critical risk, immediate action required | Take action now |

---

## 🔄 How It Works

### 1. Data Ingestion

Real-time behavioral signals are collected for each agency from:
- Transaction systems
- User activity logs
- External APIs (TBO, etc.)
- Historical databases

### 2. Agent Analysis

Each of 7 specialized AI agents analyzes signals independently:
- **Drift Agent**: Detects pattern changes
- **Credit Agent**: Evaluates financial health
- **Identity Agent**: Assesses account stability
- **Memory Agent**: Compares with history
- **Peer Agent**: Benchmarks against peers
- **Prediction Agent**: Forecasts future
- **Incentive Agent**: Tests responsiveness

### 3. Swarm Consensus

Weighted voting combines agent opinions:
- Each agent votes with confidence score
- Weights adjust based on past accuracy
- Consensus risk score calculated (0-100)
- Disagreement index highlights conflicts

### 4. Disagreement Detection

Minority warnings highlight conflicting views:
- High disagreement = uncertain prediction
- Low disagreement = high confidence
- Triggers manual review when needed

### 5. Simulation

Counterfactual engine predicts outcomes:
- Tests 3 potential actions
- Runs Monte Carlo simulations
- Calculates expected losses
- Determines minimum regret action

### 6. Decision

Minimum regret policy selects optimal action:
- Balances risk vs. customer retention
- Considers financial impact
- Recommends best course of action

### 7. Learning

Feedback loop adjusts agent weights:
- Tracks actual outcomes
- Rewards accurate predictions
- Penalizes inaccurate predictions
- Optimizes swarm over time

---

## ⚙️ Configuration

### Environment Variables

Copy `.env.example` to `.env` and configure:

```bash
# Database
DATABASE_URL=postgresql://postgres:postgres@localhost:5432/traveltrust_ai

# API Keys
TBOAIR_API_KEY=your-tboair-api-key
OPENAI_API_KEY=your-openai-api-key
SENDGRID_API_KEY=your-sendgrid-api-key

# Security
SECRET_KEY=your-secret-key-here

# Application
APP_ENVIRONMENT=development
DEBUG=True
```

### Agent Weights

Configure initial agent weights:

```bash
DRIFT_AGENT_WEIGHT=1.0
CREDIT_AGENT_WEIGHT=1.0
IDENTITY_AGENT_WEIGHT=1.0
MEMORY_AGENT_WEIGHT=1.0
PEER_AGENT_WEIGHT=1.0
PREDICTION_AGENT_WEIGHT=1.0
INCENTIVE_AGENT_WEIGHT=1.0
```

### Risk Thresholds

Adjust risk classification thresholds:

```bash
RISK_THRESHOLD_STABLE=25
RISK_THRESHOLD_STRESSED=50
RISK_THRESHOLD_TURBULENT=75
```

---

## 🧪 Testing

### API Testing

```bash
# Get all agencies
curl http://localhost:8000/agencies

# Get agent votes for agency 1
curl http://localhost:8000/agents/votes/1

# Run simulation
curl -X POST http://localhost:8000/simulate \
  -H "Content-Type: application/json" \
  -d '{"agency_id": 1}'

# Get learning statistics
curl http://localhost:8000/learning/statistics
```

### WebSocket Testing

Connect to `ws://localhost:8000/ws/live-updates` to receive live risk updates every 5 seconds.

### Run Tests

```bash
# Backend tests
cd backend
pytest

# Frontend tests
cd frontend
npm test
```

---

## 🐛 Troubleshooting

### Database Connection Issues

```bash
# Check if PostgreSQL is running
docker ps | grep postgres

# Check database logs
docker logs traveltrust-db

# Restart database
docker-compose restart db
```

### Frontend API Errors

```bash
# Verify backend is running
curl http://localhost:8000/health

# Check CORS settings
# Verify NEXT_PUBLIC_API_URL in frontend/.env
```

### WebSocket Not Connecting

```bash
# Check backend logs
docker logs traveltrust-backend

# Verify WebSocket endpoint
wscat -c ws://localhost:8000/ws/live-updates
```

For more troubleshooting, see [DOCKER_SETUP.md](DOCKER_SETUP.md).

---

## 🤝 Contributing

We welcome contributions! Please follow these guidelines:

1. **Fork the repository**
2. **Create a feature branch** (`git checkout -b feature/amazing-feature`)
3. **Commit your changes** (`git commit -m 'Add amazing feature'`)
4. **Push to the branch** (`git push origin feature/amazing-feature`)
5. **Open a Pull Request**

### Development Guidelines

- Follow PEP 8 for Python code
- Use TypeScript for frontend code
- Write tests for new features
- Update documentation
- Follow security best practices

### Code of Conduct

- Be respectful and inclusive
- Provide constructive feedback
- Focus on what is best for the community
- Show empathy towards other community members

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- **TBO India** - For providing travel API integration
- **OpenAI** - For AI reasoning capabilities
- **FastAPI** - For the excellent web framework
- **Next.js** - For the amazing React framework

---

## 📞 Support

For questions, issues, or suggestions:

- 📧 Email: support@traveltrustai.com
- 📖 Documentation: [docs.traveltrustai.com](https://docs.traveltrustai.com)
- 💬 Community: [Discord](https://discord.gg/traveltrustai)
- 🐛 Issues: [GitHub Issues](https://github.com/yourusername/traveltrust-ai/issues)

---

## 🗺️ Roadmap

### Version 1.1.0 (Q2 2024)
- [ ] Multi-language support
- [ ] Advanced analytics dashboard
- [ ] Mobile app (iOS/Android)
- [ ] Enhanced reporting

### Version 1.2.0 (Q3 2024)
- [ ] Machine learning model improvements
- [ ] Additional agent types
- [ ] Integration with more travel APIs
- [ ] Custom alert rules

### Version 2.0.0 (Q4 2024)
- [ ] Real-time fraud detection
- [ ] Predictive maintenance
- [ ] Advanced simulation engine
- [ ] Enterprise features

---

<div align="center">

**Built with ❤️ by the TravelTrust AI Team**

[⬆ Back to Top](#traveltrust-ai---risk-management-system)

</div>