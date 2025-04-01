<script lang="ts">
  import bookCover from '$images/book_cover.webp?enhanced';
  import phoneCover from '$images/phone_cover.webp?enhanced';
  import { Button } from '$components';
</script>

<section class="hero">
  <div class="hero-showcase">
    <h1 class="purple mb-xs">MOVE TO SPAIN</h1>
    <h4 class="italic semi-bold">
      There's no need to make the same mistakes I made.
    </h4>
    <enhanced:img src={phoneCover} alt="" class="phone-cover" />
    <enhanced:img src={bookCover} alt="" class="book-cover" />
  </div>
  <div class="hero-text white text-center">
    <h1 class="mb-m">THIS EBOOK WILL SAVE YOU MONEY, TIME & NERVES</h1>
    <p class="light-grey mb-l">
      I moved to Spain seven years ago. The process was painful and difficult. I
      learned most things the hard way: finding a job, getting a visa,
      calculating my cost of living, choosing an apartment. That's why I wrote
      this e-book, to tell you how I did it. No bullshit, no stress.
    </p>
    <Button>Purchase E-book for $10</Button>
  </div>
</section>

<style>
  .hero-showcase {
    text-align: center;
    position: relative;
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
      max-width: 7ch;
      margin: 16px auto 32px;
    }
    h4 {
      font: italic semi-bold;
      color: hsl(0, 0%, 20%);
    }

    .phone-cover,
    .book-cover {
      display: inline-block;
      vertical-align: middle;
      margin-top: 32px;
    }

    .phone-cover {
      width: 25%;
      height: auto;
    }

    .book-cover {
      width: 55%;
      height: auto;
    }
  }

  .hero-text {
    padding: 48px 5%;
    background-color: black;
    h1 {
      font-size: 48px;
      max-width: 15ch;
      margin: 16px auto 32px;
    }
    p {
      margin-bottom: 32px;
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
      }

      .book-cover {
        position: absolute;
        right: 2%;
        bottom: 0;
        width: 55%;
        transform: translateY(30%);
      }

      .phone-cover {
        position: absolute;
        width: 25%;
        bottom: 0;
        right: 52%;
        transform: translateY(25%);
      }
    }

    .hero-text {
      padding: 100px 5%;
      width: 50%;
      background-color: black;
      h1 {
        font-size: 80px;
      }
      p {
        margin-bottom: 64px;
      }
    }
  }
</style>
