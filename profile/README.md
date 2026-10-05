<div align="center">

# 🌐 Dilnova Commerce Hub
### Enterprise Multi-Tenant eCommerce & Physical Point of Sale (POS) Platform

> Powering specialized merchant storefronts, rapid in-store retail checkout, real-time inventory telemetry, and global multi-currency commerce under a unified architecture.

**[🌐 Live Production Platform](https://www.dilnova.pp.ua)** • **[🏪 Featured Merchant Stores](https://www.dilnova.pp.ua/vendors)** • **[🎬 Watch 4-Minute Demo Video](https://youtu.be/VR7U_lXBiYc?si=dnR7-WKQR3plKxTx)**

---

`Next.js 16 App Router` • `TypeScript (Strict)` • `Drizzle ORM` • `PostgreSQL (Supabase)` • `Clerk RBAC` • `Tailwind CSS`

---

</div>

## 🌍 Welcome to Dilnova

**Dilnova Commerce Hub** is an enterprise-grade multi-vendor eCommerce ecosystem engineered from the ground up for high-velocity digital and physical retail. From seamless multi-vendor online checkout journeys to physical counter Point of Sale (POS) operations with printable thermal receipts, Dilnova bridges the gap between digital storefronts and brick-and-mortar retail counters.

---

## 🚀 Core Platform Capabilities

### 🏪 1. Multi-Tenant Storefront Isolation
Every registered merchant operates an independent digital storefront with custom branding, localized catalogs, and stock availability badges. Every database query is strictly scoped by Clerk `orgId`, ensuring **zero cross-tenant data exposure**.

### ⚡ 2. Integrated Retail Point of Sale (POS) Register
Designed for retail physical counters and tablet checkout:
- Instant barcode lookup and product quick-select grid
- Real-time itemized tax computation
- Tendered cash handling with dynamic change due calculation
- Instant 58mm thermal receipt generation with barcode footers

### 💱 3. Dynamic Multi-Currency Presentment Engine
Global shoppers can seamlessly toggle presentment currencies (e.g., **LKR ↔ USD**) in real time with cached exchange rates, automatically re-calculating product prices, cart line items, and tax classes.

### 📦 4. Warehouse Inventory Telemetry & Audit Trails
Store administrators track stock across SKUs and physical warehouse bin storage locations (e.g., `Bin A1-S02`), receive automated low-stock warnings, and review immutable movement audit logs covering inbound restocks, customer orders, and POS disbursements.

### 🚚 5. Post-Purchase Transparency & Automated Invoices
- **Enterprise Tax Invoices**: Print-ready invoices itemized by tax class with bank wire verification slips.
- **Real-Time Tracking**: 3-stage live courier milestone stepper (`Dispatched` → `In Transit` → `Delivered`).

### 🛡️ 6. Superadmin SaaS Governance & GDPR Compliance
Platform superadmins oversee global tenant analytics, manage multi-tier SaaS subscriptions (Starter, Growth, Enterprise), and execute automated GDPR customer data exports (`.json`) backed by cryptographic SHA-256 integrity verification.

---

## 💻 Engineering Architecture

```mermaid
graph TD
    Client["Browser / Tablet / Mobile POS"] --> Proxy["Next.js 16 proxy.ts (CSP Nonces & Auth Routing)"]
    Proxy --> App["Next.js 16 App Router (React 19 Server Components)"]
    App --> Clerk["Clerk Authentication (Tenant RBAC orgId Scoping)"]
    App --> Drizzle["Drizzle ORM (Type-Safe Query Layer)"]
    Drizzle --> Supabase["Supabase PostgreSQL (Pooled Connections)"]
    App --> Edge["Vercel Edge CDN Deployment (hnd1 Region)"]
