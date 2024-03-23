# Food Waste Reduction Platform (FWRP)

## 1. Version History

- **Version:** 1.0
- **Date:** March 22, 2024
- **Authors:**
  - Elisha Kalyan
  - Armando Mavova Bazeyidio
  - Deepanshu
  - AaniqAllaudin

## 2. Introduction

### About the System

The Food Waste Reduction Platform (FWRP) is a web-based application designed to reduce food waste by facilitating connections among food retailers, consumers, and charitable organizations. Its core functionalities include user registration, inventory management, and the listing and claiming of surplus food.

### Purpose of the Document

This document outlines the development plan of the FWRP, providing a detailed blueprint for its structure, design considerations, and functional requirements.

## 3. Targeted Audience

- **Retailers:** Businesses with surplus food inventory.
- **Consumers:** Individuals seeking discounted food options.
- **Charitable Organizations:** Entities looking to distribute surplus food to those in need.

## 4. Scope

### In Scope

- Development of a web-based platform.
- Features for user registration, authentication, and inventory management.
- Notification system for surplus food alerts.

### Out of Scope

- Handling of real money transactions.
- Integration with external logistics services.
- Real-time chat features.

## 5. Application Architecture

The FWRP utilizes a three-tier architecture, consisting of:
- **Presentation Layer:** For UI and user interactions.
- **Business Layer:** Contains core functionalities and business logic.
- **Database Layer:** Manages data storage and retrieval.

## 6. Business Architecture

![2](https://github.com/Elisha-777/FINAL-PROJECT-CST-8288-/assets/156712128/4f258830-2d23-4e4e-a279-c855b3bf98e0)

### Retailer Use Cases

- Manage Inventory: Add, update, or remove items.
- Identify and list surplus food items for donation or sale.

### Charitable Organization Use Cases

- Claim food items listed for donation.
- Update retailer inventory once a food item is claimed.

### Consumer Use Cases

- Purchase surplus food items at discounted rates.
- Update retailer inventory upon purchase.

## 7. Detailed Design

![1](https://github.com/Elisha-777/FINAL-PROJECT-CST-8288-/assets/156712128/45d5d96a-573b-4e16-8905-cb89d5f47825)

Key classes include:
- **User:** Base class for system users.
- **Retailer:** Manages inventory and lists surplus food.
- **Charitable Organization:** Claims surplus food items for distribution.
- **Consumer:** Purchases surplus food items.
- **InventoryItem, ClaimedItem, PurchaseItem:** Represent various item states in the system.

![3](https://github.com/Elisha-777/FINAL-PROJECT-CST-8288-/assets/156712128/e744204e-28cf-4871-9148-b96fd370de04)

## 8. Database

### Logical Model

- **Users Table:** Stores user information.
- **Inventory Table:** Tracks food items, quantities, and expiration dates.

### Physical Model
![5](https://github.com/Elisha-777/FINAL-PROJECT-CST-8288-/assets/156712128/6a3b05cb-36b0-4360-9700-9e8e6b036f3b)

# Food Waste Reduction Platform (FWRP) - Database Structure

The Food Waste Reduction Platform (FWRP) aims to minimize food waste by facilitating the efficient redistribution of surplus food items from retailers to consumers and charitable organizations. This document outlines the logical data model of FWRP, detailing the database's structural organization, including entities, attributes, and relationships critical to the system's data requirements.

## Entities and Attributes

- **Users**
  - Represents individuals interacting with the platform.
  - Attributes: user ID, name, email, password, user type (retailer, consumer, charitable organization).

- **Retailers**
  - Represents businesses or entities managing inventory.
  - Foreign key: Users table reference.
  - Attributes: Included in the Users entity.

- **Surplus Food**
  - Represents food items listed by retailers as surplus.
  - Attributes: surplus ID, retailer ID, item name, quantity, expiration date, donation/sale status.

- **Consumers**
  - Represents individuals browsing and purchasing items.
  - Foreign key: Users table reference.
  - Attributes: Included in the Users entity.

- **Charitable Organizations**
  - Represents organizations claiming surplus food items.
  - Foreign key: Users table reference.
  - Attributes: Included in the Users entity.

- **Inventory**
  - Stores detailed information about inventory managed by retailers.
  - Attributes: item ID, retailer ID, item name, quantity, expiration date.

- **Subscriptions**
  - Represents user subscriptions for surplus food alerts.
  - Attributes: subscription ID, user ID, location, communication method, food preferences.

## Relationships

1. **Users - Retailers, Consumers, Charitable Organizations**
   - One-to-many relationship between users and their roles.

2. **Retailers - Surplus Food, Inventory**
   - Retailers manage surplus food items and inventory.

3. **Charitable Organizations - Surplus Food**
   - Charitable organizations claim surplus food items.

4. **Users - Subscriptions**
   - Users subscribe to surplus food alerts.

## Key Aspects

- **Normalization**
  - The model follows normalization principles to minimize data redundancy and ensure data integrity.

- **Referential Integrity**
  - Foreign key constraints maintain data consistency and prevent orphaned records.

The logical data model of FWRP facilitates effective data management and system operation, supporting the platform's mission to reduce food waste through improved distribution mechanisms.
