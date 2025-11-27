# IAM-Implementation-Script-Tool

This tool automates the process of generating optimized IAM zone tags for both websites and email newsletters. It is designed specifically for Indiegraf Media.

## Features

1. **Secure Connection:** Connects to the AdButler API (includes a Simulation Mode for testing without an API key).

2. **Tag Cleaning:** automatically removes the blocking JavaScript library calls from individual website zone tags.

3. **Lazy Loading:** Generates the mandatory Global Header Script that handles lazy loading for all zones.

4. **Tag Customization:**

    - **Web:** Select between Async (recommended), Standard, or Async 1.1 tag formats.

    - **Email:** Adds a field to input your ESP's (Email Service Provider) unique user ID variable (EUID) and ensures image tags are responsive.

5. Bulk Copy: Easily copy all generated tags at once.

## How to Use

1. **Open the Tool:** Launch ```index.html``` in any modern web browser.

2. **Enter Publisher ID:** Input the unique Publisher ID (e.g., ```185279```).

3. **Select Tag Type:** Choose your preferred website tag format (Async is default).

4. **Enter EUID (Optional):** If you are generating newsletter tags, enter your email platform's merge tag (e.g., ```%CONTACTID%```, ```*|UNIQID|*```, ```{{ contact.id }})```. This will automatically update all email tags in real-time.

5. **Click "Fetch & Process":** The tool will generate the cleaned tags.

6. **Copy & Paste:**

    - Copy the **Global Header Script** and place it in the ```<head>``` of the website using the Indiegraf code injector.

    - Copy individual zone tags and place them in your CMS or Email Template.

## Technical Notes

- **API CORS:** If you use a real API key, the browser might block the request due to CORS (Cross-Origin Resource Sharing) policies. This is normal for browser-based tools accessing third-party APIs directly. The tool includes a robust Simulation Mode that generates correct tag structures using mock data if the API fails or if no key is provided.

- **Responsiveness:** Email tags are generated with ```style="display:block; max-width:100%; height:auto;"``` to ensure they scale correctly on mobile devices.
