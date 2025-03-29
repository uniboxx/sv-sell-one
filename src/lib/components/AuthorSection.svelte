<script lang="ts">
  import authorPic from '$images/profile_pic.jpg?enhanced';
</script>

<section class="author-section">
  <h2 class="mb-l">About the author</h2>
  <div class="author-container">
    <div class="author-text">
      <p>
        Niklas Fischer is a seasoned expatriate with over seven years of
        experience living in Spain. Originally from New York, John left behind
        the hustle of corporate America to embrace a more fulfilling life on the
        sun-soaked coasts of Spain. Through his own journey, he has navigated
        the challenges of securing visas, finding the perfect home, and adapting
        to a new culture, making him an expert in the field of relocation.
      </p>
      <p>
        Niklas’ practical advice is rooted in real-life experience, having
        learned firsthand the intricacies of moving to a new country. His goal
        is to help others avoid common pitfalls and make their transition to
        life in Spain as smooth as possible. When not sharing his expertise,
        John enjoys exploring Spain’s rich culture and history, fully embracing
        the lifestyle he once dreamed of.
      </p>
    </div>
    <enhanced:img class="author-image" src={authorPic} alt="author" />
  </div>
</section>

<style>
  .author-section {
    margin: 2rem 1rem;
    h2 {
      margin-bottom: 32px;
    }
  }
  .author-container {
    display: flex;
    flex-direction: column;
    .author-image {
      display: block;
      width: 80%;
      max-width: 1000px;
      height: auto;
      margin: 0 auto;
      border: 6px solid black;
      box-shadow: 0 4px 24px rgba(0, 0, 0, 0.5);
      margin-bottom: 32px;
    }
    .author-text {
      order: 2;
      p {
        margin-bottom: 8px;
      }
    }
  }

  @media screen and (min-width: 40rem) {
    .author-container {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      .author-image {
        width: 40%;
        align-self: start;
        border: 6px solid black;
        box-shadow: 0 4px 24px rgba(0, 0, 0, 0.5);
      }
      .author-text {
        order: 0;
        width: 50%;
      }
    }
  }
  @media screen and (min-width: 80rem) {
    .author-section {
      padding: 80px 0;
      margin-left: 12vw;
      margin-right: 20vw;
      max-width: 1150px;
    }
  }
</style>
