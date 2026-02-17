# OAuth 2.0 Basics 🛡️

**OAuth 2.0** is the industry-standard protocol for authorization. It's how you "Log in with Google" on other websites.

## The Analogy: Hotel Key Card 🏨
1.  You (The App) go to the Front Desk (Authorization Server).
2.  You show your ID (Credentials).
3.  The Front Desk gives you a **Key Card** (Access Token).
4.  You use the Key Card to enter your Room (Resource Server).
5.  The Key Card expires after a few days (Token Expiry).

## Key Roles
1.  **Resource Owner**: The User (You).
2.  **Client**: The Application (e.g., Spotify).
3.  **Authorization Server**: The Server that issues the token (e.g., Google, Facebook).
4.  **Resource Server**: The Server that has the data (e.g., Google Photos).

## The Flow (Simplified)
1.  **User** clicks "Connect with Google".
2.  **App** redirects User to **Google**.
3.  **User** signs in and says "Yes, I trust this App".
4.  **Google** sends a code back to the **App**.
5.  **App** exchanges that code for an **Access Token**.
6.  **App** uses the **Access Token** to call Google APIs.

## Why is this safe?
The App **never sees your password**. It only gets a token that can be revoked at any time.
