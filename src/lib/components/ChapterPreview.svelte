<!-- By default this component manage until 5 tabs. To add more add relative lines in css below where is the relative comment -->

<script lang="ts">
  interface ListItem {
    id: number;
    label: string;
    contentTitle: string;
    contentDescription: string;
  }
  interface Props {
    data: ListItem[];
  }
  // Pass an array of objects containing each: id, label, content title and content description
  const { data }: Props = $props();
</script>

<section class="tabbed-list">
  <h2>What you're getting</h2>
  <div class="main-container">
    <div class="tabs">
      {#each data as { id, label } (id)}
        <input type="radio" name="tab" id={`tab-${id}`} checked={id === 1} />
        <label for={`tab-${id}`}
          ><h3>
            Chapter {id}<span>: {label}</span>
          </h3></label
        >
      {/each}
    </div>
    <div class="content-info">
      {#each data as { id, contentTitle, contentDescription } (id)}
        <div class="content" id={`content-${id}`}>
          <h3>{contentTitle}</h3>
          <p>{contentDescription}</p>
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
  .tabbed-list {
    padding: 4px;
    margin: 2rem 1rem;
    max-width: 1150px;

    h2 {
      font-size: 48px;
      margin-bottom: 16px;
    }
  }
  .main-container {
    display: flex;
    flex-direction: column;

    .tabs {
      display: flex;
      justify-content: space-around;
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

  .content-info {
    .content {
      display: none;

      h3 {
        font-style: italic;
        margin: 32px 0 16px 0;
      }
    }
  }

  @media screen and (min-width: 40rem) {
    .tabbed-list {
      padding: 10px;
    }
    .main-container {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
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
      .content-info {
        width: 55%;
        h3 {
          margin: 0 0 16px 0;
        }
      }
    }
  }
  @media screen and (min-width: 80rem) {
    .tabbed-list {
      padding: 80px;
      margin: 0 auto;
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
    .content-info {
      margin-top: 16px;
      .content {
        display: none;
        padding: 0 20px;
      }
    }
  }
</style>
