<script lang="ts">
  import { HeroSection, ChapterPreview, AuthorSection } from '$components';
  import { chapters } from '$assets/data';
</script>

<svelte:head>
  <title>Move to Spain Ebook</title>
  <meta
    name="description"
    content="Ebook that guide you how to move in Spain painless."
  />
</svelte:head>

<HeroSection />
<ChapterPreview data={chapters} />
<AuthorSection />
