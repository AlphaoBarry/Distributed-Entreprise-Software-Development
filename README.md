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

## Identification and Scoping of the Two Major Functionalities

Two major functionalities were selected from Use Case 1 (Producer Product Listing and Inventory Management) for detailed operational modelling and Camunda automation. Both are scoped below.

### Functionality 1: Product Listing and Validation

**Purpose:** Allow a registered producer to list a new product with accurate, validated information, including any organic claim, so that it can be published for customers.

**Business goals supported:** Simple product listing for producers with varied technical skill; trustworthy food information for customers (allergens, organic status, best-before date, farm origin).

| Aspect | Scope |
|--------|-------|
| **Actors** | Producer (initiates); Marketplace administrator (manual review); Organic certification service (external or simulated); Marketplace system (validation and publishing) |
| **Trigger** | A registered producer chooses to add a new product |
| **In scope** | Product submission form (name, description, category, price, quantity, availability period, farm origin); optional details (harvest date, allergens, organic certification, best-before date); validation of mandatory and invalid fields with a correction loop; organic certification check; fallback when the service is unavailable or the check fails; publication of the validated product |
| **Out of scope** | Customer browsing and search; ordering and payment; integration with a real certification body (a mock service is used) |
| **Key decisions** | Is all mandatory data present and valid? Is an organic claim made? Was the certificate verified? |

**Main flow**

1.  The producer submits the product form.
2.  The system validates mandatory and format rules.
3.  If an organic claim is made, the system verifies the certificate.
4.  When all checks pass, the product is published and becomes available to customers.

**Alternative and exception paths**

*   Missing or invalid data: the producer is asked to correct and resubmit.
*   Certification service unavailable: retry, then route to an administrator for manual review or save as a draft.
*   Certification fails: the organic claim is rejected, and the producer may amend or remove it.

**Planned Camunda elements:** user task with Camunda Form (producer submission); service task with retries (certification check); exclusive gateways (validation and verification outcomes); error or timer boundary event (unavailable service); user task with Form (administrator review); process variables for product data and verification status.

**Supporting services:** mock organic certification service (REST endpoint); product data store.

### Functionality 2: Inventory and Seasonal Availability Management

**Purpose:** Keep each product's availability accurate by updating stock and season information, and by making products unavailable or available again automatically according to business rules.
## Identification and Scoping of the Two Major Functionalities

Two major functionalities were selected from Use Case 1 (Producer Product Listing and Inventory Management) for detailed operational modelling and Camunda automation. Both are scoped below. The scope is a proposal, subject to agreement with the module team before detailed implementation begins.

### Functionality 1: Product Listing and Validation

**Purpose:** Allow a registered producer to list a new product with accurate, validated information, including any organic claim, so that it can be published for customers.

**Business goals supported:** Simple product listing for producers with varied technical skill; trustworthy food information for customers (allergens, organic status, best-before date, farm origin).

| Aspect | Scope |
|--------|-------|
| **Actors** | Producer (initiates); Marketplace administrator (manual review); Organic certification service (external or simulated); Marketplace system (validation and publishing) |
| **Trigger** | A registered producer chooses to add a new product |
| **In scope** | Product submission form (name, description, category, price, quantity, availability period, farm origin); optional details (harvest date, allergens, organic certification, best-before date); validation of mandatory and invalid fields with a correction loop; organic certification check; fallback when the service is unavailable or the check fails; publication of the validated product |
| **Out of scope** | Customer browsing and search; ordering and payment; integration with a real certification body (a mock service is used) |
| **Key decisions** | Is all mandatory data present and valid? Is an organic claim made? Was the certificate verified? |

**Main flow**

1.  The producer submits the product form.
2.  The system validates mandatory and format rules.
3.  If an organic claim is made, the system verifies the certificate.
4.  When all checks pass, the product is published and becomes available to customers.

**Alternative and exception paths**

*   Missing or invalid data: the producer is asked to correct and resubmit.
*   Certification service unavailable: retry, then route to an administrator for manual review or save as a draft.
*   Certification fails: the organic claim is rejected, and the producer may amend or remove it.

**Planned Camunda elements:** user task with Camunda Form (producer submission); service task with retries (certification check); exclusive gateways (validation and verification outcomes); error or timer boundary event (unavailable service); user task with Form (administrator review); process variables for product data and verification status.

**Supporting services:** mock organic certification service (REST endpoint); product data store.

### Functionality 2: Inventory and Seasonal Availability Management

**Purpose:** Keep each product's availability accurate by updating stock and season information, and by making products unavailable or available again automatically according to business rules.

**Business goals supported:** Producers can manage frequent seasonal changes without technical expertise; customers only see products that can actually be bought.

| Aspect | Scope |
|--------|-------|
| **Actors** | Producer (initiates); Marketplace system (applies availability rules); Notification service (optional, if agreed) |
| **Trigger** | A producer updates quantity or availability period, or stock changes through another event |
| **In scope** | Form for updating quantity and seasonal availability; validation of updates (for example no negative quantity, valid date range); automatic unavailability at zero stock; automatic restoration on replenishment within the season; recording of availability status for use by other parts of the platform |
| **Out of scope** | Reduction of stock through customer orders (belongs to ordering, but the process should expose a way to be called later); surplus discounting |
| **Key decisions** | Is the update valid? Is stock zero? Is the product within its availability period? |

**Main flow**

1.  The producer submits a stock or season update.
2.  The system validates and saves the update.
3.  The system evaluates availability: stock above zero and the current date within the season.
4.  The product status is set to available or unavailable accordingly.

**Alternative and exception paths**

*   Invalid update: rejected with a message to the producer.
*   Restock outside the season: the product remains unavailable.
*   Season dates changed on a live product: availability is re-evaluated.
*   Possible extensions, if agreed: producer notification when stock reaches zero, and a scheduled expiry at season end.

**Planned Camunda elements:** user task with Camunda Form (stock and season update); business rule logic (DMN decision table or gateway conditions) for the availability rule; service task to update product status; timer event if the season-end extension is agreed; process variables (`quantity`, `seasonStart`, `seasonEnd`, `availabilityStatus`).

**Supporting services:** product and inventory service (shared with Functionality 1); notification service, if the extension is agreed.

### Relationship Between the Two Functionalities

Functionality 1 creates and publishes a product. Functionality 2 keeps that product's availability accurate for as long as it is on sale. Both operate on the same product data, which supports reuse and integration in Task 2.

### Traceability

Links to the strategic BPMN process names and i* elements (producer goals, softgoals and dependencies on the certification service) will be added once those models are drafted.

### Questions for the Module Team

1.  Are the two functionalities sufficiently substantial, with both drawn from Use Case 1?
2.  Is a simulated certification service acceptable for the external service requirement?
3.  Are small extensions to Functionality 2 acceptable (zero-stock notification, season-end timer)?
4.  Which Camunda version should be targeted?
**Business goals supported:** Producers can manage frequent seasonal changes without technical expertise; customers only see products that can actually be bought.

| Aspect | Scope |
|--------|-------|
| **Actors** | Producer (initiates); Marketplace system (applies availability rules); Notification service (optional, if agreed) |
| **Trigger** | A producer updates quantity or availability period, or stock changes through another event |
| **In scope** | Form for updating quantity and seasonal availability; validation of updates (for example no negative quantity, valid date range); automatic unavailability at zero stock; automatic restoration on replenishment within the season; recording of availability status for use by other parts of the platform |
| **Out of scope** | Reduction of stock through customer orders (belongs to ordering, but the process should expose a way to be called later); surplus discounting |
| **Key decisions** | Is the update valid? Is stock zero? Is the product within its availability period? |

**Main flow**

1.  The producer submits a stock or season update.
2.  The system validates and saves the update.
3.  The system evaluates availability: stock above zero and the current date within the season.
4.  The product status is set to available or unavailable accordingly.

**Alternative and exception paths**

*   Invalid update: rejected with a message to the producer.
*   Restock outside the season: the product remains unavailable.
*   Season dates changed on a live product: availability is re-evaluated.
*   Possible extensions, if agreed: producer notification when stock reaches zero, and a scheduled expiry at season end.

**Planned Camunda elements:** user task with Camunda Form (stock and season update); business rule logic (DMN decision table or gateway conditions) for the availability rule; service task to update product status; timer event if the season-end extension is agreed; process variables (`quantity`, `seasonStart`, `seasonEnd`, `availabilityStatus`).

**Supporting services:** product and inventory service (shared with Functionality 1); notification service, if the extension is agreed.

### Relationship Between the Two Functionalities

Functionality 1 creates and publishes a product. Functionality 2 keeps that product's availability accurate for as long as it is on sale. Both operate on the same product data, which supports reuse and integration in Task 2.
