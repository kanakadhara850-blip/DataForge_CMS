# Firestore Setup Guide

## Collections Overview

### 1. events
Stores all event information.

**Fields:**
- `title` (String) - Event title
- `subtitle` (String) - Event tagline
- `description` (String) - Full description
- `category` (String) - Event category
- `eventType` (String) - workshop, seminar, conference, etc.
- `date` (Timestamp) - Event date
- `time` (String) - Event time (HH:MM format)
- `duration` (Number) - Duration in minutes
- `venue` (String) - Venue name
- `contactEmail` (String) - Contact email
- `posterImage` (String) - Poster image URL
- `bannerImage` (String) - Banner image URL
- `status` (String) - draft, published, archived
- `registrationCount` (Number) - Current registrations
- `views` (Number) - View counter
- `createdAt` (Timestamp) - Creation date
- `updatedAt` (Timestamp) - Last update date

### 2. registrations
Stores event registration data.

**Fields:**
- `eventId` (String) - Reference to event
- `email` (String) - Participant email
- `name` (String) - Participant name
- `phone` (String) - Participant phone
- `college` (String) - College/Organization
- `registrationDate` (Timestamp) - Registration date
- `status` (String) - pending, approved, rejected

### 3. announcements
Stores announcements.

**Fields:**
- `title` (String) - Announcement title
- `content` (String) - Announcement content
- `type` (String) - info, warning, success
- `isPinned` (Boolean) - Pin to top
- `createdAt` (Timestamp) - Creation date

### 4. admins
Stores admin user information.

**Fields:**
- `uid` (String) - Firebase Auth UID
- `email` (String) - Admin email
- `name` (String) - Admin name
- `role` (String) - admin, moderator

### 5. categories
Stores event categories.

**Fields:**
- `name` (String) - Category name
- `slug` (String) - URL-friendly slug
- `icon` (String) - Icon emoji
- `color` (String) - Hex color
