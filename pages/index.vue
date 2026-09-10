<script setup lang="ts">
import HeaderNavigation from '~/components/organisms/HeaderNavigation.vue'
import HeritageGrid from '~/components/organisms/HeritageGrid.vue'
import SearchForm from '~/components/molecules/SearchForm.vue'
import { heritageSites } from '~/data/heritage'

const search = ref('')
</script>

<template>
  <div class="home-page">

    <HeaderNavigation />

    <main>
      <!-- HERO -->
      <section class="hero">
        <div class="container hero-content">
          <p class="eyebrow">PANGASINAN PROVINCIAL TOURISM OFFICE</p>

          <h1>
            Stories, places,<br />
            <span>and living heritage.</span>
          </h1>

          <p class="hero-description">
            Explore the landscapes, landmarks, and cultural destinations
            that make Pangasinan worth remembering.
          </p>

          <div class="hero-actions">
            <a href="#heritage" class="primary-button">
              Explore heritage
              <span>→</span>
            </a>

            <a href="#about" class="text-button">
              Learn about the project
            </a>
          </div>
        </div>
      </section>

      <!-- HERITAGE -->
      <section id="heritage" class="heritage-section">
        <div class="container">

          <div class="section-intro">
            <div>
              <p class="eyebrow">FEATURED DESTINATIONS</p>

              <h2>Start your Pangasinan story.</h2>
            </div>

            <p>
              Curated heritage highlights designed for quick
              discovery on mobile, tablet, and desktop.
            </p>
          </div>

          <SearchForm v-model="search" />

          <HeritageGrid
            :sites="heritageSites"
            :search="search"
          />

        </div>
      </section>

      <!-- ABOUT -->
      <section id="about" class="about-section">
        <div class="container">
          <p class="eyebrow">ABOUT THE SHOWCASE</p>

          <h2>
            Discover Pangasinan through its heritage.
          </h2>

          <p>
            The Pangasinan Heritage Digital Showcase is a responsive
            digital platform created to promote cultural awareness and
            tourism by presenting the province's notable heritage
            destinations in an accessible and mobile-first experience.
          </p>
        </div>
      </section>
    </main>

  </div>
</template>

<style scoped>
.home-page {
  min-height: 100vh;
  background: var(--background);
}

.hero {
  min-height: 580px;
  display: flex;
  align-items: center;
  background: var(--primary);
  color: white;
  position: relative;
  overflow: hidden;
}

.hero::after {
  content: '';
  position: absolute;
  width: 900px;
  height: 350px;
  right: -150px;
  bottom: -180px;
  background: rgba(240, 193, 91, 0.2);
  border-radius: 50%;
}

.hero-content {
  position: relative;
  z-index: 1;
  padding-top: 80px;
  padding-bottom: 80px;
}

.hero h1 {
  max-width: 850px;
  margin: 15px 0 25px;
  font-family: 'Playfair Display', serif;
  font-size: clamp(52px, 7vw, 88px);
  line-height: .95;
  letter-spacing: -0.04em;
}

.hero h1 span {
  color: var(--gold);
}

.hero-description {
  max-width: 620px;
  font-size: 17px;
  line-height: 1.7;
  color: rgba(255,255,255,.82);
}

.hero-actions {
  display: flex;
  align-items: center;
  gap: 25px;
  margin-top: 30px;
}

.primary-button {
  display: inline-flex;
  align-items: center;
  gap: 20px;
  padding: 15px 22px;
  background: var(--gold);
  color: var(--primary);
  font-weight: 800;
  border-radius: 4px;
  text-decoration: none;
}

.text-button {
  color: white;
  font-weight: 700;
  text-decoration: none;
  border-bottom: 1px solid rgba(255,255,255,.5);
  padding-bottom: 4px;
}

.heritage-section {
  padding: 85px 0;
}

.section-intro {
  display: grid;
  grid-template-columns: 1.5fr 1fr;
  gap: 60px;
  align-items: end;
  margin-bottom: 30px;
}

.section-intro h2,
.about-section h2 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(40px, 5vw, 58px);
  line-height: 1;
  margin: 10px 0 0;
  color: var(--primary);
}

.section-intro > p {
  color: var(--muted);
  line-height: 1.7;
}

.about-section {
  padding: 100px 0;
  background: #eaf0ef;
}

.about-section h2 {
  max-width: 750px;
  margin-bottom: 25px;
}

.about-section > .container > p:last-child {
  max-width: 750px;
  color: var(--muted);
  line-height: 1.8;
}

@media (max-width: 700px) {
  .hero {
    min-height: 600px;
  }

  .hero-content {
    padding-top: 60px;
    padding-bottom: 60px;
  }

  .hero-actions {
    flex-direction: column;
    align-items: flex-start;
  }

  .section-intro {
    grid-template-columns: 1fr;
    gap: 15px;
  }

  .heritage-section {
    padding: 60px 0;
  }
}
</style>