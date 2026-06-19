# How Real Software Development Works

## 🔄 The Software Lifecycle of a single system
```mermaid
    flowchart LR
        subgraph WFF[Waterfall Flow]
            A1[Problem Identification] --> B1[Analysis] --> C1[Design] --> D1[Coding] --> E1[Testing] --> F1[Code Review] --> G1[Configuration] --> H1[✅ Security] --> I1[Deployment] --> J1[Scaling + Availability] --> K1[Data Collection] --> L1[Data Analysis] --> M1[Prediction + Decision Making Aid]
        end

        subgraph TDDF[Test-Driven Flow]
            A2[Problem Identification] --> B2[Analysis] --> C2[Design] --> D2[Testing] --> E2[Coding] --> F2[Code Review] --> G2[Configuration] --> H2[Security] --> I2[Deployment] --> J2[Scaling + Availability] --> K2[Data Collection] --> L2[Data Analysis] --> M2[Prediction + Decision Making Aid]

            E2 -->|fix| D2
        end


        WFF --> TDDF

        classDef tdd fill:#944,stroke:#333,stroke-width:2px,color:white
        class D2 tdd
        class E2 tdd
```
**Key idea:** It’s not just coding—it’s a full process.

### ⚙️ Methodologies
#### Waterfall
- One big delivery
- Must be right first time

#### Agile + TDD
- Small steps
- Fail → fix → improve
- Sprint: 1 sprint = 1-week to 4-week cycle = sprint planning -> everyday stand up -> sprint review -> retrospective = teamwork + communication
- Scrum: define how people, event and artifacts are managed in a sprint
    - Roles
        - Product Owner defines priorities
        - Scrum Master facilitates the process
        - Development team does the work
    - Events
        - Sprint planning defines what to do in this sprint
        - Daily stand up for quick communication and blocker identification
        - Sprint review for demo and user feedback
        - Sprint retrospective for things learnt or to be improved
    - Artifacts
        - Product backlog defines what is pending to complete in later sprints (i.e. tech debt)
        - Sprint backlog are the tasks carries forward to the next sprint (subject to Product Owner approval)
        - Increment is the incremental working features built in a sprint on the product

#### Sprint Cycle (2 weeks)
Planning → Daily stand-up → Development → Demo


---

## 🧬 Software Evolution → Version Control
```mermaid
    flowchart LR
        subgraph v_1[V<sub>1</sub>]
            A1[Problem Identification] --> B1[Analysis] --> ELL1[...]  --> L1[Data Analysis] --> M1[Prediction + Decision Making Aid]
        end

        subgraph v_2[V<sub>2</sub>]
            A2[Problem Identification] --> B2[Analysis] --> ELL2[...] --> L2[Data Analysis] --> M2[Prediction + Decision Making Aid]
        end

        subgraph v_n[V<sub>n</sub>]
            A3[Problem Identification] --> B3[Analysis] --> ELL3[...] --> L3[Data Analysis] --> M3[Prediction + Decision Making Aid]
        end


        v_1 --> v_2 --> ELL4[...] --> v_n

        classDef ELL fill:transparent,color:#333,stroke-width:0
        class ELL1 ELL
        class ELL2 ELL
        class ELL3 ELL
        class ELL4 ELL
```

### 👨‍💻 Distributed Development
- Multiple developers
    - V<sub>1</sub> and V<sub>2</sub> can be done by 2 developers at the same time
    - developers does not need to sit together geographically
- Version control (Git)
- Code reviews
    - developers give peer reviews and comments
    - product is built upon concensus and accuracy

Software = teamwork.

---

## 🌍 Environments
```mermaid
    flowchart LR
        subgraph dev [Development]
            direction LR
            d1[Localhost]
            d2[Quick test-fix-try round trip]
            d3[Single-User]
        end

        subgraph testing [Testing]
            direction LR
            t1[also called UAT meaning User-Acceptance Test environment]
            t2[take deployment from development environment]
            t3[multi-user]
            t4[multi-version]
            t5[for user approval or functional verification]
            t6[might need further iterations if user rejects]
        end

        subgraph production [Production]
            direction LR
            p1[deploy a UAT approved version]
            p2[could be on-premises or on a cloud]
            p3[could be native deployment or dockerized]
            p4[live for target users and real data]
            p5[costly if mistakes / bugs occur here]
        end

        dev --> testing --> production
```

### Goals
- Ensure accuracy
- Scalability
- Minimize cost of error
- Minimize cost of evolution
- Maximize system cooperation and synergy

---

## Infrastructure

**Benefit of a cooperating infrastructure &gt; Sum of benefits from individual systems**

```mermaid
    flowchart LR
        subgraph infra [Infrastructure]
            direction LR
            S1[System 1] <--> S2[System 2]
            S1[System 1] <--> S3[System 3]
            S1[System 1] <--> S4[System 4]

            S2 <--> S3
            S2 <--> S4

            S3 <--> S4
        end

        infra
```

### 🏢 Example systems in an infrastructure
- Authentication server
- Mail server
- Database
- Inventory system
- CRM system (Customer Relationship System)
- ERP system (Enterprise Resource Planning)
- Accounting system
- Internal Control system
- Human Resource system
- Helpdesk system (An example to walk you through)
    - Dashboard
    - Callbacks
    - Helpdesk
    - ...
    - Group Permissions
- Web/API server
- Firewall
- Proxy
- VPN


---

## 🔐 Security Fundamentals
- **Authentication** → Who are you? (login, Entra ID)
- **Authorization** → What can you access?
- **Permissions** → Fine-grained control (admin vs user)

Security applies at every stage.

---

## 🧠 Career Paths

### Build
- Developer
- Application Specialist

### Design
- Architect
- Cloud Engineer

### Operate
- DevOps Engineer
- Infrastructure Engineer

### Protect
- Security Engineer

### Data
- Data Engineer (pipelines)
- Data Scientist (insights)
- AI Engineer (intelligent systems)

### Business
- Business Analyst
- Product Owner

---

## 🎯 Key Takeaways
- Software = systems + people + process
- Security is everywhere
- Many career paths from the same foundations
- Real work = team problem solving
