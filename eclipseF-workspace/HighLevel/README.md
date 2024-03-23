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
![Alt text](file:///C:/Users/ELISHA%20KALYAN/eclipseF-workspace/HighLevel/2.png "Optional title")

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
![Alt text](file:///C:/Users/ELISHA%20KALYAN/eclipseF-workspace/HighLevel/1.jpg "Optional title")

Key classes include:
- **User:** Base class for system users.
- **Retailer:** Manages inventory and lists surplus food.
- **Charitable Organization:** Claims surplus food items for distribution.
- **Consumer:** Purchases surplus food items.
- **InventoryItem, ClaimedItem, PurchaseItem:** Represent various item states in the system.
![Alt text](file:///C:/Users/ELISHA%20KALYAN/eclipseF-workspace/HighLevel/3.png "Optional title")

## 8. Database

### Logical Model

- **Users Table:** Stores user information.
- **Inventory Table:** Tracks food items, quantities, and expiration dates.

### Physical Model

```sql
CREATE TABLE Users (
    name VARCHAR(200),
    email VARCHAR(255) PRIMARY KEY,
    password VARCHAR(50),
    user_type VARCHAR(200)
);

CREATE TABLE Inventory (
    itemID INT PRIMARY KEY,
    quantity INT,
    expirationDate DATE,
    surplusIdentification BOOLEAN
);
![Alt text](file:///C:/Users/ELISHA%20KALYAN/eclipseF-workspace/HighLevel/5.png "Optional title")
