<template>
  <div>
    <div v-bind="$attrs" class="w-1/2 block mr-auto ml-auto">
      <span> {{ fromLanguage }}</span>
      word "<span>{{ toTranslate }}</span
      >" means
    </div>
  </div>
</template>

<script>
export default {
  inheritAttrs: false,
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
