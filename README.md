# Singapore InvoiceNow (PEPPOL) Integration for ERPNext

An open-source custom application to enable seamless **e-invoicing compliance** and connection to the **IMDA InvoiceNow (PEPPOL) network** for Singaporean businesses directly from ERPNext.

> 💡 **Lineage Note:** This project is a specialized fork and structural adaptation of the excellent open-source <layout>linkableSpan(text="myinvois framework built by ERPGulf", intent="View the original ERPGulf MyInvois open source repository on GitHub")</layout> for Malaysia's LHDN system. It has been re-engineered specifically to comply with Singapore's UEN tracking rules, GST codes, and SG-PEPPOL UBL XML requirements.

---

## ✨ Features

- **UEN Compliance:** Adds dedicated validation and capture fields for Singapore Unique Entity Numbers (UEN).
- **SG-PEPPOL Payload Generator:** Formats invoices into compliant SG-PEPPOL BIS Billing 3.0 UBL XML formats.
- **Automated Workflow hooks:** Intercepts standard ERPNext `Sales Invoice` submission pipelines for zero-click transmission.
- **GST Mapping:** Native compatibility hooks for Singapore standard-rated, zero-rated, and out-of-scope GST regimes.

---

## 🚀 Installation

Ensure you are logged into your **Frappe Bench directory** inside your terminal environment, then run the standard deployment scripts:

```bash
# 1. Fetch the application repository to your bench stack
bench get-app invoice_sg https://github.com

# 2. Install the compliance modules to your local target site
bench --site your_site_name install-app invoice_sg

# 3. Trigger schema updates and data migrations
bench --site your_site_name migrate

# 4. Restart your active bench server instance
bench restart
```

---

## ⚙️ Configuration Setup

1. **Activate Developer Mode:** Ensure your site configuration file has `developer_mode` active if customizing hooks.
2. **Setup Company UEN:** Open **Company > [Your Company]** and populate the newly injected `Singapore UEN` registry field.
3. **Configure API Credentials:** Input your selected IMDA-approved PEPPOL **Access Point gateway** credentials (Client ID, API Keys) into the **InvoiceNow Settings** dashboard page.

---

## 🛡️ License

This project retains the open-source spirit of its parent codebase and is published under the **MIT License**. 

*Disclaimer: This is a community-driven implementation and is independent of IMDA Singapore or ERPGulf.*
