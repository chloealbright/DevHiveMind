Sure, I can provide an example of a TypeScript function that uses helper functions, and I'll also show you how to create an integration test for it using Jest. 

Let's say you have a simple function that calculates the total price of items in a shopping cart, and you want to create an integration test for it. Here's the code:

```typescript
// cart.ts

// Helper function 1
function calculateSubtotal(price: number, quantity: number): number {
  return price * quantity;
}

// Helper function 2
function applyDiscount(subtotal: number, discountPercentage: number): number {
  const discount = (subtotal * discountPercentage) / 100;
  return subtotal - discount;
}

// Main function
export function calculateTotalPrice(items: { price: number; quantity: number }[], discountPercentage: number): number {
  const subtotal = items.reduce((acc, item) => acc + calculateSubtotal(item.price, item.quantity), 0);
  const totalPrice = applyDiscount(subtotal, discountPercentage);
  return totalPrice;
}
```

Now, let's create an integration test for this code using Jest.

```typescript
// cart.test.ts

import { calculateTotalPrice } from './cart';

describe('calculateTotalPrice', () => {
  it('calculates the total price with a discount', () => {
    const items = [
      { price: 10, quantity: 2 },
      { price: 5, quantity: 3 },
    ];
    const discountPercentage = 10; // 10% discount

    const totalPrice = calculateTotalPrice(items, discountPercentage);

    // The expected total price after a 10% discount would be 4.5 + 13.5 = 18
    expect(totalPrice).toBe(18);
  });

  it('calculates the total price without a discount', () => {
    const items = [
      { price: 10, quantity: 2 },
      { price: 5, quantity: 3 },
    ];
    const discountPercentage = 0; // No discount

    const totalPrice = calculateTotalPrice(items, discountPercentage);

    // The expected total price without a discount would be 20
    expect(totalPrice).toBe(20);
  });
});
```

In this Jest test, we're testing the `calculateTotalPrice` function with and without a discount. You can run the test using Jest to ensure that the code is working correctly. Make sure to install Jest and any necessary TypeScript configurations to run the test successfully.

To run the test, use the following command:

```
npx jest cart.test.ts
```

This should execute the integration test for the `calculateTotalPrice` function and report the results.