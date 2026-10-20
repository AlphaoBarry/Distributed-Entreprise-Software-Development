

# Establish an initial product backlog. 

## Objective 

To identify and prioritise  the initial system requirement for the producers Product Listing and inventory Management use Case.
With the support of the backlog, this will help the team understand what the system needs to operate and organise the assignments for future sprints.

## Initial Product Backlog 

| ID   | User Story | Priority |
|------|------------|----------|
| PB01 | As a producer, I want to add new products so that customers can purchase them. | Must |
| PB02 | As a producer, I want a system to validate my product information in the event incorrect details are identified. | Must |
| PB03 | As a producer, I want invalid information to be corrected so that my product can be published. | Must |
| PB04 | As a customer, there must be a certification for organic products so that it is trustworthy. | Must |
| PB05 | As a producer, I want my verified products to be published so that customers can view them. | Must |
| PB06 | As a producer, I want my product quantity updated regularly so that stock information remains accurate. | Must |
| PB07 | As a customer, I want out-of-stock products to become unavailable so that I cannot order unavailable items. | Must |
| PB08 | As a producer, I want seasonal availability to update so that products are only sold during their available period. | Must |
| PB09 | As a producer, I want the system to manage certification verification failures so that my listing is not wrongly approved. | Must |
| PB10 | As a producer, I want replenished products to become available again when they are still in season. | Must |

## Example Acceptance Criteria

PB01- adding New Products
•	 With a registered producer enters a valid product information when they submit. 
The listing, then the system accepts it.

•	  In the scenario given mandatory information is missing, the producer submits the listing, then the systems requests corrections.

PB02 – Validating Product Information
•	Given the producer enters a product details, when the listing is submitted, the system will then check that all mandatory fields are established, and the information is in the correct order. 
•	Given information is identified, when validation is completed, it is then highlighted by the system showing the affected fields and requests corrections.	

PB03- Correcting invalid information.
•	Given the system Identifies incorrect product information when the producer submits the correct details for listing. Then the system identifies the updated information.

•	Given all correction are now valid, the listing is resubmitted and the product can continue to the next stage for the publication process.

PB04- Verifying Organic Certification

•	Given a producer listed a product as organic when the listing is submitted, the system requires valid certification or proof.

•	Given the verification confirms the certification is valid, the results are received and then the system records the certification as verified.
PB05- Publishing Verified Products
•	Given a product has passed the required information and certification checks. The producer will submit the listing for publication and the system will make the product visible to customers.

•	Given a product has not passed the required check, when the publication is attempted the system will be declined or prevent the listing  from being published.


PB06- Updating Inventory Quantities.

•	Given a producer updates a product stock quantity,  once the update is completed the system records the new quantity.

•	Given  a producer enters an invalid quantity, for example a negative number  the system will reject the update and request a valid quantity.

PB07- Out-Stock-Products
•	Given a product’s quantity reaches zero, when the inventory is updated. The product will automatically become unavailable for new orders. 

•	 Given stock is replenished within the seasonal available  period, when inventory is updated then the product becomes available again.

PB08- Managing Seasonal Availability
•	Given a producer enters a valid seasonal  start and end date. The date is saved and the system records the dates.

•	Given the current date is outside the product available season. The product then becomes unavailable for new orders.
PB09- Handling Certification Verification Failure

•	Given the external certification verification fails the systems records the failure and does not mark certification as verified.

•	Given certification verification cannot be completed, when the producer views the listing the system will display  pending or failed verification status.




PB10- Restoring availability after replenishment.

•	Given a product is out of stock but remains within its seasonal availability period, when the producer records a valid replenishment, the system updates the inventory quantity.

•	Given the replenished stock is greater than zero and all required checks are valid, of ethe inventory update is saved then product become available for new orders.


## Non-Functional Requirements 

 The listed non-functional requirements have been identified to ensure that the system operates reliably and accurately.

•	Security: Only authorized producers should have access to create, update, and manage their own product listings.

•	Data Accuracy: The system should ensure, product information certification and stock quantity are stored accurately.

•	Reliability: If the external certification service fails, the system should not approve the product automatically




## Stakeholders

 The following stakeholders are identified for the product listing and inventory Management  use case. 

| Stakeholder | Role |
|-------------|------|
| Producer | Producers are responsible for adding products, updating inventory, and providing certification details. |
| Customers | Customers view available products and rely on up-to-date product information and stock availability. |
| Marketplace Administrator | Oversees marketplace operations and manages listing issues. |
| External Certification Verification Service | Responsible for checking organic certification details and returning verified results to the system. |
| Application | The system that manages product listings, certification validation, inventory updates, and product availability. |

## Prioritisation 

MoSCoW  prioritisation has been used to identify the importance of each requirement.
The main requirement  is classified as “Must”. as they are the primary core functionality described in the selected use case.

These priorities may be studied  and refined during sprint planning. 




## Definition of Done
•	Initial requirements have been identified.
•	Requirements  have been written as user stories. 
•	Each Requirement has been prioritised.
•	Acceptance  criteria have been established for PB01-PB10
•	Non-Functional requirement has been identified.
•	Stakeholders have been identified. 
•	The initial backlog  will be reviewed and agreed upon by the group. 



