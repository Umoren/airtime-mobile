<template>
  <div>
    <nuxt />
  </div>
</template>

<style>
/* @import url('https://fonts.googleapis.com/css2?family=Karla:wght@400;700&family=Roboto&display=swap'); */
html {
  font-family:
    'Karla', 'Roboto','Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  line-height: 1.5;
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
  font-family: 'Karla', sans-serif;
}

.button--wallet{
    display: inline-block;
    border-radius: 4px;
    border: 1px solid rgba(95,75,139,1);
    color: #ffffff;
    background: rgba(95,75,139,1);
    text-decoration: none;
    padding: 10px ;
    width: 100%;
    text-align: center;
    margin-bottom: 20px;
    font-size: 1.5rem;
    font-family: 'Karla', sans-serif;
}

.button--wallet:hover {
  color: #fff;
  background-color: rgba(95,75,139,1);
  text-decoration: none;
  
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>
