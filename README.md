# Distributed-Entreprise-Software-Development
### Review and analyse the case study (Sprint 0)

Producers within the Bristol Regional Food Network consist of forty local SMEs (small-to-medium enterprise) with varying levels of technical expertise, going from those using basic email ordering to others with a limited social media presence. They depend a lot on the marketplace platform that provides them a highly intuitive interfaces to list their products, update seasonal inventory, and track orders without requiring them to have an advanced technical training. Operationally, producers depend on the platform to guarantee a minimum 48-hour order preparation lead time and rely on the automated financial systems to distribute weekly payment settlements with clear audit trails for accounting. For specific product listings, they also depend on simulated external verification services to validate their organic certification claims. 

Customers are categorised into three distinct categories: young professionals and families lacking time to visit multiple farms, community groups requiring consistent local suppliers, and independent restaurants or cafés wanting to reduce the administrative overhead of sourcing from multiple SMEs. These customers depend on the platform's ability to aggregate products into seamless multi-vendor orders, allowing them to browse by category and view crucial data such as harvest dates and farm origins. Furthermore, they depend on the system's traceability capabilities to receive rapid notifications in the event of food-safety concerns, such as undeclared allergens or contamination. 

Marketplace Administrators are responsible for maintaining the overarching network, managing community features like surplus produce discounts, and investigating potential food quality incidents. They depend on the producers to supply accurate listing data and respond promptly to safety inquiries. Technically, the administrators depend on the seamless integration of a simulated external payment service to process all single and multi-vendor transactions, correctly distribute funds to the respective producers, and automatically extract the platform's 5% network commission in compliance with financial regulations. 


### Analysis of major business process and organisational responsibilities (Sprint 1)
1.	Major business processes
- Producer Listings (Background Processing): Producers add products and organic certifications to the platform. We verify these certifications using background message queues, so the application does not freeze for the user if the external verification service goes offline. 
-	Multi-Vendor Checkout: Customers buy items from several different producers in a single basket. We use the "Saga pattern" to manage this complex transaction across multiple databases. If a payment fails, this pattern ensures all reserved stock is safely and automatically returned to the correct producers. 
-	Payments (Safe Retries): The system connects to a test payment gateway. To handle sudden network drops, it’s going to use smart retry mechanisms (exponential backoff and idempotent APIs) to try the connection again without accidentally charging the customer twice. 
-	Quality Assurance (Traceability): If a food safety issue occurs, the system must instantly identify who supplied the food and who bought it. We use a highly connected database structure to quickly trace the links between customers, orders, and producers during an emergency. 
-	Community Features: The platform calculates delivery distances (food miles) using postcodes and manages discounts on leftover produce to reduce overall food waste. 
2.	Organisational Responsibilities and Key Actors
 	
The socio-technical ecosystem of the marketplace relies on distinct actors, each with defined responsibilities and system interactions. 
Internal Actors (Platform Users)
-	Producers (SMEs): Responsible for maintaining accurate product listings, updating seasonal inventory, and preparing orders within the required 48-hour lead time. As their technical literacy varies, they require intuitive interfaces and rely on the system to provide weekly financial settlements and tax-compliant audit trails. 
-	Customers (Professionals, Families, Community Groups, Restaurants): Responsible for confirming delivery/collection arrangements during multi-vendor checkouts and authorising payments. They may also initiate food quality incident reports. 
-	Marketplace Administrators: Authorised representatives who oversee platform operations. They are responsible for reviewing escalated quality incidents, deciding whether to close or further escalate issues, and ensuring overall platform compliance with data protection and financial regulations. 
External Actors (Third-Party Services)
-	External Payment Service (Simulated): Responsible for authorising customer transactions and providing status callbacks (success/declined) to the marketplace. 
-	Organic Certification Verification Service: An external registry queried by the marketplace to validate producer claims regarding organic status before publishing a product listing.



