# Billing System

A simple Django-based billing application.

## Prerequisites

- Python 3.8+
- Django 4.0+

## Setup Instructions

1.  **Clone/Extract the project**:
    Ensure you represent in the project root directory (where `manage.py` is located).

2.  **Create and Activate a Virtual Environment** (Optional but recommended):
    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3.  **Install Dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

4.  **Apply Database Migrations**:
    ```bash
    python3 manage.py migrate
    ```

5.  **Seed Initial Product Data**:
    Run the following command to populate the database with sample products:
    ```bash
    python3 manage.py seed_products
    ```
    (Note: This will delete any existing products and create fresh ones).

6.  **Run the Development Server**:
    ```bash
    python3 manage.py runserver
    ```

7.  **Access the Application**:
    Open your browser and navigate to `http://127.0.0.1:8000`.

## Features

- **Dynamic Billing Page**: Add multiple products, enter quantities, and specify available denominations.
- **Bill Generation**: Calculates totals, taxes, and balance to be returned.
- **Change Calculation**: Algorithmically determines the optimal breakdown of change to return based on shop's available cash.

- **History**: View past bills and their details.

## Assumptions

- Tax is calculated per item based on the product's tax percentage.
- Rounding is applied to the net price (flooring) as per requirements.
- "Purchase Price" in the bill table is interpreted as the base price (Quantity * Unit Price) before tax.
