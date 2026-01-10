# Indevs - Subdomain Management Platform

Indevs is a full-stack platform that allows users to register, manage, and configure subdomains (e.g., `username.indevs.in`). It features a modern React dashboard and a robust Express/MongoDB backend.

## Features

- **User Authentication**: Secure login via GitHub/Google (OAuth) or Email/Password.
- **Subdomain Management**: Register, update nameservers, and delete subdomains.
- **Dashboard**: Real-time overview of active, pending, and expired domains.
- **Automated Maintenance**: Daily cron jobs for expiry notifications and soft deletes.
- **Security**: Rate limiting, security headers (Helmet), and secure session management.

## Tech Stack

- **Frontend**: React, Vite, Tailwind CSS, Radix UI.
- **Backend**: Node.js, Express, MongoDB (Mongoose), Passport.js.

## Project Structure

- \`frontend/\`: React SPA source code.
- \`backend/\`: Express API source code.

## Getting Started

### Prerequisites

- Node.js (v18+)
- MongoDB (running locally or via Atlas)

### Installation

1.  **Clone the repository**:
    \`\`\`bash
    git clone https://github.com/yourusername/indevs.git
    cd indevs
    \`\`\`

2.  **Install Dependencies**:
    \`\`\`bash
    # Backend
    cd backend
    npm install

    # Frontend
    cd ../frontend
    npm install
    \`\`\`

3.  **Environment Setup**:
    - Rename \`backend/.env.example\` to \`backend/.env\` and fill in the secrets (MONGO_URI, SESSION_SECRET, etc.).
    - Rename \`frontend/.env.example\` to \`frontend/.env\` (set VITE_API_URL).

4.  **Run Development Servers**:
    \`\`\`bash
    # Terminal 1 (Backend)
    cd backend
    npm run dev

    # Terminal 2 (Frontend)
    cd frontend
    npm run dev
    \`\`\`

## License

MIT License - see [LICENSE](LICENSE) for details.
# domains-docs
