<template>
  <div class="recipes">
    <h1>Книга рецептов</h1>
    <router-link to="/">Добавить рецепт</router-link>
    <hr>
   <p>Здесь будут рецептыБкоторые ты написла</p>
    <p>Список пуст</p>
  </div>
</template>
<script>
export default {
  components: {},
  data () {
    return {
      recipes: []
    }
  },
  methods: {
    selectRecipe (id) {
      this.current = this.recipes.find(r => r.id === id)
    }
  }
}
</script>
