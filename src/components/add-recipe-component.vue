<template>
  <form class="form" @submit.prevent="Submit">
    <h1>Добавить рецепт</h1>
    <div v-if="visible">
      <div class="input">
        <input v-model="title" type="text" placeholder="Название рецепта">
      </div>
      <div class="input">
        <input v-model="description" type="text" placeholder="Описание рецепта">
      </div>
    </div>

    <div class="buttons">
      <button class="btn" type="submit" :disabled="!valid">Создать</button>
      <button class="btn secondary" type="button" @click="toggleForm">{{ visible ? 'Убрать форму ' : 'Показать форму'}}</button>
    </div>
  </form>
</template>

<script>
export default {
  name: 'addRecipeComponent',
  data () {
    return {
      title: '',
      description: '',
      visible: true
    }
  },
  props: {
    onAdd: {
      type: Function,
      required: true
    }
  },
  methods: {
    toggleForm () {
      this.visible = !this.visible
    },
    Submit () {
      const recipe = {
        title: this.title.trim(),
        // метод trim() удаляет произвольные пробелы в начале и в конце строки
        description: this.description.trim(),
        id: Date.now().toString()
      //  метод Date.now() возвращает колличество миллисекунд прошедших с января 1970г;
      //   toString() приводит данное значение к строке
      }
      this.title = this.description = ''
      //  очищаем формы
      this.onAdd(recipe)
    // добавляем в функцию addRecipe значения recipe
    }
  },
  computed: {
    valid () {
      return this.title.trim() && this.description.trim()
      // функция отслеживает когда значения title и description пустые
    }
  }
}

</script>

<style>
  .form {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 1rem;
    border: 1px solid #eee;
    margin-bottom: 1rem;
  }

  .form h1 {
    margin: 0;
    margin-bottom: 1rem;
  }

  .input {
    margin-bottom: 1rem;
  }

  .input input {
    border: 1px solid #ccc;
    border-radius: 5px;
    padding: 5px 8px;
    width: 400px;
  }

  .buttons {
    width: 400px;
    display: flex;
    justify-content: space-around;
  }
</style>
