# 🚀 Automated Daily Executive Brief System

A dynamic, multi-user automation system built with **n8n** that delivers personalized morning briefings including local weather and global news headlines via a Telegram Bot.

## 🌟 Key Features
- **Dynamic Personalization:** Uses Google Sheets as a database to handle multiple users simultaneously.
- **Smart Geocoding:** Automatically converts user-provided city names into GPS coordinates using the Open-Meteo Geocoding API.
- **Automated Weather:** Fetches real-time meteorological data (Temperature & Wind speed).
- **News Aggregator:** Pulls global headlines via RSS and uses a **JavaScript Code Node** to summarize and format the top 3 stories.
- **Self-Service Onboarding:** Integrated with **Google Forms** so new users can subscribe without manual intervention.
- **System Logging:** Maintains a professional log in Google Sheets to track successful deliveries and system errors.

## 🛠️ Technical Stack
- **Engine:** n8n (Self-Hosted)
- **Database:** Google Sheets API
- **Onboarding:** Google Forms
- **Communication:** Telegram Bot API
- **Data Sources:** Open-Meteo API (Weather) & BBC World News (RSS)
- **Logic:** JavaScript (Node.js) for data aggregation

## 📋 How It Works
1. **Trigger:** The workflow fires every morning via a `Schedule Trigger`.
2. **Fetch:** It reads the subscriber list from Google Sheets.
3. **Process:** For each user, it finds GPS coordinates, fetches local weather, and grabs global news.
4. **Format:** A custom JS script "squashes" multiple news items into a single readable list.
5. **Delivery:** Sends a formatted Telegram message to the user's specific `Chat ID`.
6. **Log:** Records the execution timestamp and status in the `System_Logs` sheet.
   <img width="1919" height="1079" alt="Screenshot 2026-02-22 032610" src="https://github.com/user-attachments/assets/d95480c0-882d-409f-afe2-5c45c9f9d369" />


## 🚀 Setup & Installation
1. Import the `daily_brief_workflow.json` into your n8n instance.
2. Set up a Google Cloud Project and enable the Sheets and Drive APIs.
3. Create a Telegram Bot via @BotFather and obtain your API Token.
4. Connect your credentials in n8n.
5. Link your Google Form to the spreadsheet to begin accepting subscribers.

---
*Created by Fatima Junaid*
