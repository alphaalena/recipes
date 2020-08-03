<template>
  <div class="container">
    <add-recipe-component/>
    <hr>
    <div class="columns">
      <recipe-list-component/>
      <recipe-detail-component/>
    </div>
  </div>
</template>

<script>
import AddRecipeComponent from '../components/add-recipe-component'
import RecipeListComponent from '../components/recipe-list-component'
import RecipeDetailComponent from '../components/recipe-detail-component'

export default {
  name: 'Home',
  components: {
    RecipeDetailComponent,
    RecipeListComponent,
    AddRecipeComponent
  }
}
</script>
<style>
  a {
    text-decoration: none;
    color: darkblue;
    transition: .3s all ease;
  }

  .center {
    text-align: center;
  }

  a:hover {
    cursor: pointer;
    opacity: .7;
    text-decoration: underline;
  }

  .container {
    max-width: 1000px;
    margin: 0 auto;
    height: 100vh;
  }

  .columns {
    display: flex;
  }

  .detail, .list {
    width: 50%;
    border: 1px solid #eee;
  }

  .list {
    border-right: 0;
  }

  .btn {
    border-radius: 5px;
    background: darkblue;
    color: #fff;
    padding: 6px 14px;
    cursor: pointer;
  }

  .btn:disabled {
    background-color: #eee;
    color: black;
    cursor: not-allowed;
  }

  .btn.remove {
    background: darkred;
  }

  .btn.secondary {
    background: grey;
  }
</style>
