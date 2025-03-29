<!-- By default the component manage until 5 tabs. To add more add relative lines in css below where is the relative comment -->

<script lang="ts">
  import { chapters } from '$assets/data';
</script>

<section class="chapter-preview default-margin">
  <h2 class="mb-l">What you're getting</h2>
  <div class="chapter-container">
    <div class="tabs">
      {#each chapters as { number, title } (number)}
        <input
          type="radio"
          name="chapter"
          id={`tab-${number}`}
          checked={number === 1}
        />
        <label for={`tab-${number}`}
          ><h3>
            Chapter {number}<span>: {title}</span>
          </h3></label
        >
      {/each}
    </div>
    <div class="chapter-info">
      {#each chapters as { number, strapline, excerpt } (number)}
        <div class="content" id={`content-${number}`}>
          <h3 class="chapter-strapline italic mb-s">{strapline}</h3>
          <p>{excerpt}</p>
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
  .chapter-preview {
    padding: 4px;
    margin: 2rem 1rem;

    h2 {
      font-size: 48px;
      margin-bottom: 16px;
    }
  }
  .chapter-container {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    .tabs {
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      input[type='radio'] {
        display: none;
        &:checked + label {
          background: #333;
          color: white;
        }
      }
      label {
        padding: 10px;
        cursor: pointer;
        transition: 0.3s;
        &:hover {
          background: #ddd;
        }
        span {
          display: none;
        }
      }
    }

    /* add more selectors here editing tab-n and content-n with subsequent numbers*/
    &:has(input[type='radio']#tab-1:checked) #content-1,
    &:has(input[type='radio']#tab-2:checked) #content-2,
    &:has(input[type='radio']#tab-3:checked) #content-3,
    &:has(input[type='radio']#tab-4:checked) #content-4,
    &:has(input[type='radio']#tab-5:checked) #content-5 {
      display: block;
    }
  }

  .chapter-info {
    margin-top: 16px;
    .content {
      display: none;
      margin: auto;
    }
  }

  @media screen and (min-width: 40rem) {
    .chapter-preview {
      padding: 10px;
    }
    .chapter-container {
      display: flex;
      flex-direction: row;
      margin-top: 64px;

      .tabs {
        flex-direction: column;
        justify-content: start;
        width: 40%;
        label {
          span {
            display: inline;
          }
        }
        label {
          border-bottom: 1px solid grey;
        }
      }
      .chapter-info {
        width: 55%;
        margin-top: 0;
      }
    }
  }
  @media screen and (min-width: 80rem) {
    .chapter-preview {
      padding: 80px;
      margin-left: 12vw;
      margin-right: 20vw;
      max-width: 1250px;
    }

    input[type='radio']:checked + label {
      box-shadow:
        0 4px 6px rgba(0, 0, 0, 0.1),
        0 1px 3px rgba(0, 0, 0, 0.08);
    }

    label {
      width: 100%;
      display: block;
      padding: 12px;
      text-align: left;
    }
    .chapter-info {
      margin-top: 16px;
      .content {
        display: none;
        padding: 20px;
      }
    }
  }
</style>
