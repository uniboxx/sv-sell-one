<script lang="ts">
  import { FaqItem, Button } from '$components';
  import telegramIcon from '$icons/telegram.svg';
  import { faqs } from '$assets/data';

  let questionCurrentlyExpanded = $state(-1);

  function toggle(index: number) {
    if (index === questionCurrentlyExpanded) {
      return (questionCurrentlyExpanded = -1);
    }
    questionCurrentlyExpanded = index;
  }
</script>

<div class="landing-page-section">
  <h2>Frequently Asked Questions</h2>
  <div class="faq-container">
    {#each faqs as faq, index (faq.question)}
      <FaqItem
        {...faq}
        isExpanded={index === questionCurrentlyExpanded}
        onclick={() => toggle(index)}
      />
    {/each}
  </div>
  <div class="additional-info">
    <Button>BUY NOW</Button>
    <p>Any other questions?</p>
    <a href="https://t.me/unibox">
      <span>
        Hit me up on Telegram <img
          class="telegram-icon"
          src={telegramIcon}
          alt=""
        />
      </span>
    </a>
  </div>
</div>

<style>
  .additional-info {
    display: flex;
    flex-direction: column;
    align-items: center;
    color: grey;
    & > p {
      margin-top: 32px;
    }
    a {
      text-decoration: underline;
      span {
        .telegram-icon {
          vertical-align: middle;
          width: 1rem;
          height: 1rem;
        }
      }
    }
  }
</style>
