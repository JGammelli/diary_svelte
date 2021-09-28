<template>
  <div class="home">
    <ViewDiary/>
  </div>
</template>

<script>


  import ViewDiary from '../components/ViewDiary.vue'; 

  export default {
    name: 'Home',
    
    components: {
      ViewDiary
    }
  }
</script>
