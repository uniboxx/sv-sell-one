<script lang="ts">
  import bookCover from '$assets/images/book_cover.webp';
  import phoneCover from '$assets/images/phone_cover.webp';
  import { Button } from '$components';
  import type { Snippet } from 'svelte';

  interface Props {
    children?: Snippet;
  }

  const { children }: Props = $props();
</script>

<section class="hero">
  <div class="hero-showcase">
    <h1 class="purple mb-xs">MOVE TO SPAIN</h1>
    <h4 class="italic semi-bold">
      There's no need to make the same mistakes I made.
    </h4>
    <div class="images">
      <img src={phoneCover} alt="" class="phone-cover" />
      <img src={bookCover} alt="" class="book-cover" />
    </div>
  </div>
  <div id="hero-right" class="hero-text white text-center">
    {#if children}
      {@render children()}
    {:else}
      <h1 class="heroSectionTitle">
        THIS EBOOK WILL SAVE YOU MONEY, TIME & NERVES
      </h1>
      <p class="light-grey mb-l">
        I moved to Spain seven years ago. The process was painful and difficult.
        I learned most things the hard way: finding a job, getting a visa,
        calculating my cost of living, choosing an apartment. That's why I wrote
        this e-book, to tell you how I did it. No bullshit, no stress.
      </p>
      <Button>Purchase E-book for $10</Button>
    {/if}
  </div>
</section>

<style>
  .hero-showcase {
    text-align: center;
    width: 100%;
    height: 100svh;
    overflow-y: hidden;
    padding: 48px 16px 0;
    background: linear-gradient(
      135deg,
      #e2cbff,
      #e2cbff 25%,
      #deeaff 50%,
      #ece5ff 75%,
      #927bce
    );

    h1 {
      font-size: 5rem;
      max-width: 5ch;
      margin: 16px auto 32px;
    }
    h4 {
      font: italic semi-bold;
      color: hsl(0, 0%, 20%);
    }

    .images {
      display: flex;
      justify-content: center;
      align-items: end;
      margin-top: 32px;

      .phone-cover,
      .book-cover {
        display: block;
        height: auto;
      }

      .phone-cover {
        width: 30%;
      }

      .book-cover {
        width: 50%;
      }
    }
  }

  .hero-text {
    padding: 48px 5%;
    background-color: black;

    p {
      margin-bottom: 32px;
    }
  }

  @media screen and (min-width: 40rem) {
    .hero-showcase {
      h1 {
        max-width: 7ch;
      }
      .images {
        .phone-cover {
          width: 24%;
        }

        .book-cover {
          width: 40%;
        }
      }
    }
  }
  @media screen and (min-width: 80rem) {
    .hero {
      display: flex;
      height: 100svh;
      overflow-y: hidden;
    }

    .hero-showcase {
      position: relative;
      width: 50%;
      height: 100%;
      padding: 100px 16px 0;
      background: linear-gradient(
        135deg,
        #e2cbff,
        #e2cbff 25%,
        #deeaff 50%,
        #ece5ff 75%,
        #927bce
      );

      h1 {
        font-size: 6rem;
        max-width: 7ch;
      }
    }

    .hero-text {
      padding: 100px 5%;
      width: 50%;
      background-color: black;

      p {
        margin-bottom: 64px;
      }
    }
  }
</style>
