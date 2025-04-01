<script lang="ts">
  import { loadStripe } from '@stripe/stripe-js';
  import { PUBLIC_STRIPE_KEY } from '$env/static/public';
  import { goto } from '$app/navigation';

  // console.log(PUBLIC_STRIPE_KEY);
  const { children, ...props } = $props();

  async function onclick() {
    try {
      const stripe = await loadStripe(PUBLIC_STRIPE_KEY);

      const response = await fetch('/api/checkout', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
      });
      const { sessionId } = await response.json();
      await stripe?.redirectToCheckout({ sessionId });
    } catch (error) {
      goto('/checkout/cancel');
    }
  }
</script>

<button {...props} {onclick}>{@render children()}</button>

<style>
  button {
    background-color: black;
    color: white;
    padding: 20px 24px;
    font-weight: normal;
    font-size: 1rem;
    text-transform: uppercase;
    transition: all 0.3s;
    border: 1px solid white;

    &:hover {
      background-color: white;
      color: black;
    }

    @media screen and (min-width: 40rem) {
      font-size: 1.35rem;
    }
  }
</style>
