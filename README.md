# Distributed-Entreprise-Software-Development
Group Project

# Bristol Regional Food Network - Digital Marketplace

## Project Management Approach

Our team is going to use an **Agile Scrum framework** managed via **GitHub Projects** to coordinate the development of the Bristol Regional Food Network digital marketplace. This approach will allow us to have a clear traceability between stakeholder requirements, modelling, and executable Camunda implementations.

### Sprint Structure
Our development life-cycle is divided into four sprints, aligning with the assessment milestones:

*   **Sprint 0:** Group Formation and Preparation. Focuses on case study analysis, repository setup, establishing communication channels, and defining the initial functional scope.
*   **Sprint 1:** Strategic Process Analysis and Project Setup. Focuses on the strategic BPMN model, functional scoping agreement, and product backlog creation.
*   **Sprint 2:** Socio-Technical and Operational Modelling. Focuses on i* SD/SR models, operational BPMN, and initial Camunda executable processes.
*   **Sprint 3:** Final Implementation. Focuses on end-to-end execution, Camunda Forms, service-task integration, and exception handling.

### Roles and Responsibilities
To ensure equal distribution of the work and an accurate Contribution Matrix, we will attempt to divide responsabilities as follows:

*   **Scrum Master / Repo Manager:** Coordinates weekly stand-ups, manages pull request merges, and ensures the GitHub Project board remains up to date.
*   **Lead Modeller:** Drives the development of the i* Strategic Dependency, Strategic Rationale, and BPMN models.
*   **Camunda Engineer(s):** Leads the implementation of executable business processes, user tasks, and Camunda Forms.
*   **Integration Developer:** Focuses on the implementation of automated service tasks, process variables, and business logic.

### Quality Assurance & Version Control
All assessed artefacts are maintained within this repository. Work is conducted on feature branches and merged into the main branch only upon peer review. Task tickets on the GitHub Projects board are directly linked to commits to provide a clear, auditable record of individual contributions. The version available in this repository at the sprint submission point will be used as our submitted evidence.

### Stand Up 1 | 14/10/26
### Sprint 0 Initial Deliverables
During Sprint 0, our group has completed the following preparation tasks:
1.  **Group Formation:** Established a group of 4 members and identified roles.
2.  **Repository Setup:** Created this shared repository and established our project management approach using GitHub Projects.
3.  **Case Study Analysis:** Reviewed the Bristol Regional Food Network case study and began identifying principal stakeholders (e.g., young professionals, community groups, producers).
4.  **Functional Scoping:** Identified initial candidate major functionalities for review in Sprint 1.

## Candidate Major Functionalities

Ten candidate functionalities were identified from the Bristol Regional Food Network case study and Use Case 1 (Producer Product Listing and Inventory Management). Each was screened, which requires functionalities that demonstrate an end-to-end process, user interaction, automated processing, business decisions, external service interaction, and alternative and exception flows.

### Screening Outcome

The ten candidates were grouped into five outcomes:

*   **Shortlisted (2):** Product listing and validation; Inventory and seasonal availability management.
*   **Merged into the shortlisted pair (2):** Organic certification verification (into product listing) and seasonal product updates (into inventory management).
*   **Backup option (1):** Surplus produce and last-minute discounts.
*   **Out of scope, belonging to Use Cases 2 and 3 (3):** Multi-vendor ordering and payment, weekly producer settlement, and food quality incident and traceability.
*   **Rejected (2):** Food miles calculation, and recipes and farm stories. Both contain limited process logic and few exception paths.

### Proposed Major Functionalities

1.  **Product Listing and Validation:** A producer submits product details, the system validates them, verifies any organic claim through an external or simulated certification service, and publishes the product. Exception paths include invalid data, an unavailable certification service, and failed verification.
2.  **Inventory and Seasonal Availability Management:** A producer updates stock and seasonal availability. A product becomes unavailable automatically when stock reaches zero, and becomes available again on replenishment if it is still within its season. Exception paths include invalid updates and restocks outside the season.

### Rationale

Both functionalities originate directly from Use Case 1, which keeps the project scope clear and justifiable. Together they cover Camunda user tasks and Forms, service tasks, business rules, gateways, boundary events, and error handling. 

### Next Steps

*   Agree the two proposed functionalities with our tutor before detailed implementation begins.
*   Confirm whether small extensions (such as a zero-stock notification or surplus discounts) are acceptable if the second functionality needs more depth.
*   Link both functionalities to the strategic BPMN and i* models once these are drafted.