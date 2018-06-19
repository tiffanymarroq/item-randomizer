<template>
  <div class="row">
    <form>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <label for="">Add item</label>
        <textarea class="form-control" rows="3" v-model="item"></textarea>
      </div>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <button class="btn btn-primary" @click.prevent="createNew" >Add</button>
      </div>
    </form>
  </div>
</template>

<script>
  export default {
    data: function () {
      return {
        item: ''
      };
    },
    methods: {
      createNew() {
          this.$emit('itemAdded', this.item);
          this.item ='';
      }
    }
  }
</script>
<style>
</style>
