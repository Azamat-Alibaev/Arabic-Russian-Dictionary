<template>
  <div>
    <div class="border-2 border-gray-500 m-2 p-2 rounded-lg">
      <span> {{ fromLanguage }}</span>
      word "<span>{{ toTranslate }}</span
      >" means 
    </div>
  </div>
</template>

<script>
export default {
  props: {
    toTranslate: {
      type: String,
      default: ''
    },
    fromLanguage: {
      type: String,
      default: ''
    }
  },
  setup() {
    return {
      translated: {
        type: String,
        default: ''
      }
    }
  }
}
</script>

<style lang="scss" scoped></style>
