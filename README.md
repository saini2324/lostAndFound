# TrackIt Back — Lost & Found

A lightweight full-stack Lost & Found web app built with  
**React (Vite)** on the frontend and **Express + PostgreSQL** on the backend.

---

## 🧠 Tech Stack
**Frontend:** React (Vite), Tailwind CSS  
**Backend:** Node.js, Express.js, PostgreSQL  
**Other Tools:** Cloudinary, JWT, Nodemailer 

---

## 📁 Repository Overview

### 🖥️ Server (Backend)
**Path:** `/server`

**Key Files**
- `.env`
- `db.js`
- `server.js`
- `package.json`

**Controllers**
- `authController.js` → `sendOtp`, `verifyOtp`, `register`, `login`
- `itemController.js` → `getAllItems`, `getItemById`, `addItem`, `updateItem`, `deleteItem`, `getUserItems`, `deleteUserItem`
- `mailController.js` → `sendClaimMail`
- `userController.js` → `getUserDetails`

**Middleware**
- `authMiddleware.js`

**Queries**
- `authQueries.js` → `findUserByEmail`, `createUser`
- `itemQueries.js` → CRUD operations for items and user items
- `mailQueries.js` → `getClaimDetails`
- `userQueries.js` → `getUserById`

**Routes**
- `authRoutes.js`
- `userRoutes.js`
- `itemRoutes.js`
- `userMailRoutes.js`

**Utils**
- `sendOtp.js`

---

### 💻 Client (Frontend)
**Path:** `/client`

**Key Files**
- `package.json`
- `vite.config.js`
- `tailwind.config.js`
- `index.html`
- `eslint.config.js`

**App Entry**
- `src/main.jsx`
- `src/App.jsx`
- `src/apiConfig.js`

**Styles**
- `src/index.css`
- `src/App.css`

**Components**
- Core: `Navbar`, `Footer`, `Dashboard`, `Login`, `Register`
- Functional: `Post`, `UrPost`, `EditForm`, `MyCard`, `Card`
- Misc: `About`, `Greeting`, `Head`, `NavSch`, `logout.js`

**Assets**
- `client/public/` — static files  
- `client/src/assets/` — images, icons

---

## ⚙️ Quick Start

### 1️⃣ Backend Setup
```bash
cd server
npm install
node server.js
```

---

### 2️⃣ Frontend Setup
```bash
cd client
npm install
npm run dev
```

> Access the app on [http://localhost:5173](http://localhost:5173)

---

## 🔐 Environment Variables

Create a `.env` file inside `/server` (not committed to Git).  
These variables are used throughout the backend:

```env
JWT_SECRET
DATABASE_URL
CLOUD_NAME
CLOUD_KEY
CLOUD_SECRET
GMAIL_HOST
MY_EMAIL
MY_EMAIL_PASS
```

---

## 🌐 API Overview

**Base URL:** `/api`  
(See `server/server.js`)

### 🔸 Auth
| Method | Endpoint | Controller | Route File |
|:--:|:--|:--|:--|
| POST | `/api/auth/send-otp` | `authController.sendOtp` | `authRoutes.js` |
| POST | `/api/auth/verify-otp` | `authController.verifyOtp` |  |
| POST | `/api/auth/register` | `authController.register` |  |
| POST | `/api/auth/login` | `authController.login` |  |

---

### 🔸 Users
| Method | Endpoint | Controller | Route File |
|:--:|:--|:--|:--|
| GET | `/api/users` | `userController.getUserDetails` | `userRoutes.js` |

---

### 🔸 Items
| Method | Endpoint | Controller | Route File |
|:--:|:--|:--|:--|
| GET | `/api/items` | `itemController.getAllItems` | `itemRoutes.js` |
| POST | `/api/items` | `itemController.addItem` |  |
| GET | `/api/items/:id` | `itemController.getItemById` |  |
| PUT | `/api/items/:id` | `itemController.updateItem` |  |
| DELETE | `/api/items/:id` | `itemController.deleteItem` |  |
| GET | `/api/items/getUserItems` | `itemController.getUserItems` |  |
| DELETE | `/api/items/deleteUserItem` | `itemController.deleteUserItem` |  |

---

### 🔸 Mail
| Method | Endpoint | Controller | Route File |
|:--:|:--|:--|:--|
| POST | `/api/mail/sendClaimMail` | `mailController.sendClaimMail` | `userMailRoutes.js` |

---

### 🛡️ Authentication
- **Bearer JWT Token** required in `Authorization` header.  
- Middleware: `authMiddleware.js`

---

## 📝 Notes & Tips

- **Database:** PostgreSQL pool configured in `db.js`.  
  Ensure `DATABASE_URL` and SSL settings are set properly for deployment.
- **Email:** SMTP credentials used in `sendOtp.js` and `mailController.js`.
- **Cloudinary:** File uploads configured in `itemRoutes.js`.  
  Ensure all `CLOUD_*` environment variables are set.
- **Frontend:** Expects API base URL in `src/apiConfig.js`.
- **Routing Overview:**
  - `authRoutes.js`
  - `itemRoutes.js`
  - `userRoutes.js`
  - `userMailRoutes.js`

---  


💬 *Feel free to open issues, suggest improvements, or contribute via pull requests!*

