# NetSuite Integration User Setup Guide

This guide explains how to set up an integration user in NetSuite for use with the GI process, and details the necessary permissions required for the NetSuiteClient to function correctly.

## 1. Create an Integration Record in NetSuite

1. **Log in to NetSuite** as an administrator.
2. Navigate to **Setup > Integrations > Manage Integrations > New**.
3. Enter a **Name** (e.g., `GI Integration`).
4. Ensure **State** is set to **Enabled**.
5. Note the **Consumer Key** and **Consumer Secret** generated after saving.

## 2. Create a Role for API Access

1. Go to **Setup > Users/Roles > Manage Roles > New**.
2. Name the role (e.g., `GI API Role`).
3. Under **Permissions**, add the following:
   - **Lists**:
     - Customers (View)
     - Items (View)
   - **Transactions**:
     - Sales Order (View)
   - **Reports**:
     - SuiteAnalytics Workbook (Edit)
   - **Setup**:
     - User Access Token (Full)
     - Web Services (Full)
     - SuiteAnalytics Connect (Full)
4. Under **Permissions > Setup**, ensure **Log in using Access Tokens** is enabled.
5. Save the role.


## 3. Create an Access Token

1. Go to **Setup > Users/Roles > Access Tokens > New**.
2. Select the **Application Name** (integration record), **User**, and **Role** created above.
3. Save and note the **Token ID** and **Token Secret**.

## 4. Required API Permissions

The GI client uses SuiteQL and requires the following:
- **SuiteAnalytics Connect** (for SuiteQL queries)
- **Web Services**
- **View access** to Customers, Items, Sales Orders

## 5. Configure the GI Client

- **Account ID**: Your NetSuite account ID (e.g., `1234567_SB1`)
- **Consumer Key/Secret**: From the integration record
- **Token ID/Secret**: From the access token



For more details, see the NetSuite [SuiteQL documentation](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/section_1556926717.html) and [Token-based Authentication](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/section_1546605846.html).
