# Click Tracker Web Application

## Overview
This is a single-page web application that tracks user clicks on unique URLs, collecting client-side data such as browser fingerprint, geolocation, and device details. All data is stored locally in the user's browser using IndexedDB, ensuring no server-side dependencies. The application uses Tailwind CSS for styling, Leaflet.js for map visualization, and FingerprintJS for browser fingerprinting, adhering to GDPR/CCPA privacy requirements.

## Setup and Running
1. **Host the Application**:
   - Copy the `index.html` file to a static hosting service (e.g., Netlify, GitHub Pages, or a local server like `http-server`).
   - No server-side setup is required as the application is entirely client-side.

2. **Dependencies** (all loaded via CDN):
   - Tailwind CSS: For responsive styling.
   - Leaflet.js: For map visualization of geolocation data.
   - FingerprintJS: For generating unique browser fingerprints.
   - No additional installation is needed; all libraries are loaded from `cdn.jsdelivr.net` or `unpkg.com`.

3. **Running Locally**:
   - Serve `index.html` using a static server (e.g., `npx http-server` or Python's `python -m http.server`).
   - Access the site via `http://localhost:8080/?id=campaign123` to test with a campaign ID.

## Usage
1. **Generating Unique URLs**:
   - Append a campaign ID as a query parameter to the URL (e.g., `https://your-site.com/?id=campaign123`).
   - Share this URL to track clicks for a specific campaign.

2. **Accessing the Dashboard**:
   - Click "View Dashboard" on the landing page.
   - Enter the default password `admin123` (modify in the code for production use).
   - The dashboard displays:
     - Total clicks and unique users (based on fingerprints).
     - A table of all click data (ID, timestamp, campaign ID, IP, fingerprint, etc.).
     - A map showing click locations (if geolocation is provided).

3. **Exporting and Clearing Data**:
   - **Export**: Click "Export Data" to download a JSON file containing all click data.
   - **Clear**: Click "Clear Data" to remove all stored data from IndexedDB.
   - **Opt Out**: On the privacy policy page, click "Opt Out" to delete all data and reset consent.

## Privacy and Consent
- A consent popup appears on first visit, requesting permission for geolocation, canvas fingerprinting, and WebGL fingerprinting.
- All data is stored locally in IndexedDB and not transmitted to any server.
- Users can opt out via the privacy policy page, which deletes all stored data.
- The privacy policy is accessible from the landing page and explains data usage.

## Notes
- **Storage Limits**: The application caps data at 1,000 records to avoid exceeding browser storage quotas. A warning can be added in the code to alert users when approaching this limit.
- **Security**: Data is sanitized before storage to prevent injection attacks. The client-side password is basic (`admin123`) and should be strengthened for production.
- **Privacy Compliance**: The application adheres to GDPR/CCPA by obtaining explicit consent and storing data client-side only.
- **References**: The implementation draws from FingerprintJS for robust browser fingerprinting, inspired by projects like Broprint.js and ThumbmarkJS for efficient client-side identification.

## Example Workflow
1. User visits `https://your-site.com/?id=campaign123`.
2. Consent popup appears; user accepts or declines tracking options.
3. Data (e.g., IP, fingerprint, geolocation) is collected and stored in IndexedDB.
4. Landing page confirms the click.
5. User accesses the dashboard with the password, views statistics, and sees click locations on a map.