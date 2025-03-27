# Cloud's Dental Booking System - User Guide

This guide will help you make common changes to your dental booking system without requiring technical knowledge. Follow these simple steps to update your company information, contact details, logo, and other content.

## Table of Contents
1. [Changing Company Name and Logo](#changing-company-name-and-logo)
2. [Updating WhatsApp Contact Number](#updating-whatsapp-contact-number)
3. [Updating Map Location](#updating-map-location)
4. [Changing Basic Text Content](#changing-basic-text-content)
5. [Google Calendar Configuration](#google-calendar-configuration)
6. [Updating Images](#updating-images)
7. [Social Media Links](#social-media-links)
8. [Setting Up Google Calendar Integration (Optional)](#setting-up-google-calendar-integration-optional)

## Changing Company Name and Logo

### Company Name
The company name appears in several places throughout the website. Here's how to change it:

1. **Main Website Title and SEO**:
   - Open file: `index.html`
   - Around line 13, find and change:
     ```html
     <title>Cloud's Dental Hospital - Leading Dental Healthcare in Indonesia</title>
     ```
   - Also update the meta tags (lines 6-12) with your company information

2. **Header Logo Text**:
   - In the same file `index.html`, around line 154, change:
     ```html
     <h1>Cloud's Dental Hospital</h1>
     ```

3. **Footer Logo Text**:
   - In `index.html`, around line 213, change:
     ```html
     <h2>Cloud's Dental Hospital</h2>
     ```
   - Also update the copyright information at the bottom of the page (around line 253)

4. **Admin Dashboard**:
   - Open file: `admin/index.html`
   - Around line 23, find and change:
     ```html
     <h3>Cloud's Dental</h3>
     ```

### Logo Image
To change the logo:

1. **Prepare your new logo**:
   - Create a GIF or PNG image file
   - Recommended size: approximately 120px × 60px
   - Name it `logo.gif` or `logo.png`

2. **Replace the existing logo**:
   - Navigate to the `images` folder
   - Backup the existing `logo.gif` file by renaming it (e.g., to `logo-old.gif`)
   - Copy your new logo file into this folder

## Updating WhatsApp Contact Number

To change the WhatsApp contact number for direct consultations:

1. Open file: `index.html`
2. Find the WhatsApp link (around line 185):
   ```html
   <a href="https://wa.me/60123456789" class="info-card whatsapp-card" target="_blank" rel="noopener noreferrer" data-aos="fade-up" data-aos-delay="100">
   ```
3. Replace `60123456789` with your WhatsApp number (including country code, without the + symbol)
   - For example, use `60712345678` for a Malaysian number (+60 7 1234 5678)

## Updating Map Location

The website uses a Waze map embed. To update with your location:

1. Open file: `index.html`
2. Find the iframe for the Waze map (around line 198):
   ```html
   <iframe src="https://embed.waze.com/iframe?zoom=16&lat=1.498333&lon=103.818001&ct=livemap" width="600" height="450" allowfullscreen></iframe>
   ```
3. Update the latitude and longitude parameters:
   - `lat=1.498333` - replace with your location's latitude
   - `lon=103.818001` - replace with your location's longitude

To find your coordinates:
1. Go to [Google Maps](https://www.google.com/maps/)
2. Find your location on the map
3. Right-click on the exact location
4. Select "What's here?"
5. The coordinates will appear at the bottom of the screen

Alternatively, you can also:
1. Get a new embed code from Waze: [Waze Livemap](https://www.waze.com/live-map)
2. Click on your location
3. Click "Share"
4. Select "Embed" tab
5. Copy the new iframe code and replace the existing one

## Changing Basic Text Content

### Homepage Text
To update main text content:

1. Open file: `index.html`
2. Around line 166, find and modify the appointment section text:
   ```html
   <h2 class="section-title">Buat Janji Temu</h2>
   <p>Jadwalkan kunjungan Anda dengan spesialis kami. Kami akan menghubungi Anda dalam 24 jam.</p>
   ```

3. Update WhatsApp consultation text (around line 190):
   ```html
   <h3>Konsultasi Langsung</h3>
   <p>Tidak ingin membuat janji temu online? Hubungi kami langsung melalui WhatsApp untuk konsultasi cepat.</p>
   ```

4. Update Map overlay text (around line 197):
   ```html
   <h3>Temukan Kami di Waze</h3>
   ```

5. Update footer text, including the company description (around line 215):
   ```html
   <p>Menyediakan perkhidmatan pergigian bertaraf dunia untuk rakyat Malaysia sejak 2005.</p>
   ```

### Admin Portal Text
To change text in the admin dashboard:

1. Open file: `admin/index.html`
2. You can update various section titles and labels throughout the file as needed

## Google Calendar Configuration

To configure Google Calendar integration:

1. Open file: `server/config/calendar-config.js`
2. Update the calendar settings as needed:
   ```js
   // Calendar settings
   const calendarSettings = {
     // Calendar ID (use 'primary' for the main calendar)
     CALENDAR_ID: 'primary',
     
     // Set to proper timezone for your region
     TIMEZONE: 'Asia/Kuala_Lumpur',
   };
   ```

3. The timezone should match your clinic's location. Common timezones include:
   - `Asia/Kuala_Lumpur` (Malaysia)
   - `Asia/Jakarta` (Indonesia)
   - `Asia/Singapore` (Singapore)
   - `Asia/Bangkok` (Thailand)

4. If you want to use a specific Google Calendar rather than your primary one, replace `'primary'` with the Calendar ID found in your Google Calendar settings

## Updating Images

### Background and Feature Images
To replace various images on the website:

1. Prepare your new images with similar dimensions to the current ones
2. Navigate to the `images` folder
3. Replace the following images as needed (keep the same filenames):
   - `logo.gif` - Company logo
   - `hero-bg.jpg` - Hero section background
   - `appointment.jpg` - Appointment section image
   - `hospital-building.jpg` - Hospital building image

### Doctor Photos
Doctor photos are stored in the `images/doctors` folder:

1. Prepare square photos (1:1 ratio) of your doctors
2. Photos should be professional and in uniform if possible
3. To add new doctors, use the admin dashboard after logging in

## Social Media Links

To update social media links:

1. Open file: `index.html`
2. Find the social media links section in the footer (around line 217):
   ```html
   <div class="social-links">
       <a href="#"><i class="fab fa-facebook-f"></i></a>
       <a href="#"><i class="fab fa-twitter"></i></a>
       <a href="#"><i class="fab fa-instagram"></i></a>
       <a href="#"><i class="fab fa-linkedin-in"></i></a>
   </div>
   ```
3. Replace the `#` placeholder with your actual social media URLs
   - For example: `<a href="https://www.facebook.com/yourpage"><i class="fab fa-facebook-f"></i></a>`

## Setting Up Google Calendar Integration (Optional)

If you need to create your own Google Calendar integration from scratch or replace the existing credentials, follow these simple steps:

### 1. Create a Google Cloud Project

1. Go to the [Google Cloud Console](https://console.cloud.google.com/)
2. Sign in with your Google account (preferably the same account you use for your business calendar)
3. Click the project dropdown at the top of the page
4. Click "New Project"
5. Enter a name for your project (e.g., "Dental Booking System")
6. Click "Create"

### 2. Enable the Google Calendar API

1. In your new project, go to the Navigation Menu (☰) on the left
2. Click on "APIs & Services" > "Library"
3. Search for "Google Calendar API"
4. Click on "Google Calendar API" in the results
5. Click "Enable"

### 3. Create Credentials

1. After enabling the API, click on "Create Credentials"
2. Under "Which API are you using?", select "Google Calendar API"
3. For "What data will you be accessing?", select "User data"
4. Click "Next"

5. On the "OAuth consent screen" setup:
   - Select "External" (unless you have Google Workspace)
   - Click "Create"
   - Fill in required fields:
     - App name: Your dental clinic name
     - User support email: Your email address
     - Developer contact information: Your email address
   - Click "Save and Continue"

6. On the "Scopes" screen:
   - Click "Add or Remove Scopes"
   - Find and select the scope: `https://www.googleapis.com/auth/calendar`
   - Click "Update"
   - Click "Save and Continue"

7. On "Test users" screen:
   - Click "Add Users"
   - Add your email address
   - Click "Save and Continue"
   - Click "Back to Dashboard"

8. Now, go to "Credentials" in the left sidebar
9. Click "Create Credentials" and select "OAuth client ID"
10. For "Application type", choose "Desktop app"
11. Enter a name (e.g., "Dental Booking Client")
12. Click "Create"
13. You'll see a popup with your credentials. Click "Download JSON"

### 4. Update Your Application

1. Open the downloaded JSON file with a text editor (like Notepad)
2. Open your application's file: `server/config/calendar-config.js`
3. Replace the content of the `credentials` object with the content from your downloaded JSON file. The structure should be similar:

```js
const credentials = {
  "installed": {
    "client_id": "YOUR_CLIENT_ID.apps.googleusercontent.com",
    "project_id": "YOUR_PROJECT_ID",
    "auth_uri": "https://accounts.google.com/o/oauth2/auth",
    "token_uri": "https://oauth2.googleapis.com/token",
    "auth_provider_x509_cert_url": "https://www.googleapis.com/oauth2/v1/certs",
    "client_secret": "YOUR_CLIENT_SECRET",
    "redirect_uris": ["http://localhost:3000/api/calendar/oauth2callback"]
  }
};
```

4. Important: Make sure the `redirect_uris` stays as `["http://localhost:3000/api/calendar/oauth2callback"]` even if your downloaded file has different values

### 5. First-Time Authentication

After updating the credentials:

1. Restart your application
2. Log in to the admin dashboard
3. Go to "Settings"
4. Click "Connect Google Calendar"
5. Follow the Google sign-in prompts that appear
6. Grant permission when asked to allow the application to access your calendar

This process needs to be done only once. After successful authentication, the system will remember your calendar connection and automatically sync all appointments.

### Important Notes

- You should use the same Google account for both creating the Cloud project and connecting the calendar
- If you use a specific calendar rather than your primary calendar, update the `CALENDAR_ID` in the settings
- The free tier of Google Cloud Platform has generous limits and should be sufficient for most dental practices

