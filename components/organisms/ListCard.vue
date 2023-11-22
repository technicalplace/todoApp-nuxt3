<template>
  <div class="list">
    <div class="listheader">
      <p class="list-title">
        {{ title }}
        <span class="list-counter">total:{{ totalCardInList }}</span>
      </p>
      <div class="deletelist" @click="removeList">×</div>
    </div>
    <card-view
      v-for="(item, index) in cards"
      :body="item.body"
      :key="item.id"
      :cardIndex="index"
      :listIndex="listIndex"
    />
  </div>
</template>

<script setup lang="ts">
const title = ref('タイトル');
</script>

<style scoped>
.listheader {
  width: 100%;
  margin: 0;
}
.list-title {
  margin: 0 20px;
  font-size: 24px;
  color: aliceblue;
}
.deletelist {
  position: absolute;
  top: 6px;
  right: 14px;
  font-size: 28px;
}
</style>