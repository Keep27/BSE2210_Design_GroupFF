

# BSE 2210 — Software Design  
**Assignment 1: Foundations of Modern Software Design (Introduction Unit)**  
**Group FF**  


# Table of Contents  

## 0.0 Executive Summary  

## 1.0 Software Design in 2025  
### 1.1 Design as a Process  
### 1.2 Design as an Artifact  
### 1.3 UML Use Case Diagram (Textual Description + Analysis)  
### 1.4 Architecture Decision Record (Microservices Decision)  
### 1.5 System Overview + Architecture Diagram (Textual Description)  

## 2.0 Modern Trends  
### 2.1 Microservices Architecture  
### 2.2 AI Integration  
### 2.3 Sustainable & Ethical Architecture  
### 2.4 Serverless Computing  

## 3.0 Business Case  
### 3.1 Problem Statement  
### 3.2 Proposed Solution  
### 3.3 Expected Value  

## 4.0 Outsourcing Options  
### 4.1 Onshore Outsourcing  
### 4.2 Offshore Outsourcing  
### 4.3 Nearshore Outsourcing  
### 4.4 Recommendation  

## 5.0 Cultural Intelligence in Design  

## 6.0 DevOps and DevSecOps  
### 6.1 CI/CD Pipeline (with Security)  
### 6.2 Benefits  

## 7.0 Non-Functional Requirements (NFRs)  

## 8.0 AI Opportunities and Ethical Concerns  

## 9.0 Risk Register  

## 10.0 Key Performance Indicators (KPIs)  

## 11.0 Roadmap  

## 12.0 Testing and Quality Assurance  

## 13.0 Conclusion  
---



---

## 0.0 Executive Summary  

This report presents the design proposal for the **Unified Student Experience Platform (USEP)**, a modern digital solution aimed at consolidating fragmented student services into a single integrated platform. Universities today rely on multiple disconnected systems — a Learning Management System (LMS) for academics, an HR system for staff, and separate portals for financial aid, clubs, and community events. This fragmentation creates inefficiencies, reduces student satisfaction, and increases long-term IT costs.  

The proposed USEP addresses these challenges by integrating all services into a **centralized, secure, and scalable hub**. It is built on **microservices architecture** to support scalability, **AI-driven personalization** to improve student outcomes, **DevOps/DevSecOps practices** to ensure continuous improvement and security, and **cultural inclusivity** to serve diverse international student populations.  

The report analyzes software design as both a **process** and an **artifact**, outlines architectural decisions, explains modern design trends, and develops a business case for the platform. It concludes with a roadmap, testing plan, and evaluation metrics to ensure success.  

---

## 1.0 Software Design in 2025  

### 1.1 Design as a Process  
In 2025, software design is not a one-time event but an **iterative and collaborative process** that bridges requirements and implementation. The process involves:  

1. **Requirements Gathering:** Identifying both functional (course registration, financial aid tracking) and non-functional requirements (performance, security, accessibility).  
2. **Modeling Interactions:** Using UML use case diagrams and architecture models to capture how users and systems interact.  
3. **Defining Architecture:** Establishing clear modules and layers that separate concerns and support scalability.  
4. **Prototyping & Validation:** Building early prototypes to gather feedback from stakeholders before committing to final designs.  
5. **Iteration & Feedback Loops:** Continuously refining the design based on testing and real-world input.  

Modern design is also **tool-driven**. CI/CD pipelines automate validation, while cloud monitoring ensures real-time observability of deployed systems. Design is therefore deeply connected with delivery.  

### 1.2 Design as an Artifact  
Artifacts represent the **visible outputs** of the design process. These include:  
- **UML Diagrams** (use case, class, and architecture) to communicate system behavior and structure.  
- **Architecture Decision Records (ADRs)** to capture the rationale for major design decisions.  
- **Process Blueprints** such as CI/CD pipeline diagrams.  
- **Documentation** that evolves as a “living” resource, guiding developers and stakeholders alike.  

Artifacts ensure continuity across the project lifecycle — from initial planning to long-term maintenance — and help align all stakeholders with a shared vision.  

---

### 1.3 UML Use Case Diagram (Textual Description + Analysis)  

**Actors:**  
- **Primary Actors:**  
  - *Student* — the main user, accessing academic, support, and community features.  
  - *Academic Advisor* — staff member supporting students academically.  
  - *System Administrator* — responsible for system performance, user management, and reporting.  
- **Secondary Actors (External Systems):**  
  - *LMS System* — for course content and assessments.  
  - *HR System* — for staff and administrative records.  

**Functional Categories:**  
1. **Academic Services:** Course Registration, Timetable Management, Results, and Grades.  
2. **Support Services:** AI Advising, Financial Aid Tracking, Loan Alerts, Academic Support.  
3. **Community Services:** Forums, Cultural Events, Student Clubs, Messaging.  
4. **System Management:** User Accounts, System Monitoring, Reports.  
5. **Integration Services:** Sync with LMS, HR, API Management, Data Sharing.  

**Analysis:**  
- All services are gated by **centralized authentication** for security.  
- Students have the broadest interactions, while advisors focus on support and administrators on system control.  
- External systems connect through integration services, preventing security loopholes.  
- Use cases are **modular**, aligning with microservices implementation.  

This model enhances **clarity, scalability, and maintainability** and provides a blueprint for later architecture decisions.  

---

### 1.4 Architecture Decision Record (ADR)  

**Title:** Adoption of Microservices Architecture  

**Context:**  
The platform must handle fluctuating demand (e.g., spikes during course registration or exam result releases). A monolithic design would struggle with scaling and maintenance.  

**Decision:**  
Adopt a **microservices architecture** where each module (Academic, Support, Community, Integration) is independently deployable, communicates via APIs, and can scale as needed.  

**Consequences:**  
- **Positive:**  
  - Each module scales independently (e.g., Academic module during registration).  
  - Failures are isolated to the affected service.  
  - Faster innovation as teams can deploy updates independently.  
- **Negative:**  
  - Requires container orchestration (Kubernetes, Docker).  
  - Increased complexity in logging, monitoring, and debugging distributed systems.  

---

### 1.5 System Overview + Architecture Diagram (Textual Description)  

The platform follows a **layered modular architecture**:  

1. **Frontend Layer (Web + Mobile):** Provides the user interface for students and staff.  
2. **Academic Services Module:** Handles course-related functions.  
3. **Support Services Module:** Manages AI advising and financial services.  
4. **Community Services Module:** Supports events, clubs, forums, and messaging.  
5. **Integration Layer:** Provides APIs to connect with LMS and HR systems.  
6. **Data Layer:** Manages student databases and secure cloud storage.  

**Flow of Data:**  
- Users interact with the **frontend layer**, which forwards requests to service modules.  
- Modules call the **integration layer** when LMS/HR data is needed.  
- All persistent records are stored in the **data layer** with role-based access controls (RBAC) and encryption.  

This architecture ensures **performance, resilience, and maintainability**.  

---

## 2.0 Modern Trends  

### 2.1 Microservices Architecture  
- **Benefits:** isolation of faults, independent scaling, and flexible updates.  
- **Risks:** requires robust DevOps pipelines, distributed tracing, and monitoring.  

### 2.2 AI Integration  
- **Applications:**  
  - Chatbots for academic advising and financial queries.  
  - Predictive analytics to identify at-risk students.  
  - Personalized cultural event and club recommendations.  
- **Risks:** Bias, loss of personal interaction.  
- **Mitigation:** Regular dataset audits, hybrid human-AI support, transparency in AI decisions.  

### 2.3 Sustainable & Ethical Architecture  
- Use of **renewable-energy cloud providers**.  
- Efficient resource utilization via container orchestration.  
- Adherence to **FAT principles**: Fairness, Accountability, Transparency.  

### 2.4 Serverless Computing  
- Best suited for **event-driven tasks** such as notifications and reminders.  
- Reduces costs as the university only pays per execution.  
- Increases scalability for small, temporary workloads.  

---

## 3.0 Business Case  

### 3.1 Problem Statement  
Currently, students navigate **disjointed systems** for academics, HR, and community activities. This causes:  
- User confusion and frustration.  
- Higher dropout risks due to poor digital experiences.  
- Rising IT maintenance costs for multiple overlapping platforms.  

### 3.2 Proposed Solution  
The **Unified Student Experience Platform (USEP)** consolidates services into one integrated system with seamless LMS and HR connectivity.  

### 3.3 Expected Value  
- **Student Retention:** streamlined experiences reduce stress and increase satisfaction.  
- **Operational Efficiency:** centralization reduces duplication and lowers IT overhead.  
- **International Competitiveness:** innovative services attract global students.  
- **Data Insights:** unified analytics enable smarter institutional decisions.  

---

## 4.0 Outsourcing Options  

### 4.1 Onshore Outsourcing  
- **Pros:** cultural alignment, clear communication.  
- **Cons:** high costs, limited availability of skilled talent.  

### 4.2 Offshore Outsourcing  
- **Pros:** significant cost savings, broad talent pools.  
- **Cons:** timezone and cultural gaps, potential quality and security concerns.  

### 4.3 Nearshore Outsourcing  
- **Pros:** balance between cost and cultural/timezone alignment.  
- **Cons:** minor alignment challenges still possible.  

### 4.4 Recommendation  
Adopt **nearshore outsourcing** to balance affordability, collaboration, and inclusivity. Strong governance and well-defined contracts will ensure success.  

---

## 5.0 Cultural Intelligence in Design  

To serve an international community, USEP integrates:  
- **Multilingual UI:** English, French, Swahili, Chinese, Arabic.  
- **Accessibility Standards:** WCAG 2.1 AA compliance.  
- **Timezone Awareness:** automatic adjustment of events and notifications.  
- **Cultural Inclusivity:** calendars and features that recognize global diversity.  

---

## 6.0 DevOps and DevSecOps  

### 6.1 CI/CD Pipeline (with Security)  
- **Source Control:** code repository with versioning.  
- **Automated Builds:** compilation and unit testing.  
- **Static Analysis:** code quality and vulnerability scanning.  
- **Containerization:** Docker images orchestrated with Kubernetes.  
- **Staging Tests:** integration and performance validation.  
- **Security Gates:** DevSecOps checks before production release.  
- **Monitoring:** production observability with logging and metrics dashboards.  

Proposed CI/CD Pipeline
[Source Code Repository]  
        ↓  
[CI Server: Automated Build + Unit Tests]  
        ↓  
[Static Code Analysis + Security Scan]  
        ↓  
[Containerization: Docker / Kubernetes]  
        ↓  
[Staging Environment: Integration Tests]  
        ↓  
[Security Gate: DevSecOps Checks]  
        ↓  
[Production Deployment: Monitored Rollout]

### 6.2 Benefits  
- Faster release cycles.  
- Early detection of vulnerabilities.  
- Reliable scaling for peak loads.  

---

## 7.0 Non-Functional Requirements (NFRs)  

- **Availability:** ≥ 99.9% uptime.  
- **Performance:** 95% of requests respond under 500ms.  
- **Scalability:** handle at least 10× normal loads during peak periods.  
- **Security:** encryption, RBAC, compliance with GDPR.  
- **Privacy:** informed consent for student data use.  

---

## 8.0 AI Opportunities and Ethical Concerns  

- **Opportunities:** 24/7 AI chatbot, predictive analytics, adaptive learning.  
- **Concerns:** algorithmic bias, reduced student-human interaction, privacy risks.  
- **Mitigation:** dataset auditing, hybrid systems with human oversight, explainable AI.  

---

## 9.0 Risk Register  

| Risk | Impact | Likelihood | Mitigation |
|------|--------|------------|------------|
| Data breach | High | Medium | Encryption, penetration tests |
| AI bias | High | Low-Med | Regular audits, human review |
| LMS/HR integration failure | Medium | Medium | Sandbox testing, clear API contracts |
| Vendor misalignment | Medium | Medium | Strong SLAs and governance |

---

## 10.0 Key Performance Indicators (KPIs)  

- **Uptime:** ≥ 99.9% availability.  
- **Adoption Rate:** 70% active student use in year one.  
- **Satisfaction:** +10 NPS increase in first year.  
- **Efficiency:** 30% faster support ticket resolution.  

---

## 11.0 Roadmap  

- **Phase 0 — Discovery (6 weeks):** Requirements gathering, prototyping.  
- **Phase 1 — MVP (12 weeks):** Academic + Authentication modules.  
- **Phase 2 — Integration (8 weeks):** LMS/HR adapters, Support module.  
- **Phase 3 — Community (8 weeks):** Forums, clubs, events.  
- **Phase 4 — Pilot (4 weeks):** Limited rollout to selected student groups.  
- **Phase 5 — Launch & Continuous Improvement:** University-wide adoption.  

---

## 12.0 Testing and Quality Assurance  

- **Unit Tests:** Ensure functionality with ≥ 80% coverage.  
- **Integration Tests:** Validate LMS/HR interoperability in a sandbox.  
- **Performance Tests:** Stress-test for peak registration loads.  
- **Security Tests:** SAST, DAST, and third-party penetration tests.  
- **Accessibility Tests:** Automated WCAG 2.1 checks plus manual reviews.  

---

## 13.0 Conclusion  

The **Unified Student Experience Platform (USEP)** consolidates fragmented systems into a **single, intelligent, and inclusive platform**.  

Through **microservices, AI integration, DevOps practices, and sustainable architecture**, the platform provides:  
- **Technical Modernity** — modular, scalable, resilient.  
- **Ethical Responsibility** — transparency, fairness, inclusivity.  
- **Strategic Advantage** — improved retention, efficiency, and competitiveness.  

USEP positions the university as a **leader in digital innovation** and ensures sustainability well beyond 2025.  

---
