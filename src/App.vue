<template>
  <div id="nav">
    <router-link :to="{name: 'Home'}" class="navLink">Your diary</router-link> 
    <router-link :to="{name: 'NewNote' }" class="navLink">Make new post</router-link>
  </div>
  <router-view/>
</template>


<style>
  *{
    text-decoration: none;
  }
  div{
    text-align: center;
  }
  ul{
    list-style: none;
  }
  #nav{
    padding: 1em;
  }
  .navLink{
    padding: 1em;
    font-size: 2em;
    color: black;
  }
  .navLink:hover{
    color: coral;
  }
</style>
