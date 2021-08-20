<template>
    <div class="panel-container">
        <button class="add-button">Добавить цену</button>
        <div class="group">
            <input type="number" placeholder="От" v-model.number="from" />
            <input type="number" placeholder="До" v-model.number="to" />
            <label>м²</label>
        </div>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Component from 'vue-class-component'

    @Component
export default class PriceBlock extends Vue {
        from = null
        to = null
        get () {
          return {
            from: this.from,
            to: this.to
          }
        }
}
</script>
