<script lang="ts">
  const { children, ...props } = $props();
</script>

<button {...props}>{@render children()}</button>

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
