# Wave Contractor Vocabulary & Professional Communication Guide

**Purpose:** Master the language of transportation, logistics, software, and startup teams  
**Scope:** 11 vocabulary categories + real-world usage examples  
**Goal:** Sound like a professional contractor from Day 1

---

## SECTION 1: Core Business Vocabulary (What Executives Use)

### KPI (Key Performance Indicator)
**Definition:** Measurable business metric that indicates success  
**Wave Context:** 
```
Revenue per ride: $3-5 (Wave's cut)
Driver acceptance rate: 80%+ (% of drivers accepting rides)
Customer completion rate: 92%+ (% of rides completed)
Driver retention (30-day): 70% (% staying active)
```

**How to Use:**
```
❌ "The system is good."
✅ "Our KPIs show 92% completion rate and $4.20 revenue per ride."
```

---

### SLA (Service Level Agreement)
**Definition:** Commitment to performance/availability  
**Wave Context:**
```
API uptime: 99.9% (3.5 minutes downtime/month max)
Dispatch time: <30 seconds (request to driver offer)
Driver availability: 24/7 (available in service area)
Support response: <1 hour (to critical issues)
```

**How to Use:**
```
❌ "The system should be fast."
✅ "Our SLA commits to <500ms API response time and 99.9% uptime."
```

---

### SOP (Standard Operating Procedure)
**Definition:** Documented process that anyone can follow  
**Wave Context:**
```
Driver onboarding SOP: Background check → License verification → Insurance approval → Training
Customer support SOP: Ticket received → Categorized → Assigned → Resolved → Closed
Payment reconciliation SOP: Daily payments → Verification → Reconciliation → Reporting
```

**How to Use:**
```
❌ "We'll figure out how drivers get approved."
✅ "Let me document the driver onboarding SOP so we have a repeatable process."
```

---

### Workflow
**Definition:** Sequence of steps to complete a task  
**Wave Context:**
```
RIDESHARE WORKFLOW:
  1. Customer opens app
  2. Enters destination
  3. Requests ride
  4. Driver assigned (dispatch)
  5. Driver navigates to customer
  6. Pickup
  7. Ride to destination
  8. Dropoff
  9. Payment (Stripe)
  10. Rating

MEDICAL TRANSPORT WORKFLOW:
  1. Hospital orders transport
  2. Patient eligibility verified
  3. Driver assigned
  4. Patient picked up
  5. Patient transported to appointment
  6. Appointment confirmed
  7. Patient returned
  8. Insurance billing triggered
```

**How to Use:**
```
❌ "I'll build the thing."
✅ "I'll map the complete workflow and identify where automation adds value."
```

---

## SECTION 2: Transportation Vocabulary (Wave's Domain)

### Dispatch (Critical for Wave)
**Definition:** Assigning rides to drivers  
**Technical Details:**
```
Dispatch Algorithm:
  1. Customer requests ride
  2. System finds 5 nearest drivers
  3. Sends notification to each
  4. First to accept gets the ride
  5. Driver navigates to pickup
```

**Optimization Goals:**
```
- Minimize dispatch time (<30 seconds)
- Maximize driver acceptance rate (>80%)
- Minimize deadhead miles (no passenger)
- Maximize vehicle utilization
```

**How to Use:**
```
❌ "The system assigns rides."
✅ "Our dispatch algorithm finds the 5 nearest drivers and assigns to first acceptor, optimizing for 30-second dispatch time and 80%+ acceptance rate."
```

---

### Fleet (All Vehicles)
**Definition:** Total inventory of vehicles  
**Wave Context:**
```
Wave Fleet Management:
  - Track 200-500 active vehicles
  - Monitor fuel consumption
  - Schedule maintenance
  - Track utilization (% of time earning revenue)
  - Manage insurance and registration
```

**Dashboard Would Show:**
```
- Vehicles online: 250/300
- Vehicles idle: 50
- Vehicles in maintenance: 3
- Fleet utilization: 83%
- Average fuel cost per mile: $0.18
```

**How to Use:**
```
❌ "The cars are working."
✅ "We're managing a fleet of 300 vehicles with 83% utilization and monitoring fuel efficiency and maintenance schedules."
```

---

### Utilization (Key Metric)
**Definition:** Percentage of time vehicles are generating revenue  
**Wave Formula:**
```
Utilization = Active Time / Available Time

Example:
Driver available: 8am-8pm = 12 hours
Driver active (with passenger): 10 hours
Utilization: 10/12 = 83%

Target: 80%+ utilization (vehicle constantly earning)
```

**Business Impact:**
```
83% utilization × 10 rides/shift × $4/ride = $33.20/shift revenue
If you improve to 90% utilization: $36.40/shift revenue = 10% more revenue
```

**How to Use:**
```
❌ "The drivers are busy."
✅ "We're tracking vehicle utilization at 83%, with a target of 90% through optimization."
```

---

### Deadhead Miles (Cost, Not Revenue)
**Definition:** Miles driven without a passenger (waste)  
**Wave Impact:**
```
SCENARIO: Driver drives 10 miles empty to find customer
  - Cost: Fuel ($1.80), Wear & tear ($2.00)
  - Revenue: $0
  - Net: -$3.80

OPTIMIZATION: Dispatch nearest driver
  - Deadhead miles reduced from 10 to 2 miles
  - Cost savings: $3.04 per ride
  - Annual impact (100 rides/day): $110,960 saved
```

**How to Use:**
```
❌ "The drivers drive around a lot."
✅ "We're minimizing deadhead miles through geospatial optimization, reducing waste per ride."
```

---

### ETA (Estimated Time of Arrival)
**Definition:** How long until driver/ride arrives  
**Wave Context:**
```
Driver ETA: 8 minutes (customer waiting in app)
Ride ETA: 22 minutes (to destination)

Accuracy matters:
  - If ETA says 5 min but takes 15 min → Customer angry
  - If ETA says 15 min but takes 5 min → Customer happy
  - Accurate ETA = better satisfaction
```

**How to Use:**
```
❌ "We tell customers how long the driver takes."
✅ "Our ETA prediction uses traffic data and historical patterns to provide accurate arrival estimates."
```

---

### Geo-Fencing (Virtual Boundaries)
**Definition:** Virtual boundary on map (driver can't leave, customer must be inside)  
**Wave Use Cases:**
```
Airport geo-fence: Only assigned drivers allowed in pickup zone
Hospital geo-fence: Only medical-certified drivers allowed
Downtown zone: Higher demand zone (can incentivize)
Service area boundary: Only serve customers within this zone
```

**Technical:**
```
Geo-fence = Latitude/Longitude polygon
When driver enters/exits → Notification triggered
When customer location outside service area → Alert
```

**How to Use:**
```
❌ "We keep drivers in the right place."
✅ "We use geo-fencing to ensure compliance with service area boundaries and incentivize high-demand zones."
```

---

### Route Optimization
**Definition:** Finding fastest/cheapest path  
**Wave Context:**
```
Single pickup: A → B (simple)
Multiple pickups: A → B → C → D (complex)
  - 24 possible routes to visit all 4 locations
  - Optimal might be: A → C → B → D (save 15% distance)
  - At scale (50 pickups): Finding optimal = complex

Medical transport: Hospital → Patient home → Appointment → Return
  Route optimization can reduce travel time 20-30%
```

**How to Use:**
```
❌ "We tell drivers where to go."
✅ "We implement route optimization for multi-pickup scenarios, reducing average trip time by 20%."
```

---

## SECTION 3: Driver Management Vocabulary (Supply Side)

### Driver Onboarding
**Definition:** Complete process to get new driver approved  
**Wave Onboarding SOP:**
```
Day 1: Apply
  - Basic info
  - Driver's license upload
  - Phone verification

Days 2-3: Background Check
  - Criminal record check
  - Driving record check
  - Insurance verification

Days 4-5: Document Review
  - License verification
  - Insurance valid
  - Vehicle registration check

Day 6: Training
  - App tutorial
  - Safety training
  - Payment explanation

Day 7: Approval
  - Driver can go online
  - Can accept rides
```

**Duration:** 7 days  
**Goal:** Ensure safe, reliable drivers  

**How to Use:**
```
❌ "We let drivers join."
✅ "Our driver onboarding SOP takes 7 days, includes background checks and training, ensuring quality."
```

---

### Driver Retention (Keeping Them)
**Definition:** Keeping drivers active on the platform  
**Wave Metrics:**
```
Day 1 retention: 100% (driver just started)
Week 1 retention: 70% (only 70% still active)
Month 1 retention: 50% (only half stay)
Month 3 retention: 30% (most churn)
```

**Retention Tactics:**
```
- Earnings guarantees ($20/hour minimum)
- Bonuses for peak hours (surge pricing)
- Incentives for hitting milestones (100 rides = $100 bonus)
- Engagement campaigns (weekly earnings summary)
- Feedback & support (in-app help, driver support team)
```

**How to Use:**
```
❌ "We want drivers to stay."
✅ "We're implementing retention strategies targeting 70%+ 30-day retention through earnings optimization and incentive programs."
```

---

### Driver Churn (Losing Them)
**Definition:** Rate at which drivers leave  
**Wave Calculation:**
```
Starting drivers: 300
New drivers: 50
Churned drivers: 100
Net: 300 + 50 - 100 = 250 drivers

Churn rate = 100 / 300 = 33% (very high!)
Target: <15% monthly churn
```

**Churn Reasons:**
```
- Not enough rides (30%)
- Low earnings (25%)
- Bad customer ratings (20%)
- Better opportunity elsewhere (15%)
- Vehicle issues (10%)
```

**Solution Mapping:**
```
Not enough rides? → Expand service area
Low earnings? → Increase surge pricing, bonuses
Bad ratings? → Improve customer service
Vehicle issues? → Provide fleet vehicles
```

**How to Use:**
```
❌ "Drivers are leaving."
✅ "We're seeing 25% monthly churn. Root cause analysis shows 30% due to insufficient ride volume. Solution: geo-expansion + surge pricing optimization."
```

---

### Driver Utilization (Time Earning)
**Definition:** Percentage of available time driver is earning revenue  
**Wave Calculation:**
```
Driver available: 8am-6pm = 10 hours = 600 minutes
Driver with passenger: 8 hours 20 min = 500 minutes
Driver waiting/idle: 1 hour 40 min = 100 minutes

Utilization = 500 / 600 = 83%

Target: 80%+ (driver constantly busy)
Healthy: 70-90%
Poor: <70%
```

**Impact:**
```
83% × 10 rides/shift × $4 Wave revenue = $33.20/shift
If drop to 70%: = $28/shift = $5.20/shift lost revenue
Scale: 300 drivers × 5 shifts/week = $7,800/week impact
```

**How to Use:**
```
❌ "Drivers are busy."
✅ "Average driver utilization is 83%, with range of 70-90%. We're optimizing dispatch to target 90% for revenue growth."
```

---

## SECTION 4: Software Development Vocabulary

### Frontend (What Users See)
**Definition:** User interface (UI) + user experience (UX)  
**Wave Frontend:**
```
Rider App (Mobile)
  - Login screen
  - Map screen (search destination)
  - Ride request screen
  - Driver tracking screen
  - Payment screen
  - Rating screen

Driver App (Mobile)
  - Login/logout
  - Go online/offline button
  - Ride offer notifications
  - Navigation screen
  - Navigation to customer
  - Pickup confirmation
  - Dropoff confirmation
  - Rating screen

Operator Dashboard (Web)
  - Live map (drivers + rides)
  - Real-time metrics
  - Driver performance
  - Customer metrics
  - System health
```

**How to Use:**
```
❌ "I'll build the app."
✅ "I'll design the frontend user flows for both rider and driver experiences, prioritizing clarity and conversion."
```

---

### Backend (Server-Side Logic)
**Definition:** Server, database, business logic  
**Wave Backend:**
```
API Endpoints:
  POST /rides - Create ride request
  GET /rides/:id - Get ride details
  PATCH /rides/:id - Update ride status
  POST /drivers/accept - Driver accepts ride
  POST /payments - Process payment
  GET /analytics - Get metrics

Databases:
  - Users (customers, drivers)
  - Rides (trip history)
  - Payments (financial data)
  - Ratings (feedback)
  - Analytics (metrics)

Business Logic:
  - Dispatch algorithm
  - Payment processing
  - Rating system
  - Surge pricing
  - Eligibility checks
```

**How to Use:**
```
❌ "The backend is working."
✅ "Our backend APIs handle dispatch, payment processing, and real-time updates with <500ms response times."
```

---

### Database (Data Storage)
**Definition:** Organized data storage  
**Wave Databases:**
```
Users Table:
  - user_id, name, email, phone, ratings

Drivers Table:
  - driver_id, name, vehicle_info, ratings, earnings

Rides Table:
  - ride_id, customer_id, driver_id, pickup, dropoff, fare, status

Payments Table:
  - payment_id, ride_id, amount, status, timestamp

Ratings Table:
  - rating_id, ride_id, from_user, to_user, score, comment
```

**Scale:**
```
Users: 50,000+
Drivers: 5,000+
Rides: Millions (100K/day × 365 days = 36.5M/year)
Payments: Millions (every ride)
Ratings: Millions (every ride)
```

**How to Use:**
```
❌ "We store data."
✅ "Our PostgreSQL database stores rides, payments, and ratings with optimized indexes for query performance."
```

---

### API (Application Programming Interface)
**Definition:** System-to-system communication  
**Wave APIs:**
```
Google Maps API
  - Get directions
  - Calculate ETA
  - Get traffic info

Stripe API
  - Process payments
  - Create charges
  - Refund transactions

Twilio API
  - Send SMS notifications
  - Voice calls for support

Firebase API
  - Push notifications
  - Real-time messaging

Wave Internal APIs
  - /dispatch - Find drivers
  - /rides - Manage rides
  - /payments - Handle money
  - /analytics - Get metrics
```

**How to Use:**
```
❌ "We connect to Google Maps."
✅ "We integrate with Google Maps API for real-time routing and ETA prediction, and Stripe for PCI-compliant payment processing."
```

---

### Authentication (Verifying Identity)
**Definition:** Proving you are who you claim  
**Wave Auth:**
```
Phone number login:
  - User enters phone number
  - Receives SMS code
  - Enters code to verify
  - Logged in

Email + password:
  - User creates account (email + password)
  - System hashes password (never stores plain text)
  - User logs in with email + password
  - System verifies password

Two-factor (2FA):
  - Login with password
  - Receive SMS code
  - Enter code
  - Access granted
```

**Security:**
```
Passwords: Never stored as plain text (hashed with bcrypt)
Tokens: JWT tokens expire after 24 hours
Refresh tokens: Extend session without re-login
API keys: Separate keys for drivers, customers, admins
```

**How to Use:**
```
❌ "Users log in."
✅ "We implement JWT-based authentication with 24-hour token expiration and SMS-based 2FA for sensitive operations."
```

---

### Authorization (What You Can Access)
**Definition:** Determining permissions based on role  
**Wave Authorization:**
```
Customer Role:
  ✅ Can request rides
  ✅ Can view their ride history
  ✅ Can rate drivers
  ❌ Cannot see other customers' data

Driver Role:
  ✅ Can accept rides
  ✅ Can view earnings
  ✅ Can rate customers
  ❌ Cannot modify pricing

Admin Role:
  ✅ Can view all data
  ✅ Can modify driver/customer accounts
  ✅ Can access analytics
  ✅ Can change settings
```

**How to Use:**
```
❌ "Users can see stuff."
✅ "We implement role-based access control with three tiers: Customer, Driver, Admin, each with specific permissions."
```

---

## SECTION 5: Mobile App Vocabulary

### Native App
**Definition:** Built specifically for one platform (iOS or Android)  
**Wave Native:**
```
iOS App (iPhone/iPad):
  - Built in Swift
  - Optimized for iPhone
  - Uses iOS-specific features (Apple Pay, iCloud)

Android App (Android phones):
  - Built in Kotlin
  - Optimized for Android
  - Uses Android-specific features (Google Pay, Android notifications)
```

**Pros:**
- Optimized performance
- Full access to device features
- App Store/Play Store presence

**Cons:**
- Two codebases to maintain
- 2x development effort

**How to Use:**
```
❌ "We have an app."
✅ "We maintain native iOS (Swift) and Android (Kotlin) apps, ensuring platform-specific optimization."
```

---

### Cross-Platform
**Definition:** One codebase runs on multiple platforms  
**Wave Cross-Platform:**
```
React Native:
  - One codebase (JavaScript)
  - Compiles to iOS and Android
  - 70-80% code sharing
  - Wave rider app: React Native
```

**Pros:**
- Single codebase
- Faster development
- Consistent experience

**Cons:**
- Slightly less optimized
- Limited access to device features

**How to Use:**
```
❌ "We have iOS and Android apps."
✅ "We use React Native for 70% code sharing between iOS and Android, reducing development time."
```

---

### Push Notification
**Definition:** Message sent to phone without user opening app  
**Wave Notifications:**
```
"Driver arriving in 5 minutes"
"Your ride is on the way"
"Rate your driver"
"Special offer: 20% off next ride"
"Your driver is 2 minutes away"
```

**Technical:**
```
Firebase Cloud Messaging (FCM) → Sends notification
Device displays notification
User taps notification → Opens app to relevant screen
App tracks notification metrics (delivery, opens, clicks)
```

**Impact:**
```
Good notifications: Increase engagement 40%
Bad notifications: Users disable them (or worse, uninstall)
Timing matters: 2pm notification ignored, 5pm notification engaged
```

**How to Use:**
```
❌ "We send messages to phones."
✅ "We implement Firebase Cloud Messaging with personalized timing and content optimization for 40% engagement increase."
```

---

## SECTION 6: Cloud & Infrastructure Vocabulary

### Server (Hardware Running Software)
**Definition:** Computer running applications  
**Wave Servers:**
```
Web Servers (receive requests from apps):
  - 10+ servers in load-balanced configuration
  - Handle API requests
  - Run business logic

Database Servers:
  - Primary database (read/write)
  - Read replicas (read only, for scaling)
  - Backup servers (recovery)

Cache Servers (Redis):
  - Store frequently accessed data
  - Reduce database load
  - Faster responses
```

**Scale:**
```
Small Wave: 3-5 servers
Medium Wave: 20-50 servers
Large Wave: 100+ servers globally
```

**How to Use:**
```
❌ "The system runs on servers."
✅ "We use 15 load-balanced application servers and 3-node PostgreSQL cluster with read replicas for <500ms response times."
```

---

### Hosting (Where It Lives)
**Definition:** Cloud provider running your servers  
**Wave Hosting Options:**
```
AWS (Amazon Web Services):
  - EC2 instances (servers)
  - RDS (database)
  - S3 (file storage)
  - CloudFront (CDN)
  
Google Cloud:
  - Compute Engine
  - Cloud SQL
  - Cloud Storage

Vercel (for web frontend):
  - Automatic deployments
  - CDN globally distributed
  - Serverless functions
```

**Choice Criteria:**
```
Cost: AWS ~30% cheaper than others
Features: AWS most complete
Simplicity: Vercel easiest for web
Global reach: Vercel best for distribution
```

**How to Use:**
```
❌ "We're in the cloud."
✅ "We host backend on AWS (EC2 + RDS) for reliability and frontend on Vercel for global CDN distribution."
```

---

### Deployment (Publishing Code)
**Definition:** Moving code from development to live production  
**Wave Deployment Process:**
```
Developer writes code
  ↓
Code review (other developers approve)
  ↓
Tests run automatically (unit, integration, security)
  ↓
If tests pass: Deploy to staging (test environment)
  ↓
Manual testing in staging
  ↓
If approved: Deploy to production (live for customers)
  ↓
Monitor performance and errors
```

**Tools:**
```
GitHub Actions: Runs tests automatically
DockerCI: Builds containers
Kubernetes: Manages deployment
Rollback available if issues detected
```

**How to Use:**
```
❌ "I'll put it live."
✅ "I'll deploy through our CI/CD pipeline: automated testing → staging deployment → monitoring → production release with rollback capability."
```

---

### Production Environment (LIVE)
**Definition:** Real system used by real customers  
**Wave Production:**
```
CRITICAL:
  - Real customers using the app
  - Real money being processed
  - Real drivers/vehicles assigned
  - Any downtime = lost revenue
  
Requirements:
  - 99.9% uptime SLA
  - Automatic backups
  - Disaster recovery
  - 24/7 monitoring
  - On-call engineer always available
```

**How to Use:**
```
❌ "I'll test it in production."
✅ "We test thoroughly in staging before production deployment to minimize risk to live systems."
```

---

### Staging Environment (TEST)
**Definition:** Copy of production for safe testing  
**Wave Staging:**
```
Identical to production EXCEPT:
  - Test data (fake customers, fake drivers)
  - Fake payment processing (Stripe test mode)
  - No real revenue impact
  - Can be taken offline for testing

Use cases:
  - Test new features before production
  - Load testing (stress test without affecting customers)
  - Security testing
  - Database migration testing
```

**How to Use:**
```
❌ "I'll try it and see if it breaks."
✅ "I'll validate in staging with test data before production deployment."
```

---

### Uptime (Availability)
**Definition:** Percentage of time system is operational  
**Wave Uptime Targets:**
```
99% uptime = 3.6 hours downtime/year
99.9% uptime = 43 minutes downtime/year ← Wave target
99.99% uptime = 4.3 minutes downtime/year ← Premium target

Downtime calculation:
365 days × 24 hours = 8,760 hours/year
99.9% uptime = 8,760 - 8.76 hours = 8,751.24 hours available
Downtime allowed: 8.76 hours = 43 minutes
```

**How to Use:**
```
❌ "The system is usually up."
✅ "We target 99.9% uptime SLA, limiting outages to 43 minutes/year through redundancy and monitoring."
```

---

## SECTION 7: AI & Automation Vocabulary (Wave's Future)

### Workflow Automation
**Definition:** Using software to replace manual tasks  
**Wave Automation Opportunities:**
```
Current (Manual):
  Ride completed → Human creates invoice → Human emails customer

Automated:
  Ride completed → System creates invoice → System sends email
  
Impact:
  - 1 minute manual task → Instant automation
  - 300 rides/day × 1 minute = 300 minutes saved
  - 5 hours/day of staff time saved
```

**Tools:**
```
n8n: Visual workflow builder
Zapier: Automation platform
Make: Integration platform
Custom scripts: Python automation
```

**How to Use:**
```
❌ "We'll do it manually."
✅ "I'll implement workflow automation for post-ride invoicing and notifications using n8n, reducing manual work by 5 hours/day."
```

---

### AI Agent
**Definition:** Software that performs tasks autonomously  
**Wave AI Agents:**
```
Dispatch Agent:
  - Receive ride request
  - Find optimal driver
  - Send offer
  - Monitor acceptance
  - Retry if declined

Support Agent:
  - Receive support ticket
  - Classify issue
  - Provide automated response
  - Escalate if complex

Fraud Detection Agent:
  - Monitor transactions
  - Detect anomalies
  - Flag suspicious activity
  - Prevent fraud
```

**How to Use:**
```
❌ "We could use AI."
✅ "I'll implement an AI agent for customer support using LLM that resolves 40% of tickets without human intervention."
```

---

### LLM (Large Language Model)
**Definition:** AI model trained on massive text (GPT-4, Claude, Gemini)  
**Wave Use Cases:**
```
Customer Support:
  "Where's my driver?" → LLM looks up ride → "Your driver is 5 minutes away"

Dynamic Pricing:
  "Should we surge price?" → LLM analyzes demand → Recommends $1.50x surge

Driver Feedback:
  "Write feedback for this driver" → LLM generates → Professional feedback

Prediction:
  "Will this customer churn?" → LLM analyzes history → High/medium/low risk
```

**How to Use:**
```
❌ "We could use ChatGPT."
✅ "We integrate OpenAI's GPT-4 API for intelligent customer support automation, with context from our customer database for personalized responses."
```

---

### Prompt Engineering
**Definition:** Writing instructions for AI models  
**Good Prompt:**
```
"You are a Wave customer support agent. Answer questions about rides, 
payments, and driver ratings. Keep responses under 2 sentences. If 
unsure, escalate to human. Use customer's first name."
```

**Bad Prompt:**
```
"Answer customer questions."
```

**Impact:**
```
Good prompt → 90% satisfaction
Bad prompt → 40% satisfaction
```

**How to Use:**
```
❌ "I'll use AI to answer questions."
✅ "I'll implement prompt engineering with context injection to provide personalized, accurate support responses."
```

---

### Vector Database
**Definition:** Database that stores knowledge for AI retrieval  
**Wave Example:**
```
Ingest (one-time):
  Load Wave SOP: "How to report a safety issue"
  Load policies: "Cancellation policy"
  Load FAQs: "Can I change my destination?"
  
When customer asks "Can I modify my trip?":
  System searches vector database
  Retrieves relevant policy
  LLM answers with policy context
  
Result: Accurate answers backed by company knowledge
```

**Tools:**
```
Pinecone: Managed vector database
ChromaDB: Open-source vector database
Weaviate: GraphQL-based vector database
```

**How to Use:**
```
❌ "AI will figure it out."
✅ "I'll implement RAG with ChromaDB vector database to ground AI responses in Wave's actual policies and procedures."
```

---

### RAG (Retrieval Augmented Generation)
**Definition:** AI pulls company knowledge before answering  
**Wave Example:**
```
WITHOUT RAG:
  Customer: "What's your cancellation policy?"
  AI: "Most companies allow cancellation within 5 minutes"
  (Generic, possibly wrong)

WITH RAG:
  Customer: "What's your cancellation policy?"
  System retrieves Wave's cancellation policy
  AI: "Wave allows cancellation up to pickup. If driver has already started heading to you (within 2 minutes), a $2 fee applies."
  (Accurate, company-specific)
```

**Impact:**
```
WITHOUT RAG: 60% of answers are wrong/generic
WITH RAG: 95% of answers are accurate
```

**How to Use:**
```
❌ "I'll use an LLM for support."
✅ "I'll implement RAG (Retrieval Augmented Generation) where AI retrieves Wave's policies before responding, ensuring 95%+ accuracy."
```

---

## SECTION 8: Data & Analytics Vocabulary

### Dashboard (Visual Metrics)
**Definition:** Visual display of business metrics  
**Wave Dashboards:**
```
Operator Dashboard:
  - Live map with drivers and rides
  - Real-time metrics (rides/hour, revenue/hour)
  - Driver performance (top earners, ratings)
  - System health (uptime, errors)

Driver Dashboard:
  - Earnings this week/month
  - Trip history
  - Ratings and feedback
  - Predicted earnings

Customer Analytics:
  - Repeat ride rate
  - Churn rate
  - NPS (satisfaction)
  - Lifetime value
```

**Tools:**
```
Grafana: Real-time dashboards
Metabase: SQL-based BI
Looker: Enterprise analytics
Tableau: Advanced visualizations
```

**How to Use:**
```
❌ "I'll show the numbers."
✅ "I'll build a Grafana dashboard showing real-time KPIs: dispatch time, completion rate, revenue/hour, and driver utilization."
```

---

### Business Intelligence (BI)
**Definition:** Using data to make decisions  
**Wave BI Questions:**
```
"Which geographic zone has highest profitability?"
"What's the churn rate by cohort (when they joined)?"
"How does weather affect demand?"
"Should we surge price now?"
"Which drivers are at risk of churn?"
```

**How to Use:**
```
❌ "The data shows something."
✅ "Our BI analysis reveals that medical transport has 65% higher margins than rideshare, recommending resource reallocation."
```

---

### Data Pipeline
**Definition:** Flow of data from source to dashboard  
**Wave Pipeline:**
```
Ride Data (source)
  ↓
Database (PostgreSQL)
  ↓
Data Warehouse (Snowflake)
  ↓
Analytics (SQL queries)
  ↓
Dashboard (Grafana)
  ↓
Decision made!
```

**Scale:**
```
100 rides/second → Database
8.6M rides/day → Data warehouse
Monthly aggregation → Dashboard
```

**How to Use:**
```
❌ "We'll get the data somehow."
✅ "I'll design a data pipeline: PostgreSQL → Snowflake warehouse → dbt transformations → Grafana dashboards."
```

---

### ETL (Extract, Transform, Load)
**Definition:** Moving and transforming data between systems  
**Wave ETL Example:**
```
EXTRACT:
  Pull ride data from Wave production database

TRANSFORM:
  - Calculate revenue (fare × Wave cut)
  - Group by driver
  - Calculate average rating
  - Remove sensitive customer data (PII)

LOAD:
  Load into analytics warehouse for reporting
```

**How to Use:**
```
❌ "I'll move the data."
✅ "I'll implement nightly ETL to extract rides from production, transform into analytical format (revenue, driver metrics), and load into warehouse for reporting."
```

---

## SECTION 9: Finance Vocabulary (Understand Profitability)

### CAC (Customer Acquisition Cost)
**Definition:** How much it costs to acquire one customer  
**Wave Calculation:**
```
Monthly marketing spend: $50,000
New customers acquired: 2,000
CAC = $50,000 / 2,000 = $25 per customer

Healthy CAC:
  - If LTV is $250, CAC of $25 is excellent (10x return)
  - If LTV is $50, CAC of $25 is bad (2x return)
```

**How to Use:**
```
❌ "We're spending on marketing."
✅ "Our CAC is $25 with an LTV of $250, resulting in a healthy 10:1 ratio."
```

---

### LTV (Lifetime Value)
**Definition:** Total revenue expected from one customer  
**Wave Calculation:**
```
Repeat customer rate: 50% (50% of customers ride again)
Average rides per customer: 12
Average fare: $12
Wave cut: 25% = $3 per ride

LTV = 12 rides × $3 = $36 per customer (conservative)
     OR
LTV = (repeat rate × rides × revenue) = 50% × 12 × $3 = $18
```

**Healthy LTV:LTV CAC Ratio:**
```
LTV:CAC > 3 = profitable
LTV:CAC = 10 = excellent
LTV:CAC = 2 = barely viable
LTV:CAC = 1 = losing money on acquisition
```

**How to Use:**
```
❌ "Customers are valuable."
✅ "Our LTV is $200 with CAC of $25, yielding 8:1 ratio and strong unit economics."
```

---

## SECTION 10: Professional Communication Examples

### Instead of THIS, Say THIS:

```
❌ "The website is broken."
✅ "We're experiencing a production issue affecting API response times. 
   Current status: investigating. ETA resolution: 30 minutes."

❌ "I'll build it."
✅ "I'll review the requirements, document the scope, estimate effort 
   (80 hours), define success metrics, and provide a delivery timeline."

❌ "The system is slow."
✅ "Performance monitoring shows 2-second API response times 
   (target: <500ms). Root cause: database query optimization needed. 
   Solution: implement indexing and caching. ETA: completion by Friday."

❌ "I made some changes."
✅ "I've deployed updates to the dispatch algorithm, improving driver 
   acceptance rate from 78% to 82%. Validation complete. No regression detected."

❌ "Drivers aren't staying."
✅ "Driver 30-day retention is 65% (target: 75%). Analysis shows 40% 
   churn due to insufficient ride volume. Recommendation: geo-expansion 
   in underserved areas."

❌ "The app crashed."
✅ "Production incident: iOS app crash rate spiked to 5% (SLA: <1%). 
   Root cause: memory leak in real-time tracking. Fix deployed. 
   Monitoring shows crash rate returned to 0.3%. Post-mortem scheduled."

❌ "We need automation."
✅ "I recommend implementing workflow automation for post-ride invoicing 
   using n8n. Current manual effort: 5 hours/day. Projected savings: 
   $150K annually. ROI: 12 weeks."

❌ "The data is messy."
✅ "Our data quality metrics show 12% incomplete driver records. 
   I'm implementing validation rules in the onboarding pipeline 
   to ensure 100% data completeness going forward."

❌ "I'll use AI for this."
✅ "I'll implement RAG-enhanced customer support using GPT-4, 
   grounding responses in Wave's actual policies. Projected resolution 
   rate: 40% without human escalation. Accuracy target: 95%."
```

---

## SECTION 11: Quick Reference — Vocabulary Used in Interviews

### Must Know These Phrases

**Operational:**
- "KPI" — "Our KPIs show..."
- "SLA" — "We committed to 99.9% SLA..."
- "SOP" — "Let me document the SOP..."
- "Workflow" — "I'll map the complete workflow..."

**Transportation:**
- "Dispatch" — "Our dispatch algorithm..."
- "Utilization" — "Driver utilization is 83%..."
- "Deadhead miles" — "We minimize deadhead miles..."
- "Fleet" — "We manage a fleet of..."

**Software:**
- "Frontend/Backend" — "Frontend is React Native, Backend is Node.js..."
- "API" — "We integrate with Google Maps API..."
- "Database" — "Our PostgreSQL database..."
- "Uptime" — "99.9% uptime SLA..."

**Business:**
- "CAC/LTV" — "LTV:CAC ratio of 8:1..."
- "Retention" — "Driver 30-day retention..."
- "Churn" — "Monthly churn rate..."

**AI:**
- "RAG" — "Retrieval Augmented Generation for accuracy..."
- "LLM" — "We use GPT-4 for customer support..."
- "Prompt engineering" — "I'll engineer prompts for..."
- "Workflow automation" — "n8n automation reduces manual effort by..."

---

## Your Secret: Use This Vocabulary Naturally

**INTERVIEW SCENE:**

```
Wave Manager: "So what would you do first?"

Your Answer (Uses Vocabulary):
"First, I'd document the current SOPs and identify optimization 
opportunities. Then I'd map the complete workflow, pinpoint bottlenecks, 
and quantify impact using KPIs. For driver retention specifically, I'd 
analyze churn data by cohort, identify root causes (utilization, 
earnings, ratings), and recommend targeted interventions. For dispatch, 
I'd review the current algorithm's performance against SLA targets for 
acceptance rate and deadhead miles, then propose geospatial optimization 
using PostGIS. I'd implement monitoring dashboards in Grafana to track 
these KPIs in real-time and set up alerts for SLA violations."

Wave Manager thinks: "This person knows what they're talking about."
```

---

## Summary: Master This Vocabulary

If you can comfortably use these terms in context, you'll sound like a professional contractor:

```
✅ Dispatch, Fleet, Utilization, Deadhead miles, ETA, Geo-fencing, Route optimization
✅ Driver Onboarding, Retention, Churn, Utilization
✅ Frontend, Backend, Database, API, Authentication, Authorization
✅ KPI, SLA, SOP, Workflow
✅ Uptime, Deployment, Production, Staging
✅ CAC, LTV, Retention, Churn, Profitability
✅ Dashboard, Data Pipeline, ETL
✅ RAG, LLM, Prompt Engineering, Workflow Automation
```

You'll be the contractor who sounds like they belong.

