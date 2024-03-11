<template>
  <div class="container">
    <aside>
      <HeroAvatar>
        <img
          src="@/assets/img/profile.jpg"
          alt="Foto de Arian"
          width="140"
          loading="lazy" />
      </HeroAvatar>
      <BinaryTextSVG />
    </aside>
    <main id="main-content">
      <article class="about-content">
        <h1 class="about-content__headline">Sobre mí</h1>
        <p>👋 ¡Hola! ¿Cómo estás?</p>
        <p>
          Me llamo Arian <small>(como Adrián, ¡pero sin la D!)</small>, y soy un <strong>Técnico Universitario en Desarrollo Web</strong>, con dicho título alcanzado en la Universidad Nacional del Comahue en el año 2021. 
        </p>
        <p>
          Mientras estuve estudiando, me dediqué mayormente al Soporte Técnico TI en campo, pero estoy muy dispuesto a dar el salto en mi carrera profesional por el lado de la ingeniería de software.
        </p>
        <p>
          Por ello, estuve realizando diversos cursos y conceptos, entre los que puedo mencionar: accesibilidad y experiencia de usuario, edición de imágenes mediante Adobe Photoshop, conceptos de computación en la nube (léase AWS y GCP), frameworks de PHP y Javascript <small>(¡como Vue, con el que está armado este sitio!)</small>.
        </p>
        <p>
          En fin, una mezcla bastante variada de contenido, ya que uno hoy en día no puede quedarse atrás con la tecnología. Pero más allá de la programación, estoy interesado en la tecnología como hobby, así como el gaming en PC.
        </p>
        <SocialMediaIcons boxed />
      </article>
    </main>
  </div>
</template>

<script setup>
import { useRoute } from 'vue-router'
import config from '../config/siteconfig.json'

const title = 'Sobre mí • Arian Acevedo'
const { description } = config
const route = useRoute()

useHead({
  title,
  meta: [
    {
      name: 'description',
      content: description,
    },
    { property: 'og:type', content: 'website' },
    { property: 'og:title', content: title },
    { property: 'og:description', content: description },
    { property: 'og:url', content: `${config.siteUrl}${route.path}` },
    {
      property: 'twitter:title',
      content: title,
    },
    {
      property: 'twitter:description',
      content: description,
    },
  ],
})
</script>

<route lang="yaml">
meta:
  layout: default
</route>

<style lang="css" scoped>
:global(#app) {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.container {
  flex-flow: row wrap;
  padding: 3rem 0;
}

main {
  padding: 1.2rem 2.4rem;
}

.about-content {
  .about-content__headline {
    font-size: var(--text-2xl);
  }

  p {
    font-size: var(--text-lg);
    opacity: 0.8;
    max-width: 71ch;
  }
}

.binary-text-svg {
  font-family: var(--font-mono);
  font-size: var(--text-xl);
  position: absolute;
  left: 282px;
  top: 387px;
  opacity: 0.3;

  & :deep(tspan) {
    --text-delay: 500ms;

    opacity: 0;
    animation: pulse-spread 3s var(--text-delay) ease-out infinite alternate;

    &:nth-child(1) {
      --text-delay: 500ms;
    }

    &:nth-child(2) {
      --text-delay: 1s;
    }

    &:nth-child(3) {
      --text-delay: 1.5s;
    }

    &:nth-child(4) {
      --text-delay: 2s;
    }

    &:nth-child(5) {
      --text-delay: 2.5s;
    }

    &:nth-child(6) {
      --text-delay: 3s;
    }
  }
}

@keyframes pulse-spread {
  0% {
    opacity: 0;
  }

  100% {
    opacity: 0.3;
  }
}

@media screen and (min-width: 426px) and (max-width: 768px) {
  aside {
    margin-left: 40px;
    padding: 0 2.4rem 0 0;
  }
}

@media screen and (max-width: 425px) {
  aside {
    padding: 0 1rem;
  }

  .container {
    height: 100%;
  }

  .binary-text-svg {
    top: 50%;
    left: 0;
    bottom: 0;
  }
}
</style>
