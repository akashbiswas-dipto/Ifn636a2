# Software Requirements Specification
**Project:** Food Waste Management Platform  
**Prepared for:** IFN636 Assessment 2  

---

## 1. Introduction  

### 1.1 Purpose  
The purpose of the Food Waste Management Platform (FWMP) is to connect food contributors (e.g., households, restaurants, supermarkets) with beneficiaries (e.g., charities, individuals in need) to minimize food waste. The system enables users to log surplus food, track availability, and claim contributions efficiently.  

### 1.2 Problem Statement  
Food waste is a pressing global issue, with large quantities of edible food discarded due to lack of proper redistribution channels. Current donation methods are often informal, inefficient, and lack transparency. This results in wasted resources and missed opportunities to support communities in need. FWMP addresses this gap by providing a structured digital platform for food contributions and collection.  

### 1.3 Scope  
- **In-Scope Features:**  
  - Secure user authentication (Login, Register).  
  - User roles: Contributor and Beneficiary.  
  - Logging food contributions with details (title, category, quantity, pickup location, time).  
  - Dashboard displaying available contributions.  
  - Claiming food items by beneficiaries.  
  - User profile management.  

- **Out-of-Scope Features:**  
  - Payment processing.  
  - Third-party logistics/delivery integration.  

### 1.4 User Characteristics  
- **Contributors:** Households, restaurants, supermarkets (basic to moderate computer skills).  
- **Beneficiaries:** Charities, NGOs, or individuals (basic computer literacy).  
- **Admins:** Monitor activities, manage users.  
- Users may access via web browsers on desktops and mobile devices.  

### 1.5 Constraints  
- Must comply with food safety and liability disclaimers.  
- Secure storage of user data (privacy compliance).  
- Deployed on AWS cloud infrastructure.  
- Budget and development time limited to assessment scope.  

---

## 2. Functional Requirements  

1. **User Authentication**  
   - FWMP shall allow users to register with name, email, password, address, and user type.  
   - FWMP shall allow users to log in securely.  

2. **Dashboard**  
   - FWMP shall display available food contributions as cards.  
   - FWMP shall allow users to filter and view food categories.  

3. **Food Contribution Management**  
   - Contributors can log new food items with title, category, description, quantity, pickup window, and location.  
   - Beneficiaries can claim food items.  

4. **User Profile**  
   - FWMP shall allow users to update name, email, address, and user type.  

5. **Notifications**  
   - FWMP shall notify contributors when their contributions are claimed.  

6. **Admin Features**  
   - Admins can monitor logs and manage users.  

---

## 3. Non-Functional Requirements  

- **Performance:** Handle 500+ concurrent users.  
- **Security:** Passwords hashed, all communications encrypted (TLS 1.3).  
- **Reliability:** 99.9% uptime.  
- **Usability:** Simple, intuitive UI with minimal learning curve.  
- **Maintainability:** Modular architecture, use of design patterns (minimum 7).  
- **Scalability:** Elastic scaling on AWS.  
- **Accessibility:** Compliant with WCAG 2.1 guidelines.  

---

## 4. Safety Considerations  

- Food quality and safety disclaimers must be displayed.  
- Liability disclaimer: FWMP is not responsible for food safety post-collection.  
- Prevent fraudulent activity with account verification.  

---

## 5. Risk Management  

| Risk | Impact | Likelihood | Mitigation |
|------|--------|------------|------------|
| Fake accounts | High | Medium | Verification & admin approval |
| Data breaches | Critical | Medium | Strong encryption & secure cloud policies |
| Food safety concerns | High | High | Display disclaimers, allow reviews/ratings |
| Scope creep | Medium | Medium | Stick to assessment-defined scope |

---

## 6. System Diagrams  

### 6.1 Use Case Diagram  
Actors: Contributor, Beneficiary, Admin  
Use cases: Login, Register, Log Food, Claim Food, Manage Profile, Manage Users.  

![Use Case Diagram](use_case_diagram.png)  

### 6.2 System Architecture Diagram  
High-level architecture showing:  
- **Frontend:** React web app.  
- **Backend:** Node.js/Express with design patterns.  
- **Database:** AWS RDS (MySQL/PostgreSQL).  
- **Cloud Deployment:** AWS EC2 + CI/CD pipeline.  

*(Insert architecture.png here)*  

### 6.3 Data Flow Diagram (Level 0)  
User → FWMP App → Database → Notifications/Reports.  

*(Insert dataflow.png here)*  

---

## 7. Wireframes (Low Fidelity)  

From Figma prototype:  
- **Login Page**  
- **Register Page**  
- **Home/Dashboard**  
- **Log Food Contribution Form**  
- **User Profile**  

[*(Link to Figma)*  ](https://www.figma.com/design/4igSbs1J3N2pNaDe6gTHLD/IFN636A2?node-id=0-1&t=IPoijwJdJ0kqSnAP-1)

---

## 8. Conclusion  

The FWMP SRS establishes the foundation for developing a socially impactful system. It ensures clarity of purpose, aligns stakeholders, and minimizes risks by defining scope, requirements, and architecture early. This document, combined with UI wireframes and diagrams, provides a comprehensive roadmap for the implementation phase.  
