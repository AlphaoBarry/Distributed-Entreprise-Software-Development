# Stakeholder Analysis

## Introduction

This stakeholder analysis identifies the main stakeholders involved in the Bristol Regional Food Network Digital Marketplace, focusing on Use Case 1: Producer Product and Inventory Management.

## Stakeholder Identification

| Stakeholder | Needs and Expectations | Responsibilities | Concerns |
|---|---|---|---|
| Producers | Need a simple way to list products, enter product details, set prices, and update stock and seasonal availability. | Submit accurate product information and maintain stock details. | Incorrect listings, complicated forms, difficulty updating stock, and products remaining available when out of stock. |
| Customers | Need accurate product descriptions, prices, stock availability, farm origin, harvest dates, allergen information, and best-before dates where relevant. | Browse the marketplace and use product information to make purchasing decisions. | Incorrect or missing product information, unavailable products being displayed, and unreliable availability information. |
| Marketplace Administrators | Need reliable and accurate product listings and a marketplace that follows its listing requirements. | Potentially oversee marketplace listings and help resolve issues; responsibilities to be confirmed. | Invalid product information, inaccurate stock records, and difficulty resolving listing or verification issues. |
| Organic Certification Verification Service | Needs the relevant certification information to verify an organic certification claim. | Return a verification result when requested. | The verification request may fail, the service may be unavailable, or the certification claim may not be verified. |
| Marketplace System / Application | Needs valid product information, accurate inventory records, and successful validation before publishing products. | Validate information, publish products, update availability, and handle errors. | Missing or invalid information, failed validation, incorrect stock updates, and verification service failures. |
| Development / Technical Team | Needs clear requirements for product listing, validation, inventory updates, and certification verification. | Develop, integrate, and test the product listing functionality. | Unclear requirements, integration problems, and failure to handle errors correctly. |

## Stakeholder Concerns and Dependencies

- Producers depend on the marketplace system to publish and update product listings and update stock and seasonal availability.
- Customers depend on producers providing accurate and up-to-date product information.
- The marketplace system depends on valid information being submitted before a product can be published.
- The marketplace system depends on the certification verification service when a producer claims organic certification.
- Producers need the system to make products unavailable automatically when stock reaches zero.
- Producers depend on the system to make products available again when stock is replenished, provided the product is still within its seasonal availability period.
- The system must handle missing or invalid information by asking producers to correct it.
- The system must account for verification failures or an unavailable certification service.
- The development team depends on clear stakeholder requirements to implement and test the process correctly.
