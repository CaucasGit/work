<script>
	let styles = {
		color: '000000',
		opacity: 50
	};
	let blockActive = 0;
</script>

<style lang="scss">

  .container {
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    align-content: flex-end;
    font-family: Arial;

    & > * {
      height: 30%;
    }
  }

  .style {
    background: rgba(0,0,225,.5);
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding: 2%;
    margin-right: 5%;

    &__description {
      margin-bottom: 2%;

      & h1 {
        font-size: 24px;
        font-weight: 700;
        margin-bottom: 3%;
      }

    }

    &__inputs {
      margin-top: 5%;
    }

    &__window {
      width: 100px;
      height: 100px;
      border: 1px solid black;
    }
  }

  .block {
    padding: 2%;
    background: rgba(0,0,225,.5);
    display: flex;
    flex-direction: column;

    &__description {
      font-size: 24px;
    }

    &__container {
      display: flex;
      flex-grow: 3;
      justify-content: center;
      align-items: center;

    }

    &__child {
      transition: .2s;
      width: 50px;
      height: 10px;
      background: red;

      &:nth-child(2) {
        background: blue;
      }

      &:nth-child(3) {
        background: green;
      }

      &_active {
        transition: .2s;
        height: 100px;
      }

      &_choice {
        transition: .2s;
        height: 0;
      }
    }
  }


</style>

<div class="main">
    <div class="container">
        <div class="style">
            <div class="style__description">
                <h1>Задание №1</h1>
                <p>Стандартный цвет - белый, с черной обводкой. Непрозрачность - 50%</p>
                <div class="style__inputs">
                    <span>Цвет(HEX): # </span>
                    <input type="text"
                           on:input={e => styles.color = e.target.value}
                           value={styles.color}>
                    <span>Прозрачность: </span>
                    <input type="number"
                           on:input={e => styles.opacity = e.target.value}
                           value={styles.opacity}
                           max="100"
                           min="0">
                </div>
            </div>
            <div class="style__window"
                 style="opacity: {styles.opacity}%; background: #{styles.color}"></div>
        </div>

        <div class="block">

            <div class="block__description">
                <h1>Задание №2</h1>
            </div>

            <div class="block__container">
                <div class="block__child"
                     on:click={() => {blockActive === 1 ? blockActive = 0 : blockActive = 1}}
                     class:block__child_active={blockActive === 1}
                     class:block__child_choice={blockActive !== 0 && blockActive !== 1}></div>
                <div class="block__child"
                     on:click={() => {blockActive === 2 ? blockActive = 0 : blockActive = 2}}
                     class:block__child_active={blockActive === 2}
                     class:block__child_choice={blockActive !== 0 && blockActive !== 2}></div>
                <div class="block__child"
                     on:click={() => {blockActive === 3 ? blockActive = 0 : blockActive = 3}}
                     class:block__child_active={blockActive === 3}
                     class:block__child_choice={blockActive !== 0 && blockActive !== 3}></div>
            </div>
        </div>
    </div>
</div>