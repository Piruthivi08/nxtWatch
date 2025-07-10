# 📺 Nxt Watch - YouTube Clone Application

A fully functional video streaming application built with **React.js**, implementing dark/light theme support, login authentication, protected routes, video listing by category (Home, Trending, Gaming), video detail pages, and a save-for-later feature.

---

## 🚀 Live Demo
https://nxtwatchpm.ccbp.tech

Username : rahul
Password : rahul@2021

---

## 🧾 Project Summary

This project replicates the core functionality of a YouTube-like platform using a modern React stack:

- **User Authentication** using JWT & Cookies
- **Theme Switching** (Dark / Light)
- **Protected Routing**
- **Search functionality**
- **Save for later**
- **Video Detail Page** using React Player

---
🔐 Authentication Flow
Login at /login with:

Username: rahul

Password: rahul@2021

On success, JWT is stored in cookies

Protected routes:

/

/trending

/gaming

/saved-videos

/videos/:id

Authenticated users are redirected from /login to /

🧭 Routes & Functionality
🔑 Login Route
Invalid credentials → show API error message

Valid credentials → redirect to Home

Show/hide password toggle using checkbox

🏠 Home Route (/)
Fetch videos using:

sql
Copy
Edit
GET https://apis.ccbp.in/videos/all?search=
Show loader during fetch

On failure → show Failure View + Retry

On empty search results → show No Videos View

Search functionality supported

Click video → navigate to /videos/:id

Sidebar navigation supported

📈 Trending Route (/trending)
Fetch trending videos:

nginx
Copy
Edit
GET https://apis.ccbp.in/videos/trending
Loader, failure, retry, navigation handled

Click video → Video Detail page

🎮 Gaming Route (/gaming)
Fetch gaming videos:

nginx
Copy
Edit
GET https://apis.ccbp.in/videos/gaming
Loader, failure, retry, navigation handled

Click video → Video Detail page

📹 Video Item Details Route (/videos/:id)
Fetch details:

bash
Copy
Edit
GET https://apis.ccbp.in/videos/:id
Show video using react-player

Like, Dislike, Save button with toggle states:

Like and Dislike are mutually exclusive

Save adds to Saved Videos (and toggle text)

Retry on failure

💾 Saved Videos Route (/saved-videos)
Show saved videos

If empty → show “No Saved Videos Found”

Click video → go to detail view

❌ Not Found Route
Any invalid URL → render Not Found page

🔼 Header Functionality
Logo → go to /

Theme icon → toggle dark/light mode

Logout button → show popup

Confirm → logout + redirect to login

Cancel → close popup

📡 API Endpoints
🔐 Login API
POST https://apis.ccbp.in/login
Request

json
Copy
Edit
{
  "username": "rahul",
  "password": "rahul@2021"
}
Success Response

json
Copy
Edit
{
  "jwt_token": "token_string"
}
Failure Response

json
Copy
Edit
{
  "status_code": 404,
  "error_msg": "Username is not found"
}
🏠 Home Videos API
GET https://apis.ccbp.in/videos/all?search=

📈 Trending Videos API
GET https://apis.ccbp.in/videos/trending

🎮 Gaming Videos API
GET https://apis.ccbp.in/videos/gaming

📹 Video Details API
GET https://apis.ccbp.in/videos/:id
Example:
https://apis.ccbp.in/videos/802fcd20-1490-43c5-9e66-ce6dfefb40d1

✅ Testing Checklist
 Login and token validation

 Route protection and redirection

 Theme switch and header features

 Search and filter

 Save/unsave logic

 Like/dislike toggle

 Retry on API failure

 Empty state handling


  Technologies Used (Frontend Only)
React.js – for building component-based UI using functional components and Hooks

React Router DOM – for routing and navigation

Context API – for global state management (e.g., theme, saved videos)

JS Cookie – to handle JWT token storage in browser cookies

React Player – to embed and play YouTube videos

Conditional Rendering – for views based on API state (loading, error, empty)



