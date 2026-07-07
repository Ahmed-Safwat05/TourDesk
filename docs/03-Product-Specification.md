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



# Hotels Module

## Business Goal

Allow the owner to manage hotel information and publish it on the public website.

---

## User Stories

- Add a hotel.
- Edit hotel information.
- Delete a hotel permanently.
- Upload hotel gallery.
- Mark hotel as Featured.
- Publish or unpublish a hotel.

---

## Screen

Hotel Management

Contains:

- Search
- Data Grid
- Add Hotel
- Edit
- Delete
- View Details

---

## Main Components

### Data Grid

Columns:

- Cover Image
- Hotel Name
- Destination
- Stars
- Category
- Status
- Featured
- Created At

---

### Hotel Form

Basic Information

- Name *
- Destination *
- Category *
- Stars *
- Description
- Address
- Google Maps URL

Media

- Gallery (Maximum 20 Images)

Relations

- Features
- Status
- Featured

---

## Hotel Details

Displays

- Basic Information
- Gallery
- Pricing Records
- Child Policies
- Preview Button

This is the only module that has a dedicated details page.

---

## Workflow

Owner creates hotel

↓

Upload gallery

↓

First uploaded image becomes Cover automatically

↓

Save as Draft

↓

Add Pricing

↓

Publish

↓

Visible on Website

---

## Validation

Required

- Name
- Destination
- Category
- Stars

Rules

- Hotel names can repeat across different destinations.
- Maximum 20 images.
- Stars: 1–5 only.
- Google Maps URL is optional.

Publishing Rules

A hotel cannot be published unless:

- At least one active pricing record exists.

---

## UX Decisions

- Drawer for Add/Edit.
- Separate page for Hotel Details.
- Cover image selected automatically.
- Delete requires confirmation.
- Preview opens the public hotel page.

---

## Notes for Implementation

Deleting a hotel permanently deletes:

- Gallery
- Pricing
- Related records

No soft delete.

---

# Pricing Module

## Business Goal

Manage hotel prices across different periods and room configurations.

---

## User Stories

- Add seasonal pricing.
- Update pricing.
- Delete pricing.
- Define child policy.

---

## Screen

Pricing Management inside Hotel Details.

---

## Main Components

Pricing Data Grid

Columns

- Room Type
- Meal Plan
- Price
- Date Range
- Status

Pricing Form

Fields

- Room Type *
- Meal Plan *
- Price *
- Start Date *
- End Date *
- Child Policy (Optional)
- Notes (Optional)

---

## Workflow

Open Hotel

↓

Pricing

↓

Add Price

↓

Validation

↓

Save

↓

Website updates automatically

---

## Validation

- Price > 0
- Start < End
- No overlapping periods for the same Room Type + Meal Plan.
- Duplicate pricing records are not allowed.

---

## UX Decisions

- Active prices appear first.
- Expired prices shown in gray.
- Current active price highlighted.

---

## Notes for Implementation

Lowest active price is calculated automatically and used across the website.

---

# Room Types Module

Manage available room types.

Examples

- Single
- Double
- Triple
- Family

Simple CRUD using Drawer.

---

# Meal Plans Module

Manage accommodation plans.

Examples

- Half Board
- Full Board
- Soft All Inclusive

Simple CRUD using Drawer.

---

# Features Module

Manage hotel features.

Fields

- Name
- Icon

Used when creating hotels.

---

# Hotel Categories Module

Manage hotel categories.

Examples

- Hotel
- Resort
- Chalet
- Camp

Simple CRUD.

---

# Marketing Module

## Business Goal

Generate ready-to-publish marketing content.

---

## Types

- Price List
- Hotel Details

---

## Workflow

Select Destination or Hotel

↓

Generate

↓

Preview

↓

Copy

↓

Publish manually

---

## Output

Plain Text

Ready for Facebook / WhatsApp / Telegram.

Future versions may support image generation.

---

# Settings Module

Manage

- Company Name
- Logo
- WhatsApp
- Phone
- About
- Social Media
- Default Language

Changes are reflected automatically on the public website.

---

# Public Website

## Home

- Hero
- Search
- Featured Hotels
- Destinations

---

## Search

Filters

- Destination
- Budget
- Stars
- Meal Plan
- Room Type

---

## Hotel Details

Displays

- Gallery
- Description
- Features
- Active Prices
- Child Policy
- Google Maps
- Contact Buttons

Hotels without active prices are hidden from search results.

Hotels with expired prices remain visible but display:

"No prices available at the moment."

---

## Notes for Implementation

The website is fully read-only.

All updates come from the Admin Dashboard.
