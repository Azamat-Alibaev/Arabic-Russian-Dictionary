<template>
  <div class="home">
    <ToTranslate />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import ToTranslate from '@/components/ToTranslate.vue'

export default defineComponent({
  name: 'Home',
  components: {
    ToTranslate
  }
})
</script>
