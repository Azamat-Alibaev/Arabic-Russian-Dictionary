<template>
  <div class="p-2 m-2 rounded text-gray-400">
    <form>
      <input
        class="element-border-and-bg "
        type="text"
        :value="word"
        @input="$emit('update:word', $event.target.value)"
      />
      <select
        class="element-border-and-bg"
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
    </form>
    <input type="submit" class="element-border-and-bg" />
  </div>
</template>

<script>
const languages = ['Russian', 'Arabic']
export default {
  props: {
    word: {
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

<style lang="css" scoped>
.element-border-and-bg {
  @apply border-gray-600 p-1 m-1 bg-gray-800  rounded-full border-2;
}
.element-border-and-bg:hover {
  @apply bg-gray-300 text-gray-800;
}
</style>
