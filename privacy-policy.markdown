# Privacy Policy

## Data Collection and Usage
This web application collects non-personally identifiable information when you click a provided link, including:
- Browser fingerprint (unique identifier based on device and browser settings).
- IP address (via a third-party API).
- Geolocation (latitude/longitude, with explicit consent).
- Browser details (user agent, screen resolution, timezone, language, etc.).
- Canvas and WebGL fingerprints (with explicit consent).
- Campaign ID from the URL.
- Timestamp, referrer URL, device memory, CPU cores, and touch support.

All data is stored locally in your browser using IndexedDB and is not transmitted to any server, ensuring your privacy.

## Purpose
The collected data is used to track link clicks for campaign analysis, displayed in a client-side dashboard with statistics and a map visualization of click locations (if geolocation is provided).

## Consent
- A popup requests your consent for geolocation, canvas fingerprinting, and WebGL fingerprinting on your first visit.
- You can decline any or all tracking options, and no data will be collected for declined options.
- Consent preferences are stored in your browser's localStorage.

## Data Management
- You can view all collected data in the dashboard (password-protected).
- Export data as a JSON file for manual analysis.
- Clear all stored data or opt out entirely via the dashboard or privacy page, which deletes the IndexedDB database and resets consent.

## Security
- Data is sanitized to prevent injection attacks.
- Stored data is local to your browser and not inherently secure. Do not store sensitive information.
- The dashboard uses a simple client-side password (`admin123` by default).

## Your Rights
- Under GDPR and CCPA, you have the right to know what data is collected, opt out of collection, and delete your data.
- Use the "Opt Out" button on the privacy page to delete all data and withdraw consent.

## Contact
For questions, contact the site administrator via the hosting platform (e.g., GitHub issues if hosted on GitHub Pages).