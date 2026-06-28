# 💳 Payment Processing System

> A flexible Java payment system demonstrating the **Strategy Design Pattern** with multiple payment methods and customer tiers.

![Java](https://img.shields.io/badge/Java-17-orange?logo=java)
![Pattern](https://img.shields.io/badge/Design-Strategy-blue)


---

## 📌 Overview

This project implements a payment processing system using the **Strategy Pattern**, allowing customers to switch between payment methods (Credit Card, PayPal, Bitcoin) at runtime without modifying existing code.

---

## ✨ Key Features

| Category | Feature | Description |
|----------|---------|-------------|
| 💰 **Payments** | Credit Card | Pay with card number & holder name |
| | PayPal | Pay via email address |
| | Bitcoin | Pay via wallet address |
| 👥 **Customers** | Regular | Standard customer tier |
| | Premium | Premium customer tier |
| 🛠️ **Design** | Strategy Pattern | Runtime payment method switching |
| | OOP | Abstract classes, interfaces, inheritance |
| | SOLID | Open/Closed Principle compliant |

---

## 🎯 Design Pattern: Strategy

| Component | Class/Interface | Role |
|-----------|-----------------|------|
| **Strategy Interface** | `PaymentStrategy` | Defines payment contract |
| **Concrete Strategies** | `BitcoinPayment`, `PayPalPayment`, `CreditCardPayment` | Implement specific payment methods |
| **Context** | `Customer` (abstract) | Uses a strategy to make payments |
| **Concrete Contexts** | `RegularCustomer`, `PremiumCustomer` | Different customer types |

---

## 📁 Project Structure

| File | Type | Responsibility |
|------|------|----------------|
| `interfaces.java` | Interface | Defines `PaymentStrategy` contract |
| `Customer.java` | Abstract Class | Base class with payment history |
| `RegularCustomer.java` | Class | Regular customer implementation |
| `PremiumCustomer.java` | Class | Premium customer implementation |
| `BitcoinPayment.java` | Class | Bitcoin payment strategy |
| `PayPalPayment.java` | Class | PayPal payment strategy |
| `CreditCardPayment.java` | Class | Credit card payment strategy |
| `Main.java` | Entry Point | Application demo |

---

## 🚀 Quick Start

### 1. Compile
```bash
javac payment/*.java Main.java
```

### 2. Run
```bash
java Main
```

---

## 💻 Usage Example

```java
// Create customer
PremiumCustomer customer = new PremiumCustomer("amir");

// Create payment strategies
BitcoinPayment bitcoin = new BitcoinPayment("1863453931");
PayPalPayment paypal = new PayPalPayment("rm4324@gmail.com");

// Make payments (Strategy Pattern in action)
customer.makePayment(paypal, 200.0);
customer.makePayment(bitcoin, 300.56);

// View history
customer.showPaymentHistory();
```

---

## 📊 Sample Output

```
amir :Premium Customer
nima :Premium Customer
mehdi :Regular Customer

amount:200.0 Pay Pal Payment : rm4324@gmail.com
amount:300.56 Bitcoin Payment : 1863453931

--- Payment History for amir ---
Pay Pal Payment : rm4324@gmail.com
Bitcoin Payment : 1863453931
```

---

## 🔧 Extending the System

To add a new payment method (e.g., Bank Transfer):

| Step | Action |
|------|--------|
| 1️⃣ | Create `BankTransferPayment.java` |
| 2️⃣ | Implement `PaymentStrategy` interface |
| 3️⃣ | Override `pay()` and `getPaymentDetails()` |
| 4️⃣ | Use it with any customer — **no other changes needed!** |

---

## 🚀 Future Enhancements

| Feature | Status |
|---------|--------|
| Input validation & error handling | ⏳ Planned |
| Database integration | ⏳ Planned |
 | Unit tests (JUnit) | ⏳ Planned |
 | Logging (SLF4J) | ⏳ Planned |
 | GUI interface | ⏳ Planned |
 | Currency conversion | ⏳ Planned |


---

<div align="center">
  <sub>Built with ☕ Java & ❤️ by following SOLID principles</sub>
</div>
