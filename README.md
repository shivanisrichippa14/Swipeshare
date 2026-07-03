# SwipeShare 📚

SwipeShare is a high-performance, peer-to-peer textbook and study resource exchange marketplace designed specifically for university students. Built on the **MERN Stack** (MongoDB, Express, React, Node.js), SwipeShare features a dual-client layout: a student-facing storefront and a comprehensive administrative dashboard.

The platform integrates dual payment processors (Stripe & Razorpay), synchronous image CDN garbage collection, and offline-resilient local state management to ensure a seamless resource-sharing experience.

---

## 🛠️ Tech Stack & Key Services

*   **Frontend storefront & admin deck:** React.js, Tailwind CSS, Context API (`ShopContext`), Axios, Lucide Icons
*   **Backend engine:** Node.js, Express.js, JWT authentication middleware, Multer (file uploads)
*   **Database:** MongoDB Atlas (Mongoose ODM)
*   **Cloud Storage & CDN:** Cloudinary SDK
*   **Payment Gateways:** Stripe API & Razorpay SDK

---

## ⚙️ System Architecture

```mermaid
graph TD
    UserClient[React User Storefront] -->|Listings / Cart / Checkout| Backend[Express App / Node.js]
    AdminClient[React Admin Dashboard] -->|Verify Listings / Manage Orders| Backend
    Backend -->|Asset Streaming| Cloudinary[Cloudinary CDN]
    Backend -->|Persist Data| MongoDB[(MongoDB Atlas)]
    Backend -->|Process Cards/Sass| Stripe[Stripe API]
    Backend -->|Process UPI/Netbanking| Razorpay[Razorpay API]
