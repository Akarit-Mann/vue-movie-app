<template>
  <header>
    <router-link to="/">
      <h1><span>Vue</span>Movies</h1>
    </router-link>
  </header>
  <main>
    <router-view/>
  </main>
</template>

<style lang="scss">

  *{
    padding: 0;
    margin: 0;
    box-sizing: border-box;

    font-family: 'Fira Sans','sans-serif';
  }

  // he said this is scss feature!
  // but this is not work for my vue setup, you can try after watching his video
  // &::selection{
  //   background: transparent(#428883,.5);
  // }

  body{
    background-color: #35495E;
  }
  a{
    text-decoration: none;
  }

  header{
    display: flex;
    align-content: center;
    justify-content: center;
    padding: 10px 16px;
    background-color: #2C3D4E;
    box-shadow: 0 0 6px rgba(0, 0, 0, .1);
  }
  h1{
    color: #FFF;
    font-size: 28px;
  }
  span{
    color: #42B883;
  }


</style>
