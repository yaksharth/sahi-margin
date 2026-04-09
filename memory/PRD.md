# Sahi Margin — PRD

## Problem Statement
Build a React SaaS web app called "Sahi Margin" for Indian e-commerce sellers.
English-only UI, slightly modern/premium look, dark navy sidebar (#1a1a2e) + orange accent (#FF6B00).

## Architecture
- **Frontend**: React 19 + Tailwind CSS v3 + lucide-react + react-router-dom
- **Backend**: FastAPI (minimal, health endpoint only)
- **Database**: MongoDB (provisioned, not used for v1 — all data is hardcoded)
- **Routing**: React Router v6 (client-side SPA)
- **Logo**: Teal/mint gradient SM monogram (user-uploaded image)

## User Personas
- Indian e-commerce sellers on Amazon India, Flipkart, Shopify
- Sellers managing multiple platforms simultaneously
- Small-to-medium sellers needing profit visibility

## Core Requirements (Static)
1. Fixed dark sidebar (240px, #1a1a2e) with logo, nav links, user profile
2. Dashboard with 4 KPI stat cards + Recent Orders table
3. Platform badges: Amazon=blue, Flipkart=amber, Shopify=green, Custom Website=purple, Manual Entry=grey
4. All prices in ₹ (Indian Rupee)
5. Active nav link highlighted in #FF6B00 orange

## What's Been Implemented (April 2026)

### Layout
- [x] Fixed sidebar (240px) with #1a1a2e background
- [x] Uploaded logo image in sidebar header
- [x] 5 navigation links with lucide-react icons + active orange highlight
- [x] Settings link + Rahul Sharma user avatar at bottom
- [x] React Router for client-side navigation

### Pages
- [x] **Dashboard**: 4 KPI cards (Revenue ₹12,450 | Profit ₹3,200 | Orders 24 | Alerts 3), Recent Orders table (6 rows, Indian products, colored platform badges)
- [x] **Profit Calculator**: Input form with live profit/margin calculation
- [x] **Orders**: Full orders table with status badges, search bar
- [x] **Inventory**: Stock table with SKU, threshold, status indicators
- [x] **Connect Store**: Platform connection cards (Amazon connected, others idle/pending)

### Testing
- All 14 test scenarios PASSED (100% success rate)
- Testing agent confirmed: badges, ₹ symbols, routing, KPI values, platform colors all correct

## Iteration 2 Changes (April 2026)
- [x] **Profit Calculator** rebuilt: Platform dropdown with auto-fill commission, GST dropdown, all-deductions breakdown, NET PROFIT live, Save to Orders (localStorage)
- [x] **Orders page**: Add Order modal (with live profit calc + localStorage persistence), Import CSV modal (drag-drop, column mapping, preview, confirm import), search bar filtering
- [x] **Connect Store**: 6 cards — WooCommerce (new, Connect btn), Custom Website (updated desc), Manual Entry (new, Add Order btn → /orders)

## Iteration 3 Changes (April 2026)
- [x] **Login page**: Centered layout, logo, email/password, show/hide, Remember Me, Sign In, Google button, Sign up link, "Trusted by 500+ Indian sellers"
- [x] **Signup page**: Full Name, Email, Phone +91, Password, Confirm, validation, "Free forever" text
- [x] **Auth flow**: localStorage mock auth, protected routes, ProtectedRoute guard, redirect to /login
- [x] **Settings page**: Business Profile (Name, Email, Phone +91, GST, Business Type), Default Calculator Settings (Platform, GST%, Shipping, Packaging), Notifications (3 toggles)
- [x] **Sidebar**: Collapsible to icon-only on desktop (chevron toggle), mobile hamburger, Logout button
- [x] **Notification bell**: On all pages, "3" red badge, dropdown with 3 notifications (2 low stock + 1 order sync)
- [x] **Dashboard**: View All → navigates to /orders
- [x] **Orders**: Platform filter tabs (All/Amazon/Flipkart/Shopify/Custom Website/Manual Entry), empty state with illustration + Add Order CTA
- [x] **Inventory**: Add Product button + modal (Name, SKU, Stock, Reorder Level, Price ₹)

## Prioritized Backlog

### P0 (Next Sprint)
- [ ] Real backend API integration (replace hardcoded data with MongoDB)
- [ ] Authentication (login/register for sellers)
- [ ] Amazon SP-API / Flipkart API real data sync

### P1 (Short term)
- [ ] Date range filter for Dashboard
- [ ] Export orders/reports as CSV/PDF
- [ ] Profit trend charts (recharts or chart.js)
- [ ] Push notifications for low stock alerts

### P2 (Future)
- [ ] Multi-seller / team accounts
- [ ] GST calculation module
- [ ] Returns & refund tracking
- [ ] Mobile responsive layout

## Next Tasks
1. Add real-time charts to Dashboard (revenue trend, platform breakdown pie chart)
2. Connect MongoDB backend for persistent data
3. Add authentication (JWT or Google OAuth)
