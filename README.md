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
