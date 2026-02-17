# Webhooks Explained 🪝

**Webhooks** are like "Reverse APIs". Instead of you calling the server, the server calls you.

## The Analogy: Pizza Delivery 🍕
-   **Polling (Traditional API)**: You call the pizza place every minute: "Is it ready? Is it ready? Is it ready?" (Inefficient).
-   **Webhook**: You give them your phone number. When the pizza is ready, **they call you**.

## How it works
1.  **Setup**: You tell the provider (e.g., Stripe) a URL on your server: `https://myapp.com/payment-success`.
2.  **Event**: A user makes a payment.
3.  **Notification**: Stripe sends a `POST` request to your URL with the payment details.
    ```json
    {
      "event": "payment_succeeded",
      "amount": 5000,
      "currency": "usd"
    }
    ```
4.  **Action**: Your server receives the data and updates the user's order status.

## Why use them?
-   **Real-time**: You know immediately when something happens.
-   **Efficiency**: No need to constantly check (poll) for updates.
