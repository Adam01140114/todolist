# Todo List Web App

A beautiful, mobile-friendly todo list application with Firebase integration, drag-and-drop reordering, and important task pinning.

## Features

- ✅ **Create and manage todos** - Add, complete, and delete tasks
- ⭐ **Important tasks** - Pin important tasks to the top of your list
- 🔄 **Drag and drop** - Reorder tasks by dragging them up and down
- 📱 **Mobile responsive** - Optimized for all screen sizes
- 🔥 **Firebase integration** - Real-time data synchronization
- 🎨 **Beautiful UI** - Modern, clean design with smooth animations

## Getting Started

1. Open `index.html` in your web browser
2. Start adding tasks using the input field
3. Mark tasks as important using the star button
4. Drag tasks to reorder them
5. Complete tasks by clicking the check button

## Firebase Setup

The app is already configured with the provided Firebase configuration. Your data will be automatically saved to the Firebase Realtime Database.

### Firebase Security Rules

**IMPORTANT:** If you see a "Permission denied" error after signing in, you need to update your Firebase Realtime Database security rules.

1. Go to the [Firebase Console](https://console.firebase.google.com/)
2. Select your project (`todolis-a32fe`)
3. Navigate to **Realtime Database** → **Rules** tab
4. Replace the existing rules with the following:

```json
{
  "rules": {
    "users": {
      "$uid": {
        "todos": {
          ".read": "$uid === auth.uid",
          ".write": "$uid === auth.uid"
        }
      }
    }
  }
}
```

5. Click **Publish** to save the rules

Alternatively, you can use the `database.rules.json` file included in this project and deploy it using the Firebase CLI:

```bash
firebase deploy --only database
```

These rules ensure that:
- Users can only read/write their own todos (under `users/{their-uid}/todos`)
- Unauthenticated users cannot access any data
- Each user's data is isolated and secure

## Mobile Usage

The app is fully responsive and works great on mobile devices:
- Touch-friendly interface
- Optimized for small screens
- Smooth drag and drop on touch devices

## Browser Compatibility

Works on all modern browsers including:
- Chrome
- Firefox
- Safari
- Edge
- Mobile browsers

Enjoy organizing your tasks! 🚀
