# TourDesk

# 04 - Business Rules

## Document Information

| Property | Value |
|----------|-------|
| Version | 1.0 |
| Status | Approved |
| Depends On | 03-Product-Specification.md |

---

# Purpose

This document defines the business rules that govern TourDesk.

These rules represent business decisions and must always be enforced by the application.

---

# Hotel Rules

## BR-001

A hotel belongs to exactly one destination.

---

## BR-002

A hotel belongs to exactly one category.

---

## BR-003

A hotel may contain multiple features.

---

## BR-004

A hotel may contain up to 20 images.

The first uploaded image automatically becomes the cover image.

---

## BR-005

Hotel status must be one of:

- Draft
- Published

---

## BR-006

A Draft hotel is never visible on the public website.

---

## BR-007

A Published hotel is visible only if it has at least one active pricing record.

---

## BR-008

Deleting a hotel permanently removes:

- Images
- Pricing
- Related records

No soft delete.

---

# Pricing Rules

## BR-009

Each pricing record belongs to exactly one hotel.

---

## BR-010

Each pricing record has exactly one room type.

---

## BR-011

Each pricing record has exactly one meal plan.

---

## BR-012

Price must be greater than zero.

---

## BR-013

Start Date must be before End Date.

---

## BR-014

The same hotel cannot have overlapping pricing periods for the same Room Type and Meal Plan.

---

## BR-015

Duplicate pricing records are not allowed.

---

## BR-016

Expired pricing remains stored but is excluded from active search results.

---

## BR-017

Lowest active price is calculated automatically.

Manual editing is not allowed.

---

# Destination Rules

## BR-018

Destination names must be unique.

---

## BR-019

A destination cannot be deleted while it still contains hotels.

---

# Features Rules

## BR-020

Features can be reused across multiple hotels.

---

# Categories Rules

## BR-021

Categories can be reused across multiple hotels.

---

# Room Types Rules

## BR-022

Room Types are managed centrally.

Deleting a Room Type that is in use is not allowed.

---

# Meal Plans Rules

## BR-023

Meal Plans are managed centrally.

Deleting a Meal Plan that is in use is not allowed.

---

# Child Policy Rules

## BR-024

Child Policy is optional.

---

## BR-025

Child Policy is stored as plain text.

Examples:

- Under 6 Free
- Under 12 Half Price

---

# Website Rules

## BR-026

The website is read-only.

Customers cannot modify any data.

---

## BR-027

Hotels without active prices are hidden from search results.

---

## BR-028

Hotels with expired prices remain visible.

Their details page displays:

"No prices available at the moment."

---

## BR-029

The website always reflects the latest published data.

No manual publishing process is required.

---

# Search Rules

## BR-030

Search supports:

- Destination
- Budget
- Stars
- Meal Plan
- Room Type

---

## BR-031

Search results are sorted by:

1. Featured Hotels
2. Lowest Active Price
3. Hotel Name

---

# Marketing Rules

## BR-032

Marketing posts are generated automatically from system data.

---

## BR-033

Generated posts are never saved automatically.

The owner decides whether to copy or publish them.

---

# Settings Rules

## BR-034

Company Settings affect the entire website immediately.

---

## BR-035

Changing the company logo updates all generated pages.

---

# Global Rules

## BR-036

Every record has:

- UUID
- Created At
- Updated At

---

## BR-037

Deletion always requires confirmation.

---

## BR-038

Search is available on every management screen.

---

## BR-039

The system minimizes user clicks whenever possible.

---

## BR-040

The system always guides the user to the next logical action.

---

# Acceptance Criteria

All business rules are uniquely identified.

All critical business decisions are documented.

No business logic should exist outside these rules.
