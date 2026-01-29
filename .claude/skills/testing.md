# Testing Skill

Best practices for writing effective tests.

## Test Pyramid

```
        /\
       /  \     E2E Tests (few)
      /    \    - User journeys
     /------\   - Critical paths
    /        \
   / Integration\ - API tests
  /   Tests     \ - Database tests
 /--------------\
/   Unit Tests   \ - Functions
/    (many)       \ - Classes
------------------
```

## Test Structure (AAA)

```typescript
test('should calculate total with discount', () => {
  // Arrange - Set up test data
  const cart = new Cart();
  cart.addItem({ price: 100 });
  cart.applyDiscount(0.1);

  // Act - Execute the code
  const total = cart.getTotal();

  // Assert - Verify result
  expect(total).toBe(90);
});
```

## What to Test

### Unit Tests
- Pure functions
- Business logic
- Edge cases
- Error conditions

### Integration Tests
- API endpoints
- Database operations
- External service integration

### E2E Tests
- Critical user journeys
- Happy paths
- Authentication flows

## Test Naming

Format: `should [expected behavior] when [condition]`

Examples:
- `should return null when user not found`
- `should throw error when password is empty`
- `should send email when order is placed`

## Test Doubles

| Type | Purpose |
|------|---------|
| Stub | Returns fixed data |
| Mock | Verifies interactions |
| Spy | Wraps real object, records calls |
| Fake | Working implementation (simpler) |

## Testing Checklist

- [ ] Tests are independent
- [ ] Tests are deterministic
- [ ] Tests are fast
- [ ] Tests have clear assertions
- [ ] Edge cases covered
- [ ] Error cases covered
- [ ] No test interdependencies
- [ ] Mocks/stubs cleaned up

## Common Patterns

### Setup/Teardown
```typescript
beforeEach(() => {
  // Reset state
});

afterEach(() => {
  // Cleanup
});
```

### Testing Async Code
```typescript
test('should fetch user', async () => {
  const user = await getUser(1);
  expect(user.name).toBe('John');
});
```

### Testing Errors
```typescript
test('should throw on invalid input', () => {
  expect(() => validate(null)).toThrow('Input required');
});
```
