*Intuz — Your automation partner, one workflow at a time.*

<p align="center">
  <picture>
    <img alt="Banner Image" src="https://github.com/user-attachments/assets/210f97fc-0fce-404a-b647-7dfe1302cd37" />
  </picture>
</p>

[Intuz](https://www.intuz.com) helps organizations orchestrate AI, automation, and enterprise systems through scalable workflows. Our repository showcases proven implementations across healthcare, operations, customer support, document processing, sales, and back-office functions, enabling teams to accelerate automation initiatives without starting from scratch.

[N8N Creator](https://n8n.io/creators/intuz/) · [Enterprise AI Development](https://www.intuz.com/ai/) · [AI Consulting Company](https://www.intuz.com/company/) · [For Custom Workflow Automation](https://www.intuz.com/get-started/)

# Automate QuickBooks invoicing & customer creation from Airtable sales orders

This n8n template from Intuz provides a complete solution to automate your entire invoicing process.

It intelligently syncs confirmed sales orders from your Airtable base to QuickBooks, automatically creating new customers if they don’t exist before generating a perfectly matched invoice. It then logs all invoice details back into Airtable, creating a flawless, end-to-end financial workflow.

## Use Cases

### 1. Accounting & Finance Teams

- Automatically generate QuickBooks invoices from new orders confirmed in Airtable.
- Keep all invoices and customer details synced across systems in real time.

### 2. Sales & Operations Teams

- Track order status and billing progress directly from Airtable without switching platforms.
- Ensure every confirmed sale automatically triggers an invoice in QuickBooks.

### 3. Business Owners / Admins

- Eliminate double-entry between Airtable and QuickBooks.
- Maintain accurate, audit-ready financial records with minimal effort.

## How it works

1. **Trigger from Airtable:** The workflow starts instantly when a sales order is ready to be invoiced in your Airtable base (triggered via a webhook).

2. **Check for Customer in QuickBooks:** It searches your QuickBooks account to see if the customer from the sales order already exists.

3. **Create New Customer (If Needed):** If the customer is not found, it automatically creates a new customer record in QuickBooks using the details from your Airtable Customers table.

4. **Create QuickBooks Invoice:** Using the correct customer record (either existing or newly created), it gathers all order line items from Airtable and generates a detailed invoice in QuickBooks.

5. **Log Invoice Back to Airtable:** After the invoice is successfully created, the workflow updates your Airtable base by adding a new record to your Invoices & Payments table and updating the original Confirmed Orders record with the new QuickBooks Invoice ID, marking it as synced.

## Key Requirements to Use This Template

1. **n8n Instance:** An active n8n account (Cloud or self-hosted).
2. **Airtable Base:** An Airtable base on a **Pro** plan or higher with tables for Confirmed Orders, Customers, Order Lines, Product & Service, and Invoices & Payments. Field names must match those in the setup guide.
3. **QuickBooks Online Account:** An active QuickBooks Online account with API access.

## Step-by-Step Setup Instructions

### Step 1: Import and Configure the n8n Workflow

- **Import Workflow:** In n8n, import the `Client-Quickbook-Invoices-via-AirTable.json` file.
- **Get Webhook URL:** Click on the first node, **Webhook**. Copy the Test URL. Keep this n8n tab open.
- **Configure Airtable Nodes:** There are six Airtable nodes. For each one, connect your Airtable credentials and select the correct Base and Table.
- **Configure QuickBooks Nodes:** There are four QuickBooks-related nodes. For each one, connect your QuickBooks Online credentials.
- **CRITICAL:** Click on the **Create Invoice URL** (HTTP Request) node. You must edit the URL and replace the placeholder number (`9341455145770046`) with your own QuickBooks Company ID. (Find this in your QuickBooks account settings under **Billing & Subscription**.)
- **Save and Activate:** Click **Save**, then toggle the workflow to **Active**. After activating, copy the new **Production URL** from the Webhook node.

## Customization Guide

You can adapt this template for various workflows by tweaking a few nodes:

- **Use a different Airtable Base:** Update the Base ID and Table ID in all Airtable nodes (Get Orders Records, Get Customer Details, Get Products, etc.).
- **Switch from Sandbox to Live QuickBooks:** Replace the Sandbox company ID and endpoint in the **Create Invoice URL** node with your production QuickBooks company ID.
- **Add more invoice details:** Edit the Code and Parse in HTTP nodes to include additional fields (like Tax, Shipping, or Notes).
- **Support multiple currencies:** Add a Currency field mapping in both Airtable and QuickBooks nodes.

## FAQ

**Is this template free to use?**
Yes. It's an open-source n8n workflow published by Intuz — copy the workflow JSON from this repo and import it into your own n8n instance at no cost.

**Do I need a paid n8n plan to run this?**
No. It runs on n8n's free self-hosted Community Edition or on n8n Cloud. You'll need your own Airtable and QuickBooks credentials, not a specific n8n pricing tier.

**What happens if the customer already exists in QuickBooks?**
The workflow reuses that customer. It searches QuickBooks first; if no match is found, it creates the customer from your Airtable Customers table, then generates the invoice and writes the QuickBooks Invoice ID back to Airtable.

## Related n8n templates from Intuz

- [Automate expense reporting from Airtable to QuickBooks](https://github.com/Intuz-production/Airtable-QuickBooks-Expense-Automation)
- [Automate full-cycle invoicing from Airtable to QuickBooks and Stripe](https://github.com/Intuz-production/QuickBooks-Invoice-Payment-Automation)
- [Automate QuickBooks customers & sales receipts generation from a Google Sheet](https://github.com/Intuz-production/Automate-QuickBooks-Customer-Sales-Receipt-Creation)

[See all of Intuz's free n8n templates](https://www.intuz.com/n8n-workflow-automation-templates/)

## Connect with us

Intuz is a USA-based AI & workflow automation company with 16+ years of experience building custom AI-enabled workflow automations for SMBs and Enterprises, specializing in agentic AI, LLM integrations, and CRM/ERP sync across Healthcare, FinTech, eCommerce, Manufacturing, and Real Estate.

* **Website:** [https://www.intuz.com](https://www.intuz.com)
* **Email:** [getstarted@intuz.com](mailto:getstarted@intuz.com)
* **LinkedIn:** https://www.linkedin.com/company/intuz/
* **Get Started:** https://n8n.partnerlinks.io/intuz

## For Custom Workflow Automation

[Click here - Get Started](https://www.intuz.com/get-started/)
