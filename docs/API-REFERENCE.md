# API Reference

## Firebase CRUD Module

All CRUD operations are in `js/firestore-crud.js`

### Events

#### Create Event
```javascript
const eventId = await FirestoreCRUD.createEvent(eventData);
```

#### Get Event
```javascript
const event = await FirestoreCRUD.getEvent(eventId);
```

#### Get Events with Filters
```javascript
const events = await FirestoreCRUD.getEvents({ status: 'published' });
```

#### Update Event
```javascript
await FirestoreCRUD.updateEvent(eventId, updateData);
```

#### Delete Event
```javascript
await FirestoreCRUD.deleteEvent(eventId);
```

### Registrations

#### Create Registration
```javascript
const regId = await FirestoreCRUD.createRegistration(registrationData);
```

#### Get Registrations
```javascript
const registrations = await FirestoreCRUD.getRegistrations(eventId);
```

#### Update Registration
```javascript
await FirestoreCRUD.updateRegistration(regId, { status: 'approved' });
```

### Announcements

#### Create Announcement
```javascript
const annId = await FirestoreCRUD.createAnnouncement(announcementData);
```

#### Get Announcements
```javascript
const announcements = await FirestoreCRUD.getAnnouncements();
```

### Statistics

#### Get Dashboard Stats
```javascript
const stats = await FirestoreCRUD.getDashboardStats();
```

## Authentication Module

### Sign In
```javascript
const user = await Auth.signIn(email, password);
```

### Sign Out
```javascript
await Auth.signOut();
```

### Check Admin Status
```javascript
const isAdmin = await Auth.isAdmin();
```

## Toast Notifications

```javascript
Toast.success(message);
Toast.error(message);
Toast.warning(message);
Toast.info(message);
```
