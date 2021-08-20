<template>
  <div class="search">
      <div class="panel upper">
          <SelectSearch v-show="!type" :callback="getData"></SelectSearch>
          <SearchInput v-show="type" :callback="getData"></SearchInput>
          <PriceBlock class="panel-price" v-show="displayPrice" ref="price"></PriceBlock>
          <SizeBlock class="panel-size" v-show="displaySize" ref="size"></SizeBlock>
      </div>
      <div class="panel lower">
          <div class="panel-element">
              <input type="checkbox" id="type" v-model="type" />
              <label class="switch" for="type">
                  <span class="slider round"></span>
              </label>
              <span class="label-main">Основной поиск</span>
              <span class="label-name">Искать по названию</span>
          </div>
          <div class="panel-element">
              <a href="#" class="button-price" @click="showPrice()" :class="{ active: displayPrice }">Цена</a>
              <a href="#" class="button-size" @click="showSize()" :class="{ active: displaySize }">Метраж</a>
          </div>
      </div>
  </div>
</template>

<!--
    Мне показалось или цена/метраж перепутаны в макете? Метраж по идее в м2 а цена в рублях, оставил как в макете
-->

<script lang="ts">
import Vue from 'vue'
import Component from 'vue-class-component'
import PriceBlock from './PriceBlock.vue'
import SizeBlock from './SizeBlock.vue'
import SelectSearch from './SelectSearch.vue'
import SearchInput from './SearchInput.vue'

    @Component({
      components: {
        PriceBlock,
        SizeBlock,
        SelectSearch,
        SearchInput
      }
    })

export default class SearchBar extends Vue {
        displayPrice: boolean = false
        displaySize: boolean = false
        type: boolean = false

        $refs!: {
            price: any,
            size: any,
        }

        showPrice () {
          this.displayPrice = !this.displayPrice
          this.displaySize = false
        }

        showSize () {
          this.displaySize = !this.displaySize
          this.displayPrice = false
        }

        getData () {
          if (this.displayPrice) {
            return this.$refs.price.get()
          }

          if (this.displaySize) {
            return this.$refs.size.get()
          }

          return {}
        }
}
</script>
