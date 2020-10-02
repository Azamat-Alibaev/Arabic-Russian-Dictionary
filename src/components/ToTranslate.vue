<template>
  <div class="p-2 m-2 rounded">
    <input
      v-bind="$attrs"
      class=""
      type="text"
      :value="toTranslate"
      @input="$emit('update:toTranslate', $event.target.value)"
    />
    <select
      v-bind="$attrs"
      name="fromLanguage"
      @change="$emit('update:fromLanguage', $event.target.value)"
    >
      <option
        v-for="lang of languages"
        :value="lang"
        :key="lang"
        :selected="lang === fromLanguage"
        >{{ lang }}
      </option>
    </select>
  </div>
</template>

<script>
const languages = ['Russian', 'Arabic']
export default {
  inheritAttrs: false,
  components: {},
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
      languages
    }
  }
}
</script>

<style lang="css" scoped></style>
