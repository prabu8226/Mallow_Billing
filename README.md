# 🧾 Billing System

A sophisticated, modern Django-based billing application designed for efficiency and ease of use. It features dynamic item management, automated tax calculation, and a change-returning algorithm.

---

## 🚀 Getting Started

### 1. Prerequisites
- **Python**: 3.12+
- **Database**: SQLite (default)

### 2. Installation

Clone the repository and navigate to the project root:

```bash
cd Mallow_Billing
```

Create and activate a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
```

Install the required dependencies:
```bash
pip install -r requirements.txt
```

### 3. Configuration ⚙️

The application uses environment variables for security. Create a `.env` file in the project root:

```ini
# Security
SECRET_KEY=your-secret-key-here

# Email (SendGrid Configuration)
EMAIL_HOST_USER=apikey
EMAIL_HOST_PASSWORD=your-sendgrid-api-key
DEFAULT_FROM_EMAIL=Your Name <your-email@example.com>
```

### 4. Database Setup

Apply migrations and seed initial product data:
```bash
python manage.py migrate
python manage.py seed_products
```
*Note: `seed_products` will populate the database with a catalog of items to get you started immediately.*

### 5. Running the App

Start the development server:
```bash
python manage.py runserver
```
Visit the app at [http://127.0.0.1:8000](http://127.0.0.1:8000)

---

## ✨ Key Features

- **Dynamic Billing Interface**: Add/remove items on the fly with real-time calculations.
- **Automated Tax Engine**: Intelligent GST/Tax calculation per product category.
- **Smart Change Algorithm**: Calculates the optimal denomination breakdown for customer change based on available cash reserves.
- **Transaction History**: Comprehensive record of all past bills for easy auditing.
- **PDF Export**: (If implemented) Generate professional receipts for customers.

---

## 🛠 Project Structure

- `billing/`: Main application logic, including models and views.
- `billing_system/`: Project configuration and settings.
- `static/`: Frontend assets (CSS, JS).
- `templates/`: HTML structures.

---

## 📝 Assumptions & Notes

- **Tax Logic**: Calculated per item based on pre-defined product rates.
- **Rounding**: Net prices are floored to the nearest integer as per business requirements.
- **Cash Management**: The change algorithm assumes a standard set of denominations (2000, 500, 200, 100, 50, 20, 10, 5, 2, 1).
