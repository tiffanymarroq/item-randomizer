<template>
    <div class="row">
        <app-item v-for="(item, i) in items" @click.native ="deleteItem(i)">{{ item }}</app-item>
    </div>
</template>

<script>
import Item from './Item.vue';
export default {
    props: ['items'],
    components: {
        appItem: Item,
    },
    methods: {
        deleteItem(i){
            this.$emit('itemDeleted', i);
        }
    }
}
</script>
<style>
</style>


