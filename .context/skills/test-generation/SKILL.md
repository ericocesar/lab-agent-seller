---
type: skill
name: test-generation
description: Test case generation
status: filled
---

# Test Generation

## Patterns

### Livewire Component Tests
```php
use Livewire\Livewire;

it('validates required fields', function () {
    Livewire::test(Component::class)
        ->set('field', '')
        ->call('save')
        ->assertHasErrors(['field' => 'required']);
});
```

### HTTP Fake Tests
```php
Http::fake(['api.pipedrive.com/*' => Http::response([...])]);
```

### Mail Fake Tests
```php
Mail::fake();
Mail::assertSent(MagicLinkMail::class);
```

### AI Agent Fake Tests
```php
SellerAgent::fake(['response text']);
```

## Best Practices

- Use `RefreshDatabase` trait
- Create model factories for test data
- Test both success and failure paths
- Test edge cases (empty results, API errors, expired tokens)
- Use `fake()->word()` for unique test data
