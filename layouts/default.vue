<template>
  <div class="font-metropolis">
    <Banner />
    <Header />
    <Nuxt />
    <Footer />
  </div>
</template>

<style @lang="postcss">
@import url('@uppy/robodog/dist/robodog.css');

html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}
a.link {
  color: #00b9d4;
  transition: color 0.3s ease-in-out;
}
a.link:hover {
  color: #06a3bb;
}
.text-ugray {
  color: #8d969a;
  font-size: 16px;
  font-weight: bold;
  text-transform: uppercase;
}
.button-cta {
  text-transform: uppercase;
  border: 2px solid rgba(223, 224, 84, 1);
  border-radius: 31px;
  padding: 12px 48px;
  display: inline-block;
  background: transparent;
  @apply font-bold text-base md:text-xl;
}
.button-cta:hover {
  background: rgba(223, 224, 84, 1);
}
.text-purp {
  color: #382658;
}
</style>
