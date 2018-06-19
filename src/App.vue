<template>
  <div class="container">
    <br>
    <div class="row">
      <div class="col-sm-12">
        <div class="alert alert-info">
          Click to remove/ Add item to list and click to randomize
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <button class="btn btn-primary" @click="foodList">Food</button>
        <button class="btn btn-danger" @click="clearList">Clear</button>
        
      </div>
    </div>

    <br>
    <app-new-item @itemAdded="newItem"></app-new-item>
    <app-grid :items="items" @itemDeleted="deleteItem"></app-grid>
    <button class="btn btn-primary" @click="randomItem">Random Pick</button>
    <div class="row">
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <div class="panel panel-default">
          <div class="panel-body  text-center" >
            {{ pick }}
          </div>
        </div>
      </div>
    </div>
    <app-maps></app-maps>

  </div>
</template>

<script>
  import Grid from './components/Grid.vue';
  import NewItem from './components/NewItem.vue';
  import Maps from './components/Maps.vue';
  

  export default {
    data: function () {
      return {
        items: [],
        pick: ''
      }
    },
    methods: {
      newItem(item) {
        // if (this.quotes.length >= 10) {
        //   return alert('Delete a quote')
        // }
        this.items.push(item);
      },
      deleteItem(i) {
        this.items.splice(i, 1);
        if(this.items.length == 0){
          this.pick='';
        }
      },
      randomItem() {
        var randomPick = '';
 
           randomPick = (this.items[Math.floor(Math.random() * this.items.length)]);
        
          this.pick = randomPick;

      },

      foodList(){
        var food = [ 'Pizza', 'Burger', 'Soup', 'Salad'];
        for(var i=0; i < food.length; i++){
          this.items.push(food[i]);
        }
      },
      clearList(){
        this.items.splice(0,this.items.length)
        this.pick = '';

      },
      
    },
    components: {
      appGrid: Grid,
      appNewItem: NewItem,
      appMaps: Maps
    }
  }
</script>

<style>
 body{
   padding: 50px 0;
 }

</style>
