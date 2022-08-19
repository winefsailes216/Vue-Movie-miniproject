<template>
  <header>
    <router-link to="/">
      <h1><span>Vue</span>Movies</h1>
    </router-link>
  </header>
  <main>
    <router-view />
  </main>
  <footer></footer>
</template>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Fira "Gill Sans", "Gill Sans MT", Calibri, "Trebuchet MS",
    sans-serif;

  &::selection {
    background: lightblue;
  }
  body {
    background-color: gray;
  }
  a {
    text-decoration: none;
  }
  header {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 10px 16px;
    background-color: darkgray;
    box-shadow: 0px 0px 6px black;
    h1 {
      color: white;
      font-size: 28px;
    }
    span {
      color: green;
    }
  }
}
</style>
