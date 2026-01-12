# Social Media Campaign Tracker
**A Full-Stack Analytics Platform for Marketing Performance**

A comprehensive web application designed to centralize marketing data, track real-time engagement, and visualize campaign performance. Built with a focus on data integrity, relational modeling, and user-driven analytics.

## Key Features

* **Secure Authentication:** Integrated **Google OAuth 2.0** for secure user login and profile management.
* **Hierarchical Data Management:** Full CRUD functionality for Channels, Campaigns, and Posts, utilizing Foreign Key relationships to maintain strict referential integrity.
* **Granular Performance Tracking:** Logic to record specific engagement metrics (impressions, clicks, shares, and saves) for every individual content piece.
* **Advanced Analytics Dashboard:** Dynamic filtering by platform (Channel) and date range to generate aggregated performance reports (ROI and CTR).

## Tech Stack

* **Frontend:** React.js, JavaScript (ES6+), CSS3.
* **Backend:** Django REST Framework (Python).
* **Database:** PostgreSQL (Relational schema with 4 core entities).
* **API:** RESTful architecture for seamless client-server communication.

## Data Architecture

The system is powered by an optimized relational model designed for scalable reporting:

* **Channel:** Standalone entity representing the platform (e.g., Instagram, TikTok, LinkedIn).
* **Campaign:** Linked to Channels; manages budgets, strategic objectives, and timelines.
* **Post:** Individual content units tied to specific parent campaigns.
* **PostMetrics:** A dedicated table for time-series performance data, enabling multi-level KPI aggregation.

## API Documentation (DRF)

The backend exposes a robust API to serve the frontend:
* `GET /api/channels/` - Retrieves all configured marketing channels.
* `POST /api/campaigns/` - Creates a new campaign linked to a specific channel.
* `GET /api/metrics/aggregate/` - Returns calculated metrics (CTR/Engagement) filtered by date or platform.

## Setup and Installation

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/mdiazgarr/social-media-campaign-tracker.git](https://github.com/mdiazgarr/social-media-campaign-tracker.git)
    ```
2.  **Environment Variables:** Create a `.env` file with your `GOOGLE_CLIENT_ID`, `SECRET_KEY`, and database credentials.
3.  **Backend (Django):**
    ```bash
    pip install -r requirements.txt
    python manage.py migrate
    python manage.py runserver
    ```
4.  **Frontend (React):**
    ```bash
    npm install
    npm start
    ```

## Future Improvements
* **Dockerization:** Containerizing the app for easier deployment and environment consistency.
* **Automated Data Ingestion:** Integrating with Meta/TikTok APIs to automate metric collection.
* **Predictive Analytics:** Using historical data to forecast campaign ROI using Machine Learning.
