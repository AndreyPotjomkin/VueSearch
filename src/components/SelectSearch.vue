<template>
    <div class="group flex">
        <select v-model="city">
            <option value="Москва">Москва</option>
            <option value="Санкт-Петербур">Санкт-Петербург</option>
            <option value="Казань">Казань</option>
        </select>
        <select v-model="operation">
            <option value="Купить">Купить</option>
            <option value="Продать">Продать</option>
        </select>
        <select class="type" v-model="type">
            <option value="Офис">Офис</option>
            <option value="Апартаменты">Апартаменты</option>
        </select>
        <button class="button-search" @click="send()">Найти</button>
    </div>
</template>

<!--
с реальным апи в value лучше вставлять id, тут встатил текст для наглядности
-->

<script lang="ts">
import Vue from 'vue'
import Component from 'vue-class-component'

const Props = Vue.extend({
  props: {
    callback: Function
  }
})

    @Component
export default class SelectSearch extends Props {
        city: string = 'Москва'
        operation: string = 'Купить'
        type: string = 'Офис'

        send () {
          console.log(this.city, this.operation, this.type, this.callback())
          // шлём куда-нибудь в апи
        }
}
</script>
