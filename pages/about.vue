<template>
  <main>
    <v-card>
      <v-card-title>
        自己紹介
      </v-card-title>
      <v-card-text>
        会津大学27期。
      </v-card-text>
    </v-card>
    <v-card>
      <v-card-title>
        興味のある分野
      </v-card-title>
      <v-card-text>
        Webサーバーサイド
      </v-card-text>
    </v-card>
    <v-card>
      <v-card-title>
        できる技術
      </v-card-title>
      <v-card-text>
        <div v-for="item in techItems">
          <v-list dense>
            {{ item.name }}
            <v-list-item v-for="(subItem, i2) in item.items" :key="i2">
              <v-list-item-icon>
                <v-icon v-text="subItem.icon"/>
              </v-list-item-icon>
              <v-list-item-content v-text="subItem.name"/>
            </v-list-item>
          </v-list>
        </div>
      </v-card-text>
    </v-card>
  </main>
</template>

<script lang="ts">
import Vue from 'vue'
import Component from "vue-class-component"


interface techItem{
  name:string
  icon:string
}


@Component
export default class about extends Vue{
  name = "about.vue"
  techItems: {name: string, items: techItem[]}[] = [{
    name: "自信あり", items: [
      {icon: "mdi-language-python", name: "Python"},
      {icon: "mdi-language-go", name: "Go"}
    ]},
    {name: "普通", items: [
        {icon: "mdi-language-typescript", name: "Typescript"},
        {icon: "mdi-docker", name: "Docker"}
      ]},
    {name: "ちょっとだけ", items: [
        {icon: "mdi-language-c", name: "C"},
        {icon: "mdi-language-java", name: "Java"},
        {icon: "mdi-vuejs", name: "Vue"},
        {icon: "mdi-nuxt", name: "Nuxt.js"}
      ]}
  ]
}
</script>

<style scoped>

</style>
