# TourDesk

# 00 - Project Blueprint

## Overview

TourDesk is a Google Apps Script application that helps a tourism company manage hotels, pricing, and marketing content through a modern admin dashboard and a public website.

The project is designed as an MVP with a production-ready architecture that can later evolve into an ASP.NET Core application.

---

# Core Principles

- Simplicity over complexity.
- Clean architecture.
- Modular code.
- Mobile-first.
- Reusable components.
- Minimal user clicks.
- Business rules are enforced server-side.
- No duplicated logic.
- Future migration to .NET must be straightforward.

---

# Technology Stack

Backend

- Google Apps Script

Frontend

- HTML Service
- Bootstrap 5
- Vanilla JavaScript (ES6)

Storage

- Google Sheets

Media

- Google Drive

---

# Architecture

Layered Architecture

Presentation Layer

↓

Application Services

↓

Repositories (Google Sheets)

↓

Google Services

---

# Project Type

Single Page Admin Dashboard

Read-only Public Website

---

# Storage Strategy

Google Sheets

One Sheet = One Entity

Relations are maintained using Smart IDs.

---

# Smart IDs

Every entity owns a readable unique identifier.

Examples

DST-000001

HOT-000001

PRC-000001

---

# Images

Images are stored inside Google Drive.

Only Drive File IDs are stored in the database.

Image URLs are generated dynamically.

---

# Authentication

Single Admin Account

Session-based Authentication.

No customer accounts.

---

# Default Language

Arabic (RTL)

Architecture prepared for English later.

---

# UI Philosophy

Modern

Clean

Minimal

Fast

Responsive

Touch Friendly

---

# Project Structure

Core

Configuration

Services

Repositories

Utilities

HTML Pages

Reusable Components

---

# Code Principles

Single Responsibility Principle

DRY

Reusable Functions

No Hardcoded Values

Meaningful Naming

Centralized Configuration

---

# Core Services

Config

Constants

Router

SheetManager

Logger

DriveService

ValidationService

AuthenticationService

---

# File Organization

One responsibility per file.

No large files.

Reusable HTML components.

---

# Public Website

Read-only.

Data comes only from the Admin Dashboard.

---

# Future Ready

Designed to support:

- ASP.NET Core
- SQL Server
- REST API
- Flutter Mobile App
- AI Marketing
- Online Booking

without rebuilding the product.
