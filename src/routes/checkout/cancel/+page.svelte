<script lang="ts">
  import { Button, HeroSection } from '$components';
</script>

<svelte:head>
  <title>Payment Checkout</title>
  <meta
    name="description"
    content="Ebook that guide you how to move in Spain painless."
  />
</svelte:head>

<HeroSection>
  <h1 class="heroSectionTitle">ERROR WHILE PURCHASING</h1>
  <p class="light-grey mb-s">
    We’re sorry, but it looks like there was an issue with your purchase. Don’t
    worry—these things happen, and we're here to help. Please double-check your
    payment details and try again.
  </p>
  <p class="light-grey mb-s">
    We apologize for any inconvenience this may have caused and appreciate your
    patience. We’re committed to ensuring that you get the guide you need to
    make your move to Spain as smooth as possible.
  </p>
  <p class="light-grey mb-m">
    If you’d like to try again, please click the button below to return to the
    checkout page.
  </p>
  <Button>Try again</Button>
</HeroSection>
