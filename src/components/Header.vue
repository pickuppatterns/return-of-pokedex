<template>
    <header>
        <h1>POKEDEX</h1>
        <img scr="http://pngimg.com/uploads/pokemon_logo/pokemon_logo_PNG14.png">
        <!--<img src="http://www.pokestadium.com/sprites/black-white/animated/shiny/pichu.gif">-->
        <div class="form">
          <label>
              NAME:
              <input class="name" type="text"
              v-model="filter.pokemon" >
          </label>
          <label>
          TYPE ONE:
          <select class="select" v-model="filter.type_1">
            <option value="">ANY</option>
            <option v-for="type in types" v-bind:key="type" v-bind:value="type">
              {{type}}
            </option>
          </select>
        </label>
        <label>
          TYPE TWO:
          <select class="select" v-model="filter.type_2">
            <option value="">ANY</option>
            <option v-for="type in types" v-bind:key="type" v-bind:value="type">
              {{type}}
            </option>
          </select>
        </label>
        <label>
              ATTACK
              <input class="number" type="number"
                  v-model.number="filter.attack" min="30" step="5">
          </label>
          <label>
              DEFENSE
              <input class="number" type="number"
                  v-model.number="filter.defense" min="30" step="5">
          </label>
          <label>
          SORT BY:
        <select class="sort" v-model="sort.field">
          <option value="pokemon">NAME</option>
          <option value="type_1">TYPE 02</option>
          <option value="attack">ATTACK</option>
          <option value="defense">DEFENSE</option>
        </select>
        <select v-model="sort.direction">
          <option value="1">Asc</option>
          <option value="-1">Desc</option>
        </select>
      </label>
    </div>
  </header>
</template>

<script>
export default {

  props: {
    filter: Object,
    types: Array,
    sort: Object
    
  }
};
</script>

<style>
  header {
    background: black;
    color: white;
  } 
  label{
    display:flex;
    justify-content:flex-end;

    }
  
  .form{
    border: 3px solid red;
    width:325px;
  }
  input {
   padding: 5px;
   background-color: #e8eeef;
   color: black;
   box-shadow: 0 1px 0 rgba(0,0,0,0.03) inset;
   font-size: 10px;
   text-align: right;
   font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
   margin-top: 10px;
  }
  input:focus {
  background-color: #f7ffe0;
  border-radius: 5px;
  outline:none;
}
.number {
  width:35px;
  text-align: right;

}
.name{
  width:275px;
  height:24px;

}
.select{width:75px;

}
.sort{


}
</style>
