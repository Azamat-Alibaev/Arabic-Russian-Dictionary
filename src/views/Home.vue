<template>
  <div class="home">
    <ToTranslate
      v-model:toTranslate.trim="toTranslateObject.toTranslate"
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
import { defineComponent, reactive, watchEffect } from 'vue'
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
      toTranslate: '',
      fromLanguage: 'Arabic'
    })
    const translatedObject = reactive({
      toTranslate: toTranslateObject.toTranslate,
      fromLanguage: toTranslateObject.fromLanguage,
      translated: ''
    })

    watchEffect(() => {
      translatedObject.toTranslate = toTranslateObject.toTranslate
      translatedObject.fromLanguage = toTranslateObject.fromLanguage
    })

    return {
      toTranslateObject,
      translatedObject
    }
  }
})
</script>
