---
tags:
  - bsa
author:
  - jacgit18
Status: 
Started: 2023-12-12
EditDate: 
Relates: "[[Attributes of Requirements & User Stories]]"
---

![[Requirement life cycle.svg]]

# Business Requirements 
Business requirements which are drivers for user stories and all this work refer to the high-level needs/wants and objectives of the organization or stakeholders that drive the development of a product or service.

These requirements are typically contained inside within [[User Stories#**Themes In-Depth** | Themes]] which represent a higher level of abstraction that allows teams to understand the broader context and purpose of the work they are doing.

Each theme may encompass multiple business requirements that collectively contribute to achieving a specific business goal.

The identification and prioritization of themes are crucial in guiding the development team to work on the most valuable and impactful features or improvements.

## **Translating Business Needs to Technical Requirements:**

### **Identify and Consider:**
   - Organization position and its impact on structure.
   - Priority of needs and wants.
   - Applicability of requirements, justifying their value, complexity, cost, and legal aspects.
   - External constraints, geopolitical factors, regulations, and legal considerations.
   - Business as usual (BAU) operations.
   - Alternative actions, potential risks, and hurdles.
   - Requirements must encompass specific conditions, focus on a defined subject, articulate vital actions, adhere to established business rules, and culminate in an outcome that aligns seamlessly with business objectives.

### **Functional and Non-Functional Requirements:**
   - Functional requirements describe how the system must work.
   - Non-functional requirements specify how the system should perform.


### **Understanding Stakeholder Needs:**
**Needs of Stake Holders drives user wants
>[!note]
> Determine stakeholders' incentives, influences, and motivations, and subsequently, categorize and prioritize them. When assessing these factors, consider that smaller issues may require fewer needs to define. Conversely, in scenarios involving the rebuilding of functionality, as seen with Tracflo, or the creation of something entirely new, the number of needs and scope may significantly expand.
#### Needs + Wants + Data = Business Requirements:
   - Business needs arise from factors like customer complaints, market changes, and process inefficiencies.
   - Stakeholder incentives, influences, and motivations should be identified, categorized, and prioritized.
   - Consider the scope, organizational culture, and established information when determining user wants.
   - Assess data relevance, quality, volume, availability, and accessibility.

### Data Considerations

- **Data Relevance:** Assess the pertinence of the data to the project objectives.
- **Data Quality:** Evaluate the accuracy and reliability of the available data.
- **Data Volume:** Determine the quantity of data required for the project.
- **Data Availability:** Ensure that necessary data is accessible when needed.
- **Data Accessibility (Format):** Consider the format in which the data is stored or presented.

**Additional Considerations:**
- **Data Types:** Distinguish between database (db) data and documentation.
- **Time Period:** Clarify the timeframe for data availability, especially with sensitive information subject to regulatory compliance.
- **Applicability:** Evaluate the relevance of the data and the specific information it contains.

### **Assumptions and Constraints:**
   - **Assumptions:** Identify, document, confirm accuracy, and manage risks associated with unproven factors.
   - **Constraints:** Recognize impositions or restrictions on the project, including business, technical, and external constraints.
   - **Triple Constraint:** Consider the interplay of budget, time, and scope in project management.

## Resolving Requirement Conflicts

Address conflicts effectively through various techniques:

1. **Multivoting:**
   - Utilize multivoting to prioritize conflicting requirements, allowing team members to collectively express preferences and reach a consensus.

2. **Weighted Ranking Voting:**
   - Apply weighted ranking voting to assign priority levels to conflicting requirements based on their relative significance.

3. **Delphi Technique:**
   - Implement the Delphi technique by creating a survey leveraging the expertise of relevant stakeholders. Aggregate and analyze the results to inform decision-making.

4. **Expert Review of Survey Results:**
   - During the review of survey outcomes, involve experts to assess and validate the results, ensuring a comprehensive and well-informed decision-making process.

## Requirement Life Cycle 

The project life cycle encompasses several key stages: Identification, Definition, Verification, Validation, Approval, and Implementation. This cycle allows for iteration, permitting a return to the Definition stage until approval is secured. The process may loop back from the Verified stage to Implementation and ultimately culminate in retirement.

It's crucial to note that change is not automatically implemented, emphasizing the non-linear nature of the life cycle.

**Decision-Making and Stakeholder Roles**

Determining who makes decisions and identifying the primary customer or focus of need are pivotal aspects. The RACI framework, representing Responsible, Accountable, Consulted, and Informed, aids in clarifying responsibilities for creating, delivering, reviewing, and validating. 

- **Responsible:** Those tasked with executing specific actions.
- **Accountable:** The individual ultimately answerable for the success or failure of a task or decision.
- **Consulted:** Those whose input is sought before making a decision or taking action.
- **Informed:** Those kept in the loop about decisions or actions but are not directly involved.

Additionally, recognizing that a conversation can serve as another form of traceability, fostering communication and understanding across stakeholders. This ensures a comprehensive approach to decision-making and project progression.




