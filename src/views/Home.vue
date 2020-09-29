<template>
  <div class="home">
    <ToTranslate
      v-model:word.trim="toTranslateObject.word"
      v-model:fromLanguage="toTranslateObject.fromLanguage"
    />
    <pre>{{ toTranslateObject }}</pre>

    <Translated
      v-model:toTranslate="translatedObject.toTranslate"
      v-model:fromLanguage="translatedObject.fromLanguage"
    />
    <pre>{{ translatedObject }}</pre>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive } from 'vue'
import ToTranslate from '@/components/ToTranslate.vue'
import Translated from '@/components/Translated.vue'

export default defineComponent({
  name: 'Home',
  components: {
    ToTranslate,
    Translated
  },
  setup() {
    const toTranslateObject = reactive({
      word: '',
      fromLanguage: 'Arabic'
    })
    const translatedObject = reactive({
      toTranslate: toTranslateObject.word,
      fromLanguage: toTranslateObject.fromLanguage,
      translated: ''
    })

    return {
      toTranslateObject,
      translatedObject
    }
  }
})
</script>
