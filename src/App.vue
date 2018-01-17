<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12 col-sm_8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <h1>Filters & Mixins</h1>
                <p>{{ text | toUpperCase | to-lowercase }}</p>
                <hr>
                <button @click="fruits.push('Berries')" class="btn btn-primary">Add New Item</button>
                <input type="text" v-model="filterText">
                <ul>
                    <li v-for="item in filteredFruits">{{ item }}</li>
                </ul>
                <hr>
                <app-list></app-list>
            </div>
        </div>
    </div>
</template>

<script>
    import List from './List.vue'
    import { fruitMixin } from './fruitMixin.js'
    export default {
        data() {
            return {
                text: 'hello there',
            }
        },
        filters: {
            toUpperCase(value) {
                return value.toUpperCase();
            }
        },
        components: {
            appList : List
        },
        mixins: [fruitMixin]
    }
</script>

<style>

</style>
