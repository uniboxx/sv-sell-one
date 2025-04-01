<script lang="ts">
  interface Props {
    question: string;
    answer: string;
    isExpanded: boolean;
    onclick: () => void;
  }
  const { question, answer, isExpanded, ...props }: Props = $props();
</script>

<button {...props} class={['container', { expanded: isExpanded }]}>
  <div class="question-and-answer">
    <p class="question">{question}</p>
    <p class="answer">
      {answer}
    </p>
  </div>

  <img src="/icons/chevron-down.svg" alt="" />
</button>

<style>
  .container {
    display: flex;
    justify-content: space-between;
    align-items: start;
    padding: 12px 0;
    border-bottom: 1px solid grey;
    text-align: left;
    margin-bottom: 32px;

    .question-and-answer {
      padding-right: 40px;
      flex-grow: 1;
      .question {
        font-weight: 600;
        margin-bottom: 16px;
      }
      .answer {
        max-height: 0;
        overflow: hidden;
        opacity: 0;
        transition:
          max-height 0.3s ease-out,
          opacity 0.3s ease-out;
      }
    }

    img {
      transition: transform 0.3s linear;
    }

    &.expanded img {
      transform: rotate(180deg);
    }

    &.expanded .answer {
      max-height: unset;
      opacity: 1;
    }
  }

  @media screen and (min-width: 40rem) {
    .container {
      margin-bottom: 48px;
    }
    .question-and-answer {
      padding-right: 80px;
    }
  }
  @media screen and (min-width: 80rem) {
    .container {
      margin-bottom: 64px;
    }
    .question-and-answer {
      padding-right: 150px;
    }
  }
</style>
