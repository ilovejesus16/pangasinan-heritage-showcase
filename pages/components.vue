<script setup lang="ts">
import BaseButton from '~/components/atoms/BaseButton.vue'
import BaseIcon from '~/components/atoms/BaseIcon.vue'
import BaseImage from '~/components/atoms/BaseImage.vue'
import BaseTypography from '~/components/atoms/BaseTypography.vue'
import ColorTokens from '~/components/atoms/ColorTokens.vue'
import HeritageCard from '~/components/molecules/HeritageCard.vue'
import SearchForm from '~/components/molecules/SearchForm.vue'
import NavigationItem from '~/components/molecules/NavigationItem.vue'
import HeaderNavigation from '~/components/organisms/HeaderNavigation.vue'
import HeritageGrid from '~/components/organisms/HeritageGrid.vue'
import { heritageSites } from '~/data/heritage'

const search = ref('')
</script>

<template>
  <div class="component-page">

    <header class="component-page__hero">
      <div class="container">
        <p class="eyebrow">ATOMIC DESIGN SYSTEM</p>
        <h1>Pangasinan Heritage<br />Component Library</h1>
        <p>
          Reusable interface components for the Pangasinan Heritage
          Digital Showcase.
        </p>
      </div>
    </header>

    <main class="container component-library">

      <!-- ATOMS -->
      <section class="component-section">
        <div class="component-heading">
          <span>01</span>
          <div>
            <p class="eyebrow">ATOMS</p>
            <h2>Basic building blocks</h2>
          </div>
        </div>

        <!-- Button -->
        <article class="component-demo">
          <div class="demo-info">
            <h3>Button</h3>
            <p>
              Used for primary actions such as exploring heritage
              destinations and submitting forms.
            </p>
          </div>

          <div class="demo-preview">
            <BaseButton label="Explore heritage" />
            <BaseButton label="Learn more" variant="ghost" />
          </div>
        </article>

        <!-- Typography -->
        <article class="component-demo">
          <div class="demo-info">
            <h3>Typography</h3>
            <p>
              Provides consistent heading, label, and body text
              hierarchy throughout the interface.
            </p>
          </div>

          <div class="demo-preview">
            <BaseTypography />
          </div>
        </article>

        <!-- Colors -->
        <article class="component-demo">
          <div class="demo-info">
            <h3>Color Tokens</h3>
            <p>
              Centralized colors maintain visual consistency and make
              future theme changes easier.
            </p>
          </div>

          <div class="demo-preview">
            <ColorTokens />
          </div>
        </article>

        <!-- Icon -->
        <article class="component-demo">
          <div class="demo-info">
            <h3>Icon</h3>
            <p>
              Small interface symbols used alongside text to improve
              recognition and navigation.
            </p>
          </div>

          <div class="demo-preview icon-preview">
            <span>
              <BaseIcon name="search" />
              Search
            </span>

            <span>
              <BaseIcon name="pin" />
              Location
            </span>

            <span>
              <BaseIcon name="arrow" />
              Explore
            </span>

            <span>
              <BaseIcon name="menu" />
              Menu
            </span>
          </div>
        </article>

        <!-- Image -->
        <article class="component-demo">
          <div class="demo-info">
            <h3>Image</h3>
            <p>
              Reusable image component with alternative text and lazy
              loading for better accessibility and performance.
            </p>
          </div>

          <div class="demo-preview image-preview">
            <BaseImage
              :src="heritageSites[0].image"
              :alt="`${heritageSites[0].name} heritage site`"
            />
          </div>
        </article>
      </section>

      <!-- MOLECULES -->
      <section class="component-section">
        <div class="component-heading">
          <span>02</span>
          <div>
            <p class="eyebrow">MOLECULES</p>
            <h2>Simple functional groups</h2>
          </div>
        </div>

        <!-- Heritage Card -->
        <article class="component-demo component-demo--wide">
          <div class="demo-info">
            <h3>Heritage Card</h3>
            <p>
              Combines image, typography, location icon, and button
              atoms to present a heritage destination.
            </p>
          </div>

          <div class="demo-preview card-preview">
            <HeritageCard :site="heritageSites[0]" />
          </div>
        </article>

        <!-- Search Form -->
        <article class="component-demo">
          <div class="demo-info">
            <h3>Search Form</h3>
            <p>
              Allows visitors to quickly find heritage destinations
              using keywords.
            </p>
          </div>

          <div class="demo-preview">
            <SearchForm v-model="search" />
          </div>
        </article>

        <!-- Navigation Item -->
        <article class="component-demo">
          <div class="demo-info">
            <h3>Navigation Item</h3>
            <p>
              Reusable navigation link used to move between sections
              of the website.
            </p>
          </div>

          <div class="demo-preview nav-preview">
            <NavigationItem label="Home" href="#top" />
            <NavigationItem label="Heritage" href="#heritage" />
            <NavigationItem label="About" href="#about" />
          </div>
        </article>
      </section>

      <!-- ORGANISMS -->
      <section class="component-section">
        <div class="component-heading">
          <span>03</span>
          <div>
            <p class="eyebrow">ORGANISMS</p>
            <h2>Complete interface sections</h2>
          </div>
        </div>

        <!-- Header -->
        <article class="component-demo component-demo--wide">
          <div class="demo-info">
            <h3>Header Navigation</h3>
            <p>
              Combines the brand, navigation items, and responsive
              mobile menu into a complete site header.
            </p>
          </div>

          <div class="demo-preview full-preview">
            <HeaderNavigation />
          </div>
        </article>

        <!-- Heritage Grid -->
        <article class="component-demo component-demo--wide">
          <div class="demo-info">
            <h3>Heritage Grid</h3>
            <p>
              Displays multiple heritage cards in a responsive grid.
              Three columns are used on desktop, two on tablet, and
              one on mobile.
            </p>
          </div>

          <div class="demo-preview grid-preview">
            <HeritageGrid :sites="heritageSites.slice(0, 3)" />
          </div>
        </article>
      </section>

    </main>
  </div>
</template>

<style scoped>
.component-page {
  min-height: 100vh;
}

.component-page__hero {
  background: var(--primary);
  color: white;
  padding: 90px 0;
}

.component-page__hero h1 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(48px, 7vw, 80px);
  line-height: 1;
  margin: 0 0 25px;
  letter-spacing: -0.04em;
}

.component-page__hero p:last-child {
  max-width: 650px;
  font-size: 18px;
  color: rgba(255,255,255,.8);
}

.component-library {
  padding: 80px 0;
}

.component-section {
  margin-bottom: 100px;
}

.component-heading {
  display: flex;
  gap: 25px;
  align-items: flex-start;
  margin-bottom: 35px;
}

.component-heading > span {
  font-size: 13px;
  font-weight: 800;
  color: var(--gold);
  padding-top: 8px;
}

.component-heading h2 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(34px, 5vw, 52px);
  line-height: 1;
  margin: 0;
}

.component-demo {
  display: grid;
  grid-template-columns: 280px 1fr;
  gap: 40px;
  padding: 30px;
  margin-bottom: 20px;
  background: white;
  border: 1px solid var(--line);
  border-radius: 10px;
}

.demo-info h3 {
  margin: 0 0 8px;
  font-size: 20px;
}

.demo-info p {
  color: var(--muted);
  font-size: 14px;
  margin: 0;
}

.demo-preview {
  min-width: 0;
  display: flex;
  align-items: center;
  gap: 25px;
}

.icon-preview span {
  display: flex;
  align-items: center;
  gap: 7px;
  font-weight: 700;
  color: var(--primary);
}

.image-preview {
  height: 220px;
  max-width: 500px;
  overflow: hidden;
  border-radius: 8px;
}

.image-preview .base-image {
  width: 100%;
}

.card-preview {
  max-width: 390px;
}

.nav-preview {
  padding: 25px;
  gap: 30px;
  border: 1px dashed var(--line);
}

.full-preview {
  display: block;
  border: 1px dashed var(--line);
  overflow: hidden;
}

.grid-preview {
  display: block;
  overflow: hidden;
}

.grid-preview :deep(.heritage-grid) {
  grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 800px) {
  .component-demo {
    grid-template-columns: 1fr;
    gap: 25px;
  }

  .grid-preview :deep(.heritage-grid) {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 600px) {
  .component-library {
    padding: 55px 0;
  }

  .component-demo {
    padding: 20px;
  }

  .demo-preview {
    flex-wrap: wrap;
  }

  .grid-preview :deep(.heritage-grid) {
    grid-template-columns: 1fr;
  }

  .component-page__hero {
    padding: 65px 0;
  }
}
</style>