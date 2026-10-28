# Project Structure & Folder Hygiene Architecture

## Onboarding Time Estimate
- **Before Restructure (Flat `src/`):** ~4 hours to locate dependencies, navigate files, and understand feature boundaries across 47 unorganized files.
- **After Restructure (Feature-Based):** ~15–20 minutes for a new engineer to onboard, locate logic, and add new features.

---

## Target Feature-Based Folder Tree

```text
src/
├── components/         # Shared UI components (used by 2+ features)
│   ├── Button.jsx
│   ├── Modal.jsx
│   ├── Spinner.jsx
│   └── Card.jsx
├── hooks/              # Shared generic custom hooks
│   ├── useDebounce.js
│   ├── useLocalStorage.js
│   └── useWindowSize.js
├── utils/              # Pure utility functions (zero React dependency)
│   ├── formatCurrency.js
│   ├── truncateText.js
│   └── parseDate.js
├── services/           # Shared base API clients & config
│   └── apiClient.js
├── features/           # Feature domain modules
│   ├── auth/           # Authentication domain
│   │   ├── LoginForm.jsx
│   │   ├── loginService.js
│   │   └── useLogin.js
│   ├── cart/           # Shopping Cart domain
│   │   ├── CartItem.jsx
│   │   ├── CheckoutForm.jsx
│   │   ├── cartService.js
│   │   └── useCart.js
│   ├── catalog/        # Product Catalog domain
│   │   ├── ProductCard.jsx
│   │   ├── ProductList.jsx
│   │   └── productService.js
│   └── orders/         # Order History domain
│       ├── OrderCard.jsx
│       ├── OrderList.jsx
│       └── ordersAPI.js
├── App.jsx
├── main.jsx
└── index.css

