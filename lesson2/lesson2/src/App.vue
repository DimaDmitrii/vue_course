<script setup>
  import Card_template from './components/Card_template/Card_template.vue';
  import { ref } from "vue"

  const cards_info = ref([
    {name: "div", value: "The div element has no special meaning at all. It represents its children. It can be used with the class, lang, and title attributes to mark up semantics common to a group of consecutive elements."},
    {name: "header", value: "The header element represents introductory content for its nearest ancestor sectioning content or sectioning root element. A header typically contains a group of introductory or navigational aids. When the nearest ancestor sectioning content or sectioning root element is the body element, then it applies to the whole page."}, 
    {name: "head", value: "The head element represents a collection of metadata for the Document."}, 
    {name: "h1", value: "The h1 element represents a section heading."}, 
    {name: "h2", value: "The h2 element represents a section heading."}, 
    {name: "h3", value: "The h3 element represents a section heading."}, 
    {name: "h4", value: "The h4 element represents a section heading."}, 
    {name: "h5", value: "The h5 element represents a section heading."}, 
    {name: "h6", value: "The h6 element represents a section heading."},
    {name: "h7", value: "no <h7> in html."}])
  const input_data = ref ("")
</script>

<template>
  <div >
    <input type="text" placeholder="Поиск" v-model="input_data">
    {{ input_data }}
  </div>

  <div v-for="card in cards_info">
    <div v-if="card.name.toLocaleLowerCase().includes(input_data)">
      <Card_template></Card_template>
      name: {{ card.name }} == value: {{ card.value }}
    </div>
  </div>
</template>
