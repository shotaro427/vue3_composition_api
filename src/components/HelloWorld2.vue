<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <input v-model="queryRef" type="text">
    <ul>
      <li v-for="(item, i) in prefectures" :key="i">{{ item }}</li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { useFilter } from '../composables/use-filter'

export default defineComponent({
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  setup() {
    const { queryRef, prefectures } = useFilter()
    return { queryRef, prefectures }
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
