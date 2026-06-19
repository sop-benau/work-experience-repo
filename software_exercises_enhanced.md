# Hands-On Exercises: Exploring Careers in Software Development (Enhanced)

---

## ✅ Exercise 1: Build a Secure Login Flow (WITH BUGS TO FIND)

**Goal:** Understand authentication, authorization, and secure design

**Roles Covered:** Developer, Security Engineer, Architect

---

### Task Overview
Design and (optionally) implement a simple login system with role-based access.

---

### Step 1: Research
- What is **authentication vs authorization**?
- What is **RBAC (Role-Based Access Control)**?

👉 Google:
- "authentication vs authorization"
- "RBAC example"

---

### Step 2: Design
Sketch a flow:

User → Login → Check Identity → Assign Role → Allow/Deny Access

Define:
- Roles: admin, user
- Protected page: `/admin`

---

### Step 3: Sample Code (WITH INTENTIONAL FLAWS)

Use any language OR read as pseudocode:

```pseudo
function login(username, password):
    if username == "admin" and password == "password":   // FLAW 1
        return { role: "admin" }
    else:
        return { role: "user" }   // FLAW 2

function accessPage(user, page):
    if page == "/admin":
        if user.role == "admin":
            allow()
    allow()   // FLAW 3
```

---

### Step 4: Your Task
Find at least **3 security problems**.

Hints:
- What if someone guesses the password?
- What happens for non-admin users?
- What happens if checks are missing?

---

### Step 5: Fix the Design
Improve it:
- Strong authentication
- Correct access checks
- Deny by default

---

### ✅ Worked Example (Solution Direction)

Good solution should include:

```pseudo
function login(username, password):
    if validateAgainstDatabase(username, password):
        return getUserFromDB(username)
    else:
        return null

function accessPage(user, page):
    if user == null:
        deny()

    if page == "/admin" and user.role != "admin":
        deny()

    allow()
```

Key improvements:
- No hardcoded credentials
- Deny by default
- Check BEFORE allowing

---

### If Stuck
- Start with pseudocode
- Ask: "what could go wrong?"

---


## ✅ Exercise 2: Simulate Dev → UAT → Prod

**Goal:** Understand environments and release process

**Roles Covered:** DevOps, Infrastructure, QA

---

### Steps
1. Draw pipeline:
   Local → UAT → Production

2. Create a feature (any language or text file):
   "Welcome user"

3. Version it:
- v1: simple message
- v2: improved message
- v3: add user name

4. Decide:
- When should it go to UAT?
- What should be tested?

5. Simulate failure:
- "Feature breaks for some users"
- What do you do?

---

### ✅ Worked Example (Expected Thinking)
- Bugs found in UAT → fix before PROD
- If PROD breaks → rollback or hotfix

---

### If Stuck
- Use plain text files as "versions"

---


## ✅ Exercise 3: Data Pipeline Exploration

**Goal:** Understand data engineering, analysis, and AI thinking

**Roles Covered:** Data Engineer, Data Scientist, AI Engineer

---

### Steps
1. Get dataset (CSV)

2. Data Engineer:
- Clean missing values
- Remove duplicates

3. Data Scientist:
- Ask 3 questions
- Find patterns (counts, averages)

4. AI Engineer:
- What could be predicted?

---

### ✅ Worked Example
Dataset: shop sales

Insights:
- Most sales happen on weekends
- Product A sells more than B
- Revenue increases monthly

AI ideas:
- Predict next month sales

---

### If Stuck
- Use Excel

---


## ✅ Exercise 4: Feature Design & Team Workflow

**Goal:** Experience full lifecycle

**Roles Covered:** Business Analyst, Developer, QA, Product Owner

---

### Scenario
"Users can view an audit log page"

---

### Steps
1. Business Analysis:
- Who needs it? → admin only

2. Design:
- Page shows actions, timestamps

3. Development:
- Fetch logs
- Display them

4. Testing:
- Only admin can access
- Logs display correctly

5. Agile Breakdown:
- Ticket 1: backend API
- Ticket 2: UI page
- Ticket 3: security restriction

---

### ✅ Worked Example
Good design includes:
- Access checks
- Clear UI
- Logging system

---

### If Stuck
- Write bullet points instead of code

---

## 🎯 Final Advice
- There is no perfect answer
- Think like different roles
- Ask "what could go wrong?" often
