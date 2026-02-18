# Magento Integration User Setup Guide

This guide explains how to set up an integration user in Magento for use with the GI process, and details the necessary permissions required for the MagentoClient to function correctly.

## 1. Create an Integration User in Magento

1. **Log in to Magento Admin Panel** as an administrator.
2. Go to **System > Extensions > Integrations**.
3. Click **Add New Integration**.
4. Fill in the required fields:
   - **Name**: e.g., `ETL Integration`
   - **Email**: (your contact email)
   - **Callback URL** and **Identity Link URL**: (leave blank unless required)
5. Under **API**, click **Add Resource Access**.

## 2. Required API Permissions

The ETL client requires access to the following Magento REST API resources:

- **Products**: `GET /V1/products`
- **Customers**: `GET /V1/customers/search`
- **Orders**: `GET /V1/orders`
- **Store Config** (for connection test): `GET /V1/store/storeConfigs`

### Recommended Resource Access
Grant the following permissions under the API section:

- **Catalog > Inventory > Products**: _Read_
- **Sales > Operations > Orders**: _Read_
- **Customers > All Customers**: _Read_
- **Stores > Settings > All Stores**: _Read_ (for store config)

> **Note:** You may grant access to the entire resource tree for testing, but for production, restrict to only the above resources for security.

## 3. Activate the Integration

1. After saving, click **Activate** next to your new integration.
2. Approve the permissions and copy the **Access Token** (API Token).



For more details, see the Magento [official documentation](https://developer.adobe.com/commerce/webapi/get-started/integration/).
