<template>
    <div class="panel-container">
        <div class="group">
            <input type="number" placeholder="От" v-model.number="from" />
            <input type="number" placeholder="До" v-model.number="to" />
            <select v-model="currency">
                <option value="rub">₽/месяц</option>
                <option value="usd">$/месяц</option>
            </select>
        </div>
        <button class="add-button">Добавить метраж</button>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Component from 'vue-class-component'

    @Component
export default class SizeBlock extends Vue {
        from = null
        to = null
        currency:string = 'rub'
        get () {
          return {
            from: this.from,
            to: this.to,
            currency: this.currency
          }
        }
}
</script>
