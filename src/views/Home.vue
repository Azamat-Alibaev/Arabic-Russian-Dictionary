<template>
  <div class="home">
    <ToTranslate />
    <Translated
      :toTranslate="{ toTranslate: 'Azamat', fromLanguage: 'Arabic' }"
    />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import ToTranslate from '@/components/ToTranslate.vue'
import Translated from '@/components/Translated.vue'

export default defineComponent({
  name: 'Home',
  components: {
    ToTranslate,
    Translated
  }
})
</script>
