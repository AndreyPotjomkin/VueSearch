<template>
    <div class="group flex">
        <input type="text" v-model="text" placeholder="Введите название объекта(бизнес-центра, торгового центра, новостройки, логопарка)" />
        <button class="button-search" @click="send()">Найти</button>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Component from 'vue-class-component'

const Props = Vue.extend({
  props: {
    callback: Function
  }
})

    @Component
export default class SearchInput extends Props {
        text: string = ''

        send (): string {
          if (this.text !== null && this.text.trim() !== null) {
            console.log(this.text, this.callback())
            // шлём куда-нибудь в апи
          } else {
            console.log('пусто')
          }

          return ''
        }
}
</script>
