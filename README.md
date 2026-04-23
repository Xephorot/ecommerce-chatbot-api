# E-Commerce Chatbot API

A robust backend built with Django REST Framework to power a sales and customer service Telegram chatbot. This system provides a secure API to manage product inventory, track user orders, and handle conversation states, acting as the core data layer for Botpress and Google Gemini integrations.

## 🚀 Key Features

* **RESTful API**: Full endpoints for managing products, categories, users, orders, and FAQs.
* **Dual-Deployment Architecture**: Decoupled system with the Django API hosted on Render and the Telegram Bot service running on Railway for optimal scalability.
* **AI-Ready**: Designed to easily consume and provide context to LLMs like Google Gemini via Botpress.
* **Secure Admin Dashboard**: Built-in Django admin interface for quick inventory and order management.

## 🛠️ Tech Stack

* **Backend Framework:** Django, Django REST Framework
* **Database:** PostgreSQL (Dockerized for local development)
* **Chatbot Logic & NLP:** Botpress Cloud, Google Gemini API
* **Integration:** Telegram Bot API
* **Deployment:** Docker, Render (API & DB), Railway (Bot Service)

## 🏗️ Architecture Flow

1. **Telegram Client** -> Receives user input.
2. **Railway (Bot Service / Botpress)** -> Processes intent using Gemini NLP.
3. **Render (Django API)** -> Receives HTTP requests from the bot, queries the PostgreSQL database, and returns inventory/order data.

## 💻 Getting Started (Local Development)

### Prerequisites
* Python 3.8+
* Docker & Docker Compose
* Telegram Bot Token (via BotFather)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Xephorot/ecommerce-chatbot-api.git
   cd ecommerce-chatbot-api
   ```

2. Set up environment variables:
   ```bash
   cp .env-example .env
   # Edit the .env file and add your SECRET_KEY, GEMINI_API_KEY, and TELEGRAM_BOT_TOKEN
   ```

3. Initialize the environment and database:
   ```bash
   chmod +x setup.sh
   ./setup.sh
   # Note: This script will handle virtual environment creation, dependencies, and migrations. 
   # It will also prompt you to create a superuser for the admin panel.
   ```

4. Start the development server:
   ```bash
   python manage.py runserver
   ```
   *The API will be available at `http://localhost:8000`. Access the admin dashboard at `/admin/`.*

## 🌐 API Endpoints

Base URL: `http://localhost:8000` (Local) or `https://<your-render-url>.onrender.com` (Prod)

* `GET /api/products/` - List all available products
* `GET /api/categories/` - Retrieve product categories
* `GET /api/orders/` - View customer orders
* `GET /api/conversations/` - Chat history logs
* `GET /api/faqs/` - Fetch frequently asked questions

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.
