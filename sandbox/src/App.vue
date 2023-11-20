<script>
import BaseCounter from './components/BaseCounter.vue'
export default {
  components: {
    BaseCounter
  },
  data() {
    return {
      message: 'Hello World!',
      counterTitle: 'Counter Standard',
      count: 0,
      incrementAmount: 1,
      listOfNumber: [
        { name: 0, id: 'd126a6ec-5ded-4efc-a010-85fd5b3f5938', list: [1, 2, 3] },
        { name: 1, id: '4d2116c5-43af-46a7-a42b-d46cbd04854d', list: [1, 2, 3] },
        { name: 2, id: '1c81c7e5-5387-4471-a94a-ba5b7e97ada7', list: [1, 2, 3] },
        { name: 3, id: '759412e7-1236-4d54-892b-b203428982ec', list: [1, 2, 3] },
        { name: 4, id: '3b7792de-c9c8-460a-8070-ca3ab601e6c1', list: [1, 2, 3] }
      ]
    }
  }
}
</script>

<template>
  <h1>Hello</h1>
  <div id="app">
    <base-counter />
    <p v-if="message.length % 2 === 0">Even: {{ message }}</p>
    <p v-else>Odd: {{ message }}</p>
    <ul>
      <li v-for="item in listOfNumber" :key="item.id">
        {{ item.id }}
        <ul>
          <li v-for="(number, index) in item.list" :key="index">{{ number }}</li>
        </ul>
      </li>
    </ul>
  </div>
</template>
