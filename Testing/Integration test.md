---
tags: 
author:
  - jacgit18
Status: init
Started: 2023-11-23
EditDate: 
Relates:
---
When crafting an integration test, the process closely resembles that of a unit test. For instance, when examining a function, conducting a unit test is akin to an integration test. The primary distinction arises if you opt to fragment parts of the function into module helper functions that the main function incorporates. In such cases, the integration test remains centered on the main function but concentrates on verifying the edge cases addressed by the modular helper functions.


## Simple Example

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

## Advanced Example 

```typescript
import * as bcrypt from 'bcrypt';

// Main authentication function using helper functions
function authenticateUser(username: string, password: string): boolean {
    const storedPasswordHash = retrieveStoredPasswordHash(username);
    if (storedPasswordHash) {
        const passwordMatch = verifyPassword(password, storedPasswordHash);
        return passwordMatch;
    }
    return false;
}

function retrieveStoredPasswordHash(username: string): string | null {
    // Simulated database retrieval, in a real-world scenario, this would interact with a database
    const storedHash = userDatabase[username];
    return storedHash || null;
}

function verifyPassword(password: string, storedHash: string): boolean {
    // Use bcrypt to compare the provided password with the stored hash
    return bcrypt.compareSync(password, storedHash);
}

// Simulated user database
const userDatabase: Record<string, string> = {
    'exampleUser': bcrypt.hashSync('secretPassword', 10),
};

// Integration test for authentication
function authenticationIntegrationTest() {
    // Test with correct credentials
    const successfulAuthentication = authenticateUser('exampleUser', 'secretPassword');
    if (successfulAuthentication) {
        console.log("Authentication test passed for correct credentials!");
    } else {
        console.error("Authentication test failed for correct credentials!");
    }

    // Test with incorrect password
    const failedAuthentication = authenticateUser('exampleUser', 'wrongPassword');
    if (!failedAuthentication) {
        console.log("Authentication test passed for incorrect password!");
    } else {
        console.error("Authentication test failed for incorrect password!");
    }

    // Test with non-existent user
    const nonExistentUser = authenticateUser('nonExistentUser', 'somePassword');
    if (!nonExistentUser) {
        console.log("Authentication test passed for non-existent user!");
    } else {
        console.error("Authentication test failed for non-existent user!");
    }
}

// Run the authentication integration test
authenticationIntegrationTest();
```

