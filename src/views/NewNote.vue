<template>
  <div class="newNote">
      <DiaryForm/>
  </div>
</template>

<script>

import DiaryForm from '../components/DiaryForm.vue'; 

export default {
  name: 'NewNote',
  components: {
    DiaryForm
  }
}
</script>
