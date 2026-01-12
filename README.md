# Fitness Centre MVP

A minimal viable product (MVP) for managing fitness centre members.  
Built using **Laravel 11**, **Vue 3**, and **Inertia.js** with authentication and full CRUD functionality.

---

## 🛠 Tech Stack

- **Backend:** PHP 8.3, Laravel 11
- **Frontend:** Vue 3, Inertia.js
- **Styling:** TailwindCSS
- **Database:** MySQL
- **Auth:** Laravel Breeze
- **Build Tools:** Node.js, Vite, npm

---

## Features

- User authentication (login, register, logout)
- Protected routes
- Member management (CRUD)
  - Create member
  - View member list
  - Edit member details
  - Delete member
- Responsive design (desktop & mobile)
- Server-side validation

---

## Project Structure
app/
└── Http/Controllers/MemberController.php
└── Models/Member.php

resources/js/Pages/
└── Members/
├── Index.vue
├── Create.vue
└── Edit.vue

database/migrations/
└── create_members_table.php


---

## Installation & Setup

### 1. Clone repository
```bash
git clone https://github.com/syahdiatulf/fitness-mvp.git
cd fitness-mvp

composer install
php artisan key:generate
php artisan migrate
npm install
npm run dev

