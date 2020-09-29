<template>
  <div>
    <ToTranslateForm
      v-model:word="toTranslateObject.word"
      v-model:fromLanguage="toTranslateObject.fromLanguage"
    />
    <pre>{{ toTranslateObject }}</pre>
  </div>
</template>

<script>
import { reactive } from 'vue'
import ToTranslateForm from '@/components/ToTranslateForm.vue'

export default {
  components: {
    ToTranslateForm
  },
  setup() {
    const toTranslateObject = reactive({
      word: '',
      fromLanguage: 'Arabic'
    })
    return {
      toTranslateObject
    }
  }
}
</script>

<style lang="scss" scoped></style>
