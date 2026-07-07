# TourDesk

# 03 - Product Specification

## Dashboard Module

---

## Business Goal

Provide the company owner with a quick overview of the system and direct access to the most common actions.

---

## User Stories

### US-001

As a Company Owner,

I want to see a summary of my business

so that I know the current status immediately after logging in.

---

### US-002

As a Company Owner,

I want quick shortcuts

so that I can perform common actions faster.

---

## Pages

Dashboard

---

## UI Components

### Statistics Cards

Display:

- Total Destinations
- Total Hotels
- Active Pricing Records
- Featured Hotels

---

### Quick Actions

Buttons:

- Add Destination
- Add Hotel
- Add Pricing
- Generate Marketing Post

---

### Recent Updates

Displays:

- Recently Added Hotels
- Recently Updated Prices

---

## Actions

The owner can:

- Open any management module.
- Navigate using quick actions.

No data can be edited directly from the dashboard.

---

## Workflow

Owner logs in

↓

Dashboard loads

↓

Statistics appear

↓

Owner selects an action

↓

Redirect to selected module

---

## Empty State

If the system contains no data:

Display:

"Welcome to TourDesk"

Show:

- Add Destination
- Company Setup

---

## Success Messages

Not applicable.

---

## Error Messages

If statistics fail to load:

"Unable to load dashboard data."

---

## UX Decisions

- Dashboard must load quickly.
- Statistics displayed as cards.
- Quick Actions always visible.
- Mobile responsive.

---

## Future Enhancements

Charts

Revenue

Reservations

Notifications

---

## Notes for Implementation

Statistics should be calculated dynamically.

---

# Destinations Module

---

## Business Goal

Allow the owner to manage all travel destinations displayed on the public website.

---

## User Stories

### US-003

As a Company Owner,

I want to add a destination

so that I can organize hotels by city.

---

### US-004

As a Company Owner,

I want to edit destination information

so that the website always displays accurate information.

---

### US-005

As a Company Owner,

I want to delete unused destinations

so that my dashboard remains organized.

---

## Pages

Destination List

Destination Form

---

## UI Components

Destination Table

Contains:

- Cover Image
- Name
- Number of Hotels
- Created Date
- Actions

---

Search Box

Search by destination name.

---

Add Destination Button

Opens the destination form.

---

Destination Form

Fields:

- Name *
- Description
- Cover Image

---

## Actions

Owner can:

- Add destination
- Edit destination
- Delete destination
- Search destinations

---

## Workflow

Owner clicks Add Destination

↓

Destination Form opens

↓

Owner enters data

↓

Owner uploads cover image

↓

Clicks Save

↓

Validation

↓

Destination saved

↓

Success message displayed

↓

Destination list refreshes automatically

---

## Validation

Required:

- Name

Optional:

- Description
- Cover Image

Rules:

Destination names must be unique.

---

## Empty State

No destinations yet.

Display:

"No destinations found."

Show:

"Add your first destination"

---

## Success Messages

Destination created successfully.

Destination updated successfully.

Destination deleted successfully.

---

## Error Messages

Destination name already exists.

Unable to save destination.

Unable to delete destination.

---

## UX Decisions

Search always visible.

Add button fixed at top.

Delete requires confirmation.

Table supports mobile view.

---

## Future Enhancements

Destination SEO

Destination Gallery

Destination Weather

---

## Notes for Implementation

Deleting a destination that contains hotels is not allowed.

The owner must move or delete hotels first.
