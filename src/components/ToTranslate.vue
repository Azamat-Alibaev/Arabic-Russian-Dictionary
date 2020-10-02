<template>
  <div class="p-2 m-2 rounded">
    <input
      v-bind="$attrs"
      type="text"
      :value="toTranslate"
      @input="updateToTranslate"
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
    toTranslateModifiers: {
      type: Object,
      default: () => ({})
    },
    fromLanguage: {
      type: String,
      default: ''
    }
  },
  setup(props, { emit }) {
    const updateToTranslate = event => {
      let val = event.target.value
      if (props.toTranslateModifiers.capitalize) {
        val = val.charAt(0).toUpperCase() + val.slice(1)
      }

      emit('update:toTranslate', val)
    }
    return {
      languages,
      updateToTranslate
    }
  }
}
</script>

<style lang="css" scoped></style>
