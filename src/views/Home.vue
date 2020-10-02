<template>
  <div class="home">
    <ToTranslate
      v-model:toTranslate.trim="toTranslateObject.toTranslate"
      v-model:fromLanguage="toTranslateObject.fromLanguage"
      class="element-border-and-bg"
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

<style>
.element-border-and-bg {
  @apply border-gray-600 p-1 m-1 bg-gray-800  rounded-full border-2;
}
.element-border-and-bg:hover {
  @apply bg-gray-300 text-gray-800;
}
</style>
