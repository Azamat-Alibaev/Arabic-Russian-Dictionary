<template>
  <div>
    <TranslatedForm
      v-model:toTranslate="translatedObject.toTranslate"
      v-model:fromLanguage="translatedObject.fromLanguage"
    />
    <pre>{{ translatedObject }}</pre>
  </div>
</template>

<script>
import TranslatedForm from '@/components/TranslatedForm.vue'
export default {
  props: {
    toTranslate: {
      type: Object,
      required: true
    }
  },
  components: {
    TranslatedForm
  },
  setup() {
    const translatedObject = {
      toTranslate: 'Azamat',
      fromLanguage: 'Arabic',
      translated: ''
    }
    return {
      translatedObject
    }
  }
}
</script>

<style lang="scss" scoped></style>
