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
  <svg
    xmlns="http://www.w3.org/2000/svg"
    width="20"
    height="20"
    fill="currentColor"
    class="bi bi-chevron-down"
    viewBox="0 0 16 16"
  >
    <path
      fill-rule="evenodd"
      d="M1.646 4.646a.5.5 0 0 1 .708 0L8 10.293l5.646-5.647a.5.5 0 0 1 .708.708l-6 6a.5.5 0 0 1-.708 0l-6-6a.5.5 0 0 1 0-.708"
    />
  </svg>
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

    &.expanded svg {
      transform: rotate(180deg);
    }

    &.expanded .answer {
      max-height: unset;
      opacity: 1;
    }
  }

  .question-and-answer {
    padding-right: 40px;
    flex-grow: 1;
  }

  .answer {
    max-height: 0;
    overflow: hidden;
    opacity: 0;
    transition:
      max-height 0.3s ease-out,
      opacity 0.3s ease-out;
  }

  button svg {
    transition: transform 0.3s linear;
    width: 4rem;
    path {
      fill: grey;
    }
  }

  .question {
    font-weight: 600;
    margin-bottom: 16px;
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
