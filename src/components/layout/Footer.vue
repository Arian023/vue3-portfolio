<template>
  <footer class="footer">
    <div class="container">
      <p class="footer__copyright">
        <em>Hecho con ♥ por Arian © 2023.</em>
        <span
          >El formato del sitio se encuentra bajo
          <a href="https://github.com/Arian023/vue3-portfolio/blob/main/LICENSE"
            >licencia MIT</a
          >.</span
        >
      </p>
      <div class="built-tech">
        <AppLink
          to="https://www.netlify.com/"
          aria-label="Hosteado en Netlify"
          title="Hosteado en Netlify"
          is-external>
          <NetlifyLogoSVG />
        </AppLink>
        <AppLink
          to="https://vuejs.org/"
          aria-label="Hecho con Vue"
          title="Hecho con Vue.js"
          is-external>
          <VueSVG />
        </AppLink>
        <AppLink
          to="https://github.com/Arian023"
          aria-label="Código fuente en Github"
          title="Código fuente en Github"
          is-external>
          <OctocatSVG />
        </AppLink>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  width: 100%;
  height: 60px;
  border-top: 1px solid var(--color-gray-800);
  margin-top: 40px;
}

.footer .container {
  align-items: center;
  justify-content: space-between;
}

.footer__copyright em {
  text-emphasis: unset;
  font-style: normal;
  font-weight: 700;
}

.footer__copyright span {
  margin-left: 8px;
  font-weight: 700;
  opacity: 0.6;
  color: var(--text-color-default);
}

.footer .built-tech {
  flex-basis: 20%;
  align-self: center;
}

.footer .built-tech svg {
  max-width: 37px;
}

.footer .built-tech a + a {
  margin-left: 30px;
}

@media screen and (max-width: 1024px) {
  .container {
    padding: 18px;
  }

  .footer {
    font-size: var(--text-base);
  }
}

@media screen and (max-width: 768px) {
  .footer .built-tech {
    flex-basis: 25%;
  }
}

@media screen and (max-width: 425px) {
  .footer {
    height: 100%;
  }

  .footer .container {
    flex-direction: column;
    text-align: center;
  }

  .footer__copyright {
    order: 2;
  }

  .footer .built-tech {
    order: 1;
    width: 100%;
    flex: 1;
    margin-bottom: 10px;
  }
}
</style>
