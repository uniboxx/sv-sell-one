<script lang="ts">
  import { chapters } from '$assets/data';
</script>

<section class="chapter-preview default-margin">
  <h2 class="mb-l">What you're getting</h2>
  <div class="chapter-container">
    <div class="tabs">
      {#each chapters as chapter (chapter.number)}
        <input
          type="radio"
          name="chapter"
          id={`tab-${chapter.number}`}
          checked
        />
        <label for={`tab-${chapter.number}`}
          ><h3>
            Chapter {chapter.number}<span>: {chapter.title}</span>
          </h3></label
        >
      {/each}
    </div>
    <div class="chapter-info">
      {#each chapters as chapter (chapter.number)}
        <div class="content" id={`content-${chapter.number}`}>
          <h3 class="chapter-strapline italic mb-s">{chapter.strapline}</h3>
          <p>{chapter.excerpt}</p>
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
    &:has(input[type='radio']#tab-1:checked) #content-1,
    &:has(input[type='radio']#tab-2:checked) #content-2,
    &:has(input[type='radio']#tab-3:checked) #content-3,
    &:has(input[type='radio']#tab-4:checked) #content-4,
    &:has(input[type='radio']#tab-5:checked) #content-5 {
      display: block;
    }
  }

  .chapter-info {
    width: 100%;
    margin-top: 16px;
    .content {
      display: none;
      padding: 20px;
      border: 1px solid black;
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
      border-bottom: 1px solid grey;
      width: 100%;
      display: block;
      padding: 12px;
      text-align: left;
    }
  }
</style>
