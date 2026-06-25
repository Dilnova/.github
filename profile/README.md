<div align="center">
  <h1>Dilnova Commerce Hub</h1>
  <p><em>The Enterprise Multi-Vendor Marketplace & Operations Sandbox</em></p>
</div>

---

## 🏢 About Dilnova

Dilnova is the mother company and central architectural hub powering a diverse ecosystem of specialized storefronts. We provide an enterprise-grade, multi-tenant eCommerce infrastructure that allows autonomous vendors to operate under one unified platform while maintaining strict data isolation.

### Our Core Ecosystem
* **Distar Hardware:** Industrial tools, heavy-duty machinery, and contractor supplies.
* **Distar Nursery:** Botanical supplies, exotic plants, and agricultural consulting.
* **Distar Tech:** High-performance developer workstations and IT infrastructure.
* **Dilstar Services:** Professional consulting and expert booking services.

---

## 🚀 Key Platform Features

* **Multi-Tenant Architecture:** Secure data isolation utilizing Clerk Organization IDs (`orgId`), ensuring every registered brand or vendor has a private, autonomous workspace.
* **Unified Checkout & Point of Sale (POS):** A robust billing register capable of real-time stock depletion, branch context validation, and printable thermal receipts.
* **Premium Inventory Management (IMS):** 
  * Centralized tracking of SKUs and bin locations.
  * Automated low-stock alerts and threshold warnings.
  * Supplier directory management and multi-branch inventory allocation.
* **SEO & Performance First:** Server-side rendered catalog listings using Next.js App Router for blazingly fast interactions and semantic schema validation.

---

## 🛡️ Role-Based Access Control (RBAC)

Dilnova utilizes a strict three-tier authorization model:

### 1. Platform Superadmin
* **Access:** Global `/superadmin` console.
* **Capabilities:** Configure system-wide parameters (system name, logos, custom storefront toggles, media limits, and platform pricing plans).

### 2. Organization Administrator (`org:admin`)
* **Access:** Full vendor dashboard (`/vendor/products` & `/admin`).
* **Capabilities:** Manage vendor memberships, assign branch roles, oversee the entire product catalog, adjust central inventory, and execute POS transactions across any branch.

### 3. Organization Member (`org:member`)
* **Access:** Restricted operational dashboard (`/vendor`).
* **Capabilities:** Process POS transactions (restricted to assigned branches), add new catalog listings, and update basic storefront profile metadata.

---

## 🛠️ Tech Stack

* **Framework:** [Next.js](https://nextjs.org/) (App Router, Server Actions)
* **Authentication:** [Clerk](https://clerk.com/) (Multi-tenant B2B Organizations)
* **Database:** PostgreSQL (via [Supabase](https://supabase.com/))
* **ORM:** [Drizzle ORM](https://orm.drizzle.team/)
* **Media Storage:** [Cloudinary](https://cloudinary.com/) (Signed Uploads)
* **Styling:** Tailwind CSS + UI Components
* **Caching:** Upstash Redis

---

## 💻 Getting Started

### Prerequisites
* Node.js (v18+)
* pnpm (v8+)
* PostgreSQL Database
* Clerk Account (with Organizations enabled)
* Cloudinary Account

### 1. Environment Setup
Create a `.env.local` file in the root directory:

```env
# Authentication (Clerk)
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_test_...
CLERK_SECRET_KEY=sk_test_...

# Database (Supabase / Postgres)
DATABASE_URL=postgresql://postgres:[PASSWORD]@pooler.supabase.com:6543/postgres
MIGRATION_DATABASE_URL=postgresql://postgres:[PASSWORD]@pooler.supabase.com:5432/postgres
NEXT_PUBLIC_SUPABASE_URL=https://[PROJECT_REF].supabase.co
NEXT_PUBLIC_SUPABASE_PUBLISHABLE_KEY=sb_publishable_...
SUPABASE_SERVICE_ROLE_KEY=...

# Media (Cloudinary)
NEXT_PUBLIC_CLOUDINARY_CLOUD_NAME=...
CLOUDINARY_API_KEY=...
CLOUDINARY_API_SECRET=...
```

### 2. Installation & Database Migrations
```bash
# Install packages
pnpm install

# Push database schema to your Postgres instance
pnpm db:migrate

# Start the development server
pnpm dev
```

---

## 📄 License

Copyright © Dilnova. All rights reserved.
