# Google Analytics 4 (GA4) Integration Setup Guide


## Prerequisites

1. **Google Analytics 4 Property** configured for your website
2. **Google Cloud Project** with Analytics Data API enabled
3. **Service Account**  for API access
4. **GA4 Property ID** (format: `properties/123456789`)

---

## Setup Steps

### 1. Enable Google Analytics Data API

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Select or create a project
3. Navigate to **APIs & Services** → **Library**
4. Search for "Google Analytics Data API"
5. Click **Enable**

### 2. Create Service Account 

1. Go to **IAM & Admin** → **Service Accounts**
2. Click **Create Service Account**
3. Name: `ga4-etl-service`
4. Click **Create and Continue**
5. Grant role: **Viewer**
6. Click **Done**
7. Click on the service account → **Keys** tab
8. Click **Add Key** → **Create New Key** → **JSON**
9. Download and save the JSON key file securely

### 3. Grant Analytics Access

1. Go to [Google Analytics](https://analytics.google.com/)
2. Navigate to **Admin** (bottom left)
3. Select your property
4. Click **Property Access Management**
5. Click **+ Add users**
6. Add your service account email (e.g., `ga4-etl-service@project-id.iam.gserviceaccount.com`)
7. Grant **Viewer** role
8. Click **Add**

### 4. Get Your GA4 Property ID

1. In Google Analytics, go to **Admin**
2. Under **Property**, click **Property Settings**
3. Copy your **Property ID** (numeric value like `123456789`)
4. Format it as: `properties/123456789`


## Additional Resources

- [Google Analytics Data API Documentation](https://developers.google.com/analytics/devguides/reporting/data/v1)
- [GA4 Dimensions & Metrics Reference](https://developers.google.com/analytics/devguides/reporting/data/v1/api-schema)
- [Service Account Authentication](https://cloud.google.com/docs/authentication/production)

