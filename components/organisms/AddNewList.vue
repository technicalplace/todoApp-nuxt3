<template>
  <form @submit.prevent="addList">
    <input 
      v-model="inputCardName"
      type="text"
      class="text-input"
      placeholder="Add new list"
      @focus="startEditing"
      @blur="finishEditing()"
    >
    <button type="submit" class="add-button" :class="inputCardName ? 'active' : ''" v-if="isEditing || titleExists">
      Add
    </button>
  </form>
</template>

<script setup lang="ts">
const storeTodoList = useTodoListStore();
const isEditing = ref<boolean>(false);
const inputCardName = ref<string>('');

const startEditing = (): void => {
  isEditing.value = true;
};
const finishEditing = (): void => {
  if (!inputCardName.value.length) {
    isEditing.value = false;
  }
};
const titleExists = computed(
  (): boolean => {
    return inputCardName.value.length > 0;
  }
);

const addList = (): void => {
  
};


</script>

<style scoped>
.text-input {
  padding: 15px 15px;
  width: calc(100% - 300px);
  background-color: #ccc;
  border-radius: 8px;
  cursor: pointer;
  border: none;
  font-family: "Noto Sans Japanese", "Noto Sans", 'system-ui', sans-serif;
  font-weight: 700;
  font-size: 20px;
  color: #242424;
  cursor: pointer;
  overflow: overlay;
}
.add-button {
  margin-top: 15px;
  padding: 15px 18px;
  background-color: #999;
  border: none;
  border-radius: 8px;
  font-family: "Noto Sans Japanese", "Noto Sans", 'system-ui', sans-serif;
  font-weight: 700;
  font-size: 18px;
  color: #fff;
}

.active {
  background-color: #00d78f;
}
</style>