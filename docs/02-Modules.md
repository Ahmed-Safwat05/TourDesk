# TourDesk

## Document Information

| Property | Value |
|----------|-------|
| Document | Modules |
| Version | 1.0 |
| Status | ✅ Approved |
| Owner | Product Team |
| Depends On | 01-Vision.md |
| Last Updated | July 2026 |

---

# Purpose

This document defines all functional modules inside TourDesk, their responsibilities, relationships, and boundaries.

Each module represents an independent business capability that can evolve without affecting the rest of the system.

---

# Product Overview

TourDesk consists of two main areas:

1. Public Website
2. Admin Dashboard

Both areas use the same data source but serve different users.

---

# User Roles

## Company Owner

The Company Owner is responsible for managing all tourism content.

Permissions:

- Full Access
- Create
- Update
- Delete
- Generate Marketing Content
- Manage Settings

---

## Customer

The customer only interacts with the public website.

Permissions:

- Browse Destinations
- Browse Hotels
- Search
- Filter
- View Hotel Details
- Contact Company

Customers cannot modify any data.

---

# System Modules

---

# Dashboard Module

## Purpose

Provides a quick overview of the business.

## Responsibilities

- Show total destinations
- Show total hotels
- Show active prices
- Show featured hotels
- Quick actions

## Depends On

- Hotels
- Pricing
- Destinations

---

# Destinations Module

## Purpose

Manage tourist destinations.

## Responsibilities

- Create destination
- Edit destination
- Delete destination
- Upload cover image
- Manage description

## Fields

- Name
- Description
- Cover Image

## Used By

- Hotels
- Website
- Search

---

# Hotels Module

## Purpose

Manage hotel information.

## Responsibilities

- Create hotel
- Edit hotel
- Delete hotel
- Upload gallery
- Manage description
- Manage location
- Manage status

## Fields

- Name
- Destination
- Category
- Stars
- Description
- Address
- Google Maps URL
- Gallery
- Featured
- Active

## Depends On

- Destinations
- Categories
- Features
- Pricing

---

# Pricing Module

## Purpose

Manage hotel prices.

This is the core business module of TourDesk.

Every hotel can have multiple pricing records.

## Responsibilities

- Seasonal prices
- Date ranges
- Meal plans
- Room types
- Child policy
- Lowest price calculation

## Validation

- No overlapping periods.
- Start date must be before end date.
- Price must be positive.
- Duplicate records are not allowed.

## Depends On

- Hotels
- Room Types
- Meal Plans

---

# Room Types Module

## Purpose

Manage room types.

## Examples

- Single
- Double
- Triple
- Quad
- Family

---

# Meal Plans Module

## Purpose

Manage accommodation plans.

## Examples

- Bed & Breakfast
- Half Board
- Full Board
- Soft All Inclusive
- Ultra All Inclusive

---

# Features Module

## Purpose

Manage hotel features.

## Feature Structure

- Name
- Icon

## Examples

- Pool
- WiFi
- Gym
- Aqua Park
- Kids Area
- Private Beach

---

# Hotel Categories Module

## Purpose

Classify hotels.

## Examples

- Hotel
- Resort
- Chalet
- Apartment
- Camp

---

# Marketing Module

## Purpose

Generate marketing content automatically.

## Responsibilities

- Hotel Post Generator
- Price List Generator
- Live Preview
- Copy Plain Text

Future versions may support image generation.

---

# Settings Module

## Purpose

Manage company information.

## Responsibilities

- Company Name
- Logo
- About
- WhatsApp
- Phone
- Social Media
- Currency
- Default Language

---

# Public Website Modules

## Home

Displays:

- Hero Section
- Destination Cards
- Featured Hotels
- Search Area

---

## Destination Listing

Displays all available destinations.

---

## Hotel Listing

Displays hotel cards.

Each card includes:

- Cover Image
- Hotel Name
- Stars
- Lowest Price
- Meal Plan
- Destination

---

## Hotel Details

Displays:

- Gallery
- Description
- Features
- Address
- Google Maps
- Available Prices
- Child Policy
- Contact Button

---

## Search

Supports filtering by:

- Destination
- Budget
- Stars
- Meal Plan
- Room Type

---

## About

Generated dynamically from Company Settings.

---

## Contact

Displays company contact information.

---

# Module Relationships

Destination

→ Hotels

Hotels

→ Pricing

Hotels

→ Features

Hotels

→ Gallery

Pricing

→ Room Types

Pricing

→ Meal Plans

Settings

→ Website

Settings

→ About

Settings

→ Contact

---

# Design Principles

Each module should:

- Have a single responsibility.
- Be independent whenever possible.
- Support future expansion.
- Minimize manual work.
- Keep the interface simple.

---

# Future Modules

Planned but excluded from Version 1:

- Offers
- Trips
- Transportation
- Cruise Packages
- Reservations
- Online Payments
- Notifications
- Reports
- Multi-company Support

---

# Notes for Implementation

- Every record uses UUID.
- Images are uploaded per hotel.
- First uploaded image becomes the cover image automatically.
- Hotel deletion permanently removes its gallery.
- Public website is read-only.
- Dashboard requires authentication.

---

# Acceptance Criteria

The Modules document is complete when:

- All modules are identified.
- Responsibilities are defined.
- Dependencies are documented.
- Public modules are defined.
- Dashboard modules are defined.
- Future modules are identified.

---

Status: ✅ Approved
