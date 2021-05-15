<template >

  <div class="container">
    <div class="style">
      <div class="style__description">
        <h1>Задание №1</h1>
        <p>Стандартный цвет - белый, с черной обводкой. Непрозрачность - 50%</p>
        <div class="style__inputs">
          <span>Цвет(HEX): # </span>
          <input type="text" v-model="styles.color">
          <span>Прозрачность: </span>
          <input type="number" max="100" min="0" v-model="styles.opacity">
        </div>
      </div>
      <div class="style__window" :style="{background: '#' + styles.color, opacity: styles.opacity + '%'}"></div>
    </div>

    <div class="block">

      <div class="block__description">
        <h1>Задание №2</h1>
      </div>

      <div class="block__container">
        <div class="block__child"
             @click="blockActive === 1 ? blockActive = 0 : blockActive = 1"
             :class="{block__child_active: blockActive === 1,
           block__child_choice: blockActive != 0 && blockActive != 1}"></div>
        <div class="block__child"
             @click="blockActive === 2 ? blockActive = 0 : blockActive = 2"
             :class="{block__child_active: blockActive === 2,
           block__child_choice: blockActive != 0 && blockActive != 2}"></div>
        <div class="block__child"
             @click="blockActive === 3 ? blockActive = 0 : blockActive = 3"
             :class="{block__child_active: blockActive === 3,
           block__child_choice: blockActive != 0 && blockActive != 3}"></div>
      </div>
    </div>

  </div>

</template>

<script>


export default {
  name: "App",
  data() {
    return {
      styles: {
        color: 'FFFFFF',
        opacity: 50
      },
      blockActive: 0
    }
  },
  methods: {

  }
}
</script>

<style lang="scss" src="./assets/scss/style.scss">

</style>