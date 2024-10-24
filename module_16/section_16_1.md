# 16.1. Defining the Project Scope

## Introduction

The first step in the capstone project is defining the project scope. A well-defined project scope ensures that you have a clear understanding of the problem you are addressing, the goals of the system, and the constraints you will operate under. This step is critical because it sets the foundation for the entire project, guiding your design decisions and ensuring that the system meets the necessary requirements.

In this section, we will outline how to define the scope of your project by clearly stating the problem, identifying the system's objectives, understanding the constraints, and listing key requirements.

---

## 1. Defining the Problem

### 1.1. **What is the Problem You’re Solving?**

- **What It Is:** Clearly define the core problem that your system is intended to address. This can be a business challenge, a user need, or a technical problem.
- **Why It Matters:** Understanding the problem is the first step to creating a solution. A well-defined problem statement helps you stay focused and ensures that your design choices are aligned with the system's purpose.

**Best Practices:**
- Focus on the real-world challenges you are solving (e.g., handling high traffic for a live streaming platform, managing large-scale transactions in e-commerce, or ensuring low-latency data access in a global application).
- Keep the problem statement concise but comprehensive, ensuring that all key aspects of the challenge are addressed.

### Example:
An e-commerce platform struggles with scaling during peak traffic events, resulting in slow response times and transaction failures. The problem: how to design a scalable, resilient architecture that can handle significant traffic surges during sales events without performance degradation.

---

## 2. Identifying the System Objectives

### 2.1. **What Does the System Need to Achieve?**

- **What It Is:** Define the primary objectives of the system. These objectives should directly address the problem and outline what success looks like. They should cover functional and non-functional requirements (e.g., performance, reliability, user experience).
- **Why It Matters:** Clear objectives guide the system design, ensuring that your architecture is optimized to meet key goals.

**Best Practices:**
- Focus on both **functional requirements** (e.g., users can browse products, make transactions, and receive real-time notifications) and **non-functional requirements** (e.g., the system must scale to 1 million users, ensure 99.99% uptime, and provide sub-second response times).
- Prioritize the most critical objectives, especially those that align with scalability, reliability, and performance.

### Example:
The system should support up to 1 million concurrent users, ensure that transaction processing is completed in less than 2 seconds, and maintain 99.99% uptime during peak events.

---

## 3. Understanding Constraints

### 3.1. **What Constraints Affect the System?**

- **What It Is:** Constraints are the limitations or restrictions that will shape your design. These can include time, budget, technology choices, or specific business rules.
- **Why It Matters:** Understanding constraints allows you to make realistic design decisions and ensure that your system fits within the available resources and limitations.

**Best Practices:**
- Identify both **technical constraints** (e.g., the system must use a specific cloud provider or database technology) and **business constraints** (e.g., the system must be built within a 6-month time frame or with a limited budget).
- Consider potential trade-offs that might be necessary to stay within the defined constraints, such as sacrificing certain features for improved scalability.

### Example:
The system must be built using AWS infrastructure and integrate with existing payment services. Additionally, it must be launched within 6 months and operate within a budget of $200,000.

---

## 4. Listing Key Requirements

### 4.1. **What are the Key Requirements?**

- **What It Is:** Key requirements outline the specific functionality and performance criteria that the system must meet. These should be measurable and clearly defined to guide the design process.
- **Why It Matters:** Clearly defined requirements ensure that the system will meet its intended goals and provide a framework for evaluating the success of the project.

**Best Practices:**
- Break down the requirements into functional (what the system should do) and non-functional (how the system should behave) categories.
- Ensure that the requirements are measurable, such as specifying exact response times, throughput, or availability targets.

### Example:
- **Functional Requirements:**
  - Users should be able to browse products and complete transactions.
  - The system should send real-time notifications for order updates.
  
- **Non-Functional Requirements:**
  - The system should maintain sub-500ms response times for 90% of user requests.
  - It should be able to scale dynamically during high-traffic events (e.g., sales promotions).
  - Maintain 99.99% uptime and automatic failover capability.

---

## 5. Aligning Scope with Stakeholder Expectations

### 5.1. **Who Are the Key Stakeholders?**

- **What It Is:** Identify the key stakeholders who will benefit from or rely on the system (e.g., end users, business teams, technical teams). Understanding their expectations and aligning them with the system scope is critical for project success.
- **Why It Matters:** Ensuring that the project scope aligns with stakeholder needs helps prevent miscommunication and ensures that the system delivers value to its intended audience.

**Best Practices:**
- Engage with stakeholders early in the process to understand their requirements, priorities, and pain points.
- Continuously revisit the project scope throughout the design process to ensure it remains aligned with stakeholder expectations.

### Example:
For an e-commerce platform, key stakeholders include the marketing team (who want a reliable system during promotions), developers (who need a scalable architecture), and end users (who expect fast and seamless shopping experiences).

---

## Conclusion

Defining the project scope is a foundational step in the capstone project, providing clarity on the problem you're addressing, the system's objectives, and the constraints you must operate within. A well-defined scope ensures that your system design is aligned with the goals and requirements of the project and sets the stage for a successful system architecture. By outlining key requirements, understanding constraints, and aligning with stakeholder expectations, you'll be better prepared to design a system that meets its objectives.

---

[Next: 16.2. High-Level Design Proposal](./section_16_2.md)
