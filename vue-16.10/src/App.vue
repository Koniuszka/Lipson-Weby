<script setup>
  import {ref} from 'vue'
  import TreeItem from './components/TreeItem.vue';


  const treeData = ref ({
    name: 'drzewo',
    children: [
      {name: 'galonz-1'},
      {name: 'galonz-2',
        children: [
          {name: 'listek-1'},
          {name: 'listek-2',
            children: [
              {name: 'listek-listek-1'},
              {name: 'listek-listek-2'}
            ]
          },
          {name: 'listek-3'}
        ]
      },
      {name: 'galonz-3'},
      {name: 'galonz-4',
        children: [
          {name: 'listek-Alojzy'},
          {name: 'listek-Bonifacy',
            children: [
              {name: 'listek-listek-Bartlomiej'},
              {name: 'listek-listek-Jan-Tymoteusz-Sulkowski'}
            ]
          }
        ]
      }
    ]
  })
</script>

<template>
  <ul>
    <TreeItem class="item" :model="treeData" />
  </ul>
</template>

<style scoped>
.item{
  cursor: pointer;
  line-height: 1.5;
}

.bold{
  font-weight: bold;
}

.add{
  cursor: pointer;
  color: green;
}
</style>
