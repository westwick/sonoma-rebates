<template>
  <div>
    <Nuxt />
  </div>
</template>

<style>
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
.button-cta {
  text-transform: uppercase;
  border: 2px solid rgba(223, 224, 84, 1);
  border-radius: 31px;
  padding: 16px 48px;
  display: inline-block;
  background: transparent;
  font-weight: bold;
  font-size: 20px;
}
.button-cta:hover {
  background: rgba(223, 224, 84, 1);
}
</style>
