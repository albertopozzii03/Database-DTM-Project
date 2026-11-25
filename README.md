# Romagna Cavi – Relational Database Design Project

**Academic Project | Database Design | SQL | Supply Chain Management**

---

## Table of Contents

1. [Project Overview](#1-project-overview)
2. [Business Context](#2-business-context)
3. [Project Objectives](#3-project-objectives)
4. [Main Functional Areas](#4-main-functional-areas)
5. [Database Design Process](#5-database-design-process)
6. [Database Structure](#6-database-structure)
7. [Business Rules and Data Integrity](#7-business-rules-and-data-integrity)
8. [SQL Queries and Business Applications](#8-sql-queries-and-business-applications)
9. [Technologies and Technical Concepts](#9-technologies-and-technical-concepts)
10. [Project Team](#10-project-team)

---

## 1. Project Overview

This academic project focuses on the design of a relational database system for **Romagna Cavi**, a cable distribution company.

The objective was to design a structured database capable of supporting the company's main operational processes, covering the entire product lifecycle, from raw material procurement to finished product delivery.

The proposed database supports supplier management, inventory tracking, production traceability, customer order management and shipment operations.

The project follows a structured database design methodology, moving from business requirements analysis to conceptual modeling, relational schema definition and SQL query development.

## 2. Business Context

Romagna Cavi operates in the cable distribution sector and manages a supply chain involving suppliers, raw materials, manufactured products, customers and transport companies.

The database was designed around the following operational workflow:

1. **Procurement:** Supply orders are placed with suppliers to acquire raw materials.
2. **Inventory Management:** Received materials are classified by category and associated with warehouse locations.
3. **Production:** Raw materials are transformed into finished products, each identified by a unique serial number.
4. **Traceability:** The relationship between raw materials and finished products is maintained to support product tracking.
5. **Customer Orders:** Customer orders are registered and organized into individual order details.
6. **Shipping:** Packing lists are generated and associated with customers and transport companies.

## 3. Project Objectives

The main objectives of the database design were to:

- Organize the company's operational information within a structured relational database.
- Support the management of suppliers, procurement activities and raw materials.
- Improve inventory classification and warehouse tracking.
- Maintain traceability between raw materials and manufactured products.
- Support customer order registration and management.
- Organize packing lists and shipment information.
- Enable operational data retrieval through SQL queries.

## 4. Main Functional Areas

### Supplier and Procurement Management
- Supplier information management.
- Registration of supply orders.
- Tracking of requested raw material categories and quantities.
- Identification of the suppliers associated with individual raw material batches.

### Inventory Management
- Classification of raw materials by product category.
- Tracking of raw material batches.
- Recording of warehouse locations.
- Management of cable characteristics and product information.

### Production and Product Traceability
- Registration of manufactured products.
- Assignment of unique serial numbers to finished products.
- Association between manufactured products and the raw materials used in production.
- Traceability of original materials and suppliers.

### Customer Order Management
- Registration of customer information.
- Management of customer orders and order values.
- Organization of order details, quantities and requested product categories.

### Packing and Shipment Management
- Creation and management of packing lists.
- Association of shipments with customers.
- Assignment of transport companies and vehicle information.
- Retrieval of shipment and delivery details.

## 5. Database Design Process

The project was developed through several stages.

### 5.1 Requirements Analysis

The initial phase involved collecting and organizing the company's business requirements.

Activities included:
- Construction of a glossary of business terms, descriptions, synonyms and relationships.
- Identification of the main database operations.
- Classification of operations as interactive or batch processes.
- Estimation of operational frequencies and database volumes.

### 5.2 Conceptual Design

An Entity-Relationship (E/R) model was developed to represent the main business entities and their relationships.

The conceptual model includes entities such as:

- SUPPLIER
- SUPPLY_ORDER
- RAW_PRODUCTS
- RAW_PRODUCTS_CATEGORY
- PROCESSED_PRODUCT
- CLIENTS
- CLIENT_ORDER
- ORDER_DETAILS
- PACKING_LIST
- TRANSPORT

Relationships and cardinalities were defined to represent the company's operational processes.

### 5.3 Logical Design

The conceptual model was translated into a relational database schema.

This phase involved:
- Mapping one-to-many (1:N) relationships.
- Transforming many-to-many (N:M) relationships into associative tables.
- Defining primary keys and foreign keys.
- Managing composite keys for dependent entities.
- Refining attributes and removing redundant relationships.

The resulting relational schema was designed to support the identified business operations while maintaining data consistency.

## 6. Database Structure

The database consists of interconnected entities representing the main operational areas of the company.

| Functional Area | Main Entities |
|---|---|
| Procurement | SUPPLIER, SUPPLY_ORDER, REQUEST |
| Raw Materials | RAW_PRODUCTS, RAW_PRODUCTS_CATEGORY |
| Production | PROCESSED_PRODUCT |
| Customers and Sales | CLIENTS, CLIENT_ORDER, ORDER_DETAILS |
| Logistics | PACKING_LIST, TRANSPORT |

The relationships between these entities allow information to be retrieved across different stages of the supply chain.

## 7. Business Rules and Data Integrity

The database design includes business constraints intended to maintain operational consistency.

**Chronological Consistency**

The production date of a finished product must be later than the receipt date of its associated raw material.

**Product Traceability**

Each processed product must be linked to at least one valid raw product, maintaining the relationship between finished goods, original materials and suppliers.

**Order Fulfillment**

A packing list must not be generated when the available quantity of processed products is lower than the quantity requested in the corresponding order details.

**Transport Assignment**

Each packing list must be associated with exactly one transport company before its transport date can be finalized.

**Unique Product Identification**

Different batches belonging to the same raw material category must remain distinguishable through their identifiers and operational information, such as arrival date and warehouse location.

## 8. SQL Queries and Business Applications

The project includes SQL queries designed to retrieve and analyze information relevant to daily business operations.

Examples include:

| Query | Business Application |
|---|---|
| Raw material retrieval by supplier | Supplier and inventory analysis |
| Finished product traceability | Identification of original materials and suppliers |
| Total requested quantities by category | Procurement and demand analysis |
| Customer order retrieval | Sales order management |
| Packing list and shipment retrieval | Logistics and delivery tracking |
| Shipment count by transport company | Transport activity analysis |
| Total order value by sales agent | Commercial performance analysis |

The queries use SQL operations including:

- SELECT and WHERE
- JOIN operations
- GROUP BY and aggregate functions
- ORDER BY
- SUM and COUNT

These queries demonstrate how the relational database can support operational information retrieval and business analysis.

## 9. Technologies and Technical Concepts

**Technologies**
- SQL
- Relational Database Design

**Technical Concepts**
- Entity-Relationship (E/R) Modeling
- Relational Schema Design
- Primary Keys and Foreign Keys
- One-to-Many and Many-to-Many Relationships
- Composite Keys
- Database Normalization
- Data Integrity Constraints
- SQL Joins and Aggregation
- Data Retrieval and Business Queries

## 10. Project Team

Academic group project developed by:

- **Alberto Pozzi**
- Lorenzo Gherardi
- Elia Drudi

---

*This repository documents an academic database design project. The database model and SQL queries were developed as part of a university assignment focused on relational database design and business process management.*
