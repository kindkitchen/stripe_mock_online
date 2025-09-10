# About

This is simple server from [https://github.com/stripe/stripe-mock](https://github.com/stripe/stripe-mock).
Nothing special except that it is deployed on Fly.io and can be accessed by anybody who lazy enough to do it by self.
Feel free to use it for yourself for simple test/mock stripe purposes (though I can not give you a gurantee that this service will be always accessed).

## Why?

The official mock server is already too simple and ready to use with `go` or `docker`.
And this solution is only to skip even this simple step. You simply have an url ready to use.

## Tips

For someone, who will try to use mock with Stripe sdk. The possible solution is how to configure stripe client to be pointed to this mock may be looked like this:
```typescript
import { Stripe } from 'stripe';

new Stripe('sk_test_mock', {
  protocol: "https",
  host: "stripe-mock-online.fly.dev",
})
  .charges
  .list()
  .then(console.debug);
```
