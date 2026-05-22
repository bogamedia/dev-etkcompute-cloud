# Playhost Project - Release Notes & Feature Documentation

## Overview
This document outlines the recent updates, features, and technical implementations for the Playhost Next.js project. It covers the migration to Next.js, the integration of a CMS, and new social features.

## 🚀 Key Features

### 1. Content Management System (CMS)
We have implemented a full-fledged CMS for managing news and blog posts.
- **Post Management**: Create, read, update, and delete posts.
- **Moderation Workflow**: 
  - Posts have statuses: `PENDING`, `PUBLISHED`, `REJECTED`.
  - Admin approval system for user-generated content.
- **Categorization**: Posts can be organized by categories.
- **Media Support**: Added support for post images.

### 2. User System & Authentication
- **Roles**: 
  - `ADMIN`: Full access to content moderation and system stats.
  - `USER`: Can register, login, and interact with content.
- **Authentication**: Secure Login and Signup flows.

### 3. Social Interactions
We have transformed the platform into a more social experience:
- **Follow System**: Users can follow other users to see their updates.
- **Messaging**: Direct messaging system between users.
  - *New*: Added `isRead` status to track seen messages.
- **Engagement**:
  - **Likes**: Users can like posts.
  - **Comments**: Threaded discussions on posts.
  - **Reposts**: Users can share posts to their own feed.

## 🛠 Technical Implementation

### Tech Stack
- **Framework**: Next.js 14
- **Database**: MySQL with Prisma ORM
- **Styling**: Bootstrap 5, Sass, Styled Components
- **UI Libraries**: Swiper, AOS (Animate On Scroll), SweetAlert2

### Database Schema Updates
Recent changes to the `prisma/schema.prisma` include:
- **`User` Model**: Added relations for `sentMessages`, `receivedMessages`, `followedBy`, and `following`.
- **`Post` Model**: Added `status` enum (`PENDING`, `PUBLISHED`, `REJECTED`) and `image` field.
- **`Message` Model**: Added `isRead` boolean field.
- **`Follow` Model**: New join table for user relationships.

### API Endpoints
New API routes have been created to support these features:
- `/api/auth/*`: Authentication handlers.
- `/api/admin/*`: Admin actions for approving posts and viewing stats.
- `/api/posts/*`: CRUD operations for posts.
- `/api/messages/*`: Messaging logic.

## 📅 Recent Changelog
- **CMS Integration**: Core CMS features merged.
- **Image Support**: Database migration to support images in posts.
- **Follow Feature**: Backend logic for user-to-user following.
- **Message Read Status**: Feature to mark messages as read.

---
*Last Updated: January 2026*
