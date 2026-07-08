# TourDesk

# 05 - Database Design

## Document Information

| Property | Value |
|----------|-------|
| Version | 1.0 |
| Status | Approved |
| Depends On | 04-Business-Rules.md |

---

# Purpose

This document defines the logical database structure used by TourDesk.

Although TourDesk uses Google Sheets as its storage engine, the data model follows relational database principles.

---

# Database Overview

Storage Engine

Google Sheets

Architecture

One Sheet = One Table

Relationships are maintained using Smart IDs.

---

# Smart IDs

Every entity has a readable unique identifier.

Examples

DST-000001

HOT-000001

PRC-000001

IMG-000001

FTR-000001

CAT-000001

RMT-000001

MLP-000001

---

# Tables

## Destinations

Primary Key

DestinationId

Columns

- DestinationId
- Name
- Description
- CoverImageFileId
- CreatedAt
- UpdatedAt

---

## Categories

Primary Key

CategoryId

Columns

- CategoryId
- Name
- CreatedAt
- UpdatedAt

---

## Features

Primary Key

FeatureId

Columns

- FeatureId
- Name
- Icon
- CreatedAt
- UpdatedAt

---

## RoomTypes

Primary Key

RoomTypeId

Columns

- RoomTypeId
- Name
- CreatedAt
- UpdatedAt

---

## MealPlans

Primary Key

MealPlanId

Columns

- MealPlanId
- Name
- CreatedAt
- UpdatedAt

---

## Hotels

Primary Key

HotelId

Foreign Keys

DestinationId

CategoryId

Columns

- HotelId
- DestinationId
- CategoryId
- Name
- Stars
- Description
- Address
- GoogleMapsUrl
- Status
- Featured
- CreatedAt
- UpdatedAt

---

## HotelImages

Primary Key

ImageId

Foreign Key

HotelId

Columns

- ImageId
- HotelId
- DriveFileId
- SortOrder
- IsCover
- CreatedAt

---

## HotelFeatures

Composite Key

HotelId

FeatureId

Columns

- HotelId
- FeatureId

---

## Pricing

Primary Key

PricingId

Foreign Keys

HotelId

RoomTypeId

MealPlanId

Columns

- PricingId
- HotelId
- RoomTypeId
- MealPlanId
- Price
- StartDate
- EndDate
- Status
- ChildPolicy
- Notes
- CreatedAt
- UpdatedAt

Status Values

- Draft
- Published

Expired is calculated automatically.

---

## CompanySettings

Single Row Table

Columns

- CompanyName
- LogoFileId
- About
- WhatsApp
- Phone
- Facebook
- Instagram
- DefaultLanguage
- Currency

---

## System

Single Row Table

Columns

- DatabaseVersion
- CompanyId
- CreatedAt

---

# Relationships

Destination

1 ---- *

Hotels

Category

1 ---- *

Hotels

Hotels

1 ---- *

Pricing

Hotels

1 ---- *

HotelImages

Hotels

* ---- *

Features

Pricing

* ---- 1

RoomTypes

Pricing

* ---- 1

MealPlans

---

# Derived Data

The following values are never stored.

They are calculated dynamically.

- Lowest Price
- Active Price
- Expired Status
- Hotel Image Count

---

# Constraints

Destination Name

Unique

Hotel Images

Maximum 20

Hotel Stars

1–5

Pricing

No overlapping periods

Room Type + Meal Plan + Period

Must be unique

---

# Google Drive

Only Drive File IDs are stored.

Public URLs are generated dynamically.

---

# Naming Convention

Sheets

PascalCase

Columns

camelCase

Smart IDs

PREFIX-000001

---

# Sheet Order

1. System

2. CompanySettings

3. Destinations

4. Categories

5. Features

6. RoomTypes

7. MealPlans

8. Hotels

9. HotelImages

10. HotelFeatures

11. Pricing

---

# Notes for Implementation

Every service must access Sheets through a central Sheet Manager.

Sheet names must never be hardcoded.

---

# Acceptance Criteria

All entities identified.

Relationships documented.

Constraints defined.

Ready for Apps Script implementation.
