🚀 Tailwind + Vanilla JS Admin Portal
A lightweight, build-less administrative dashboard boilerplate using Tailwind CSS (via CDN) and Vanilla JavaScript. This project demonstrates a full authentication flow including registration, login, session persistence with cookies, and secure profile data fetching.

📂 Project Structure
Plaintext
├── index.html # Authentication entry point with session detection
├── register.html # User creation page linked to FreeAPI
├── profile.html # Secure dashboard (requires authentication)
└── README.md # Project documentation
🛠️ Tech Stack
Styling: Tailwind CSS (Play CDN)

Logic: Vanilla JavaScript (ES6+ Fetch API)

API: FreeAPI.app

Session Management: Browser Cookies & LocalStorage

🔑 Features & Logic Flow

1. Session Guard (Redirect Logic)
   Every page contains a "Gatekeeper" script to manage user access:

Authenticated Users: If a user visits index.html or register.html while a valid cookie exists, they are automatically redirected to profile.html.

Unauthenticated Users: If a user attempts to access profile.html without a token, they are booted back to index.html.

2. Registration & Login
   Register: Sends username, email, password, and role to the FreeAPI registration endpoint.

Login: Validates credentials and stores the returned accessToken in a document cookie with SameSite=Strict security.

3. Profile Management
   Data Fetching: On load, the profile page calls the GET /current-user endpoint using the Bearer Token stored in the cookie to display real-time account details.

Logout: Performs a POST /logout call to the server to invalidate the session, clears the local cookie, and redirects to the login screen.

🚀 Getting Started
Clone or Download the HTML files into a single folder.

Run a Local Server:

If using VS Code, right-click index.html and select "Open with Live Server".

Alternatively, use Python: python -m http.server 8000.

Test Credentials:
The forms are pre-filled with the following test keys for your convenience:

Username: doejohn

Password: test@123

⚠️ Notes for Production
CDN Usage: This project uses the Tailwind Play CDN for speed. For production, it is recommended to switch to the Tailwind CLI to minify CSS.

Security: For a real-world application, ensure your cookies are set to HttpOnly and Secure via a backend server to prevent XSS attacks.
