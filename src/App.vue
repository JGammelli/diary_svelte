<template>
  <div id="nav">
    <router-link :to="{name: 'Home'}">Home</router-link> 
    <router-link :to="{name: 'NewNote' }">Make new note</router-link>
  </div>
  <router-view/>
</template>


<style>

</style>
