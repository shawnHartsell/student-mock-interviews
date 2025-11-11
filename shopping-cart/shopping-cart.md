# 🛒 Shopping Cart with Discounts

## Overview

Build a shopping cart system that handles adding/removing items, calculating totals with tax, and applying discount codes.

**Time**: 30-45 minutes

## Problem Statement

Build a shopping cart system that supports the following operations:

### Core Functionality

1. **Add items to cart** - Store product name, unit price, and quantity
2. **Remove items from cart** - Delete a product completely
3. **Update quantities** - Change the quantity of an existing item
4. **Calculate totals** - Compute subtotal, apply discounts, add tax, and get final total
5. **Apply discount codes** - Support various discount types (see below)
6. **Generate receipt** - Display formatted, itemized receipt

### Discount Codes

Your cart should support applying **one discount code** from the following:

- `"SAVE10"` - 10% off entire order
- `"FREESHIP"` - $5.00 off order (simulating free shipping)
- `"BOGO"` - Buy one get one 50% off (applies to items with quantity 2 or more)

**Bonus**: `"SHIRTS20"` - 20% off items in "Shirts" category

### Expected Interface

Your implementation should support operations similar to:

```python
cart = ShoppingCart()

# Adding items
cart.add_item("T-Shirt", 19.99, 2)
cart.add_item("Jeans", 49.99, 1)

# Modifying cart
cart.update_quantity("T-Shirt", 3)
cart.remove_item("Jeans")

# Applying discounts and calculating
cart.apply_discount("SAVE10")
total = cart.get_total(tax_rate=0.08)

# Display results
cart.print_receipt(tax_rate=0.08)
```

### Sample Output

For a cart with:

- T-Shirt: $19.99 × 2
- Jeans: $49.99 × 1
- Socks: $9.99 × 3
- Discount: "SAVE10"
- Tax: 8%

The receipt should look similar to:

```
========== RECEIPT ==========
T-Shirt x2          $39.98
Jeans x1            $49.99
Socks x3            $29.97
----------------------------
Subtotal:          $119.94
Discount (SAVE10):  -$11.99
Tax (8%):            $9.60
----------------------------
TOTAL:             $117.55
============================
```
