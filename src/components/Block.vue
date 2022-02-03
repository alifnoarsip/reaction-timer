<template>
  <div class="container">
    <button class="button" v-on="click">
      <span class="title">play</span>
    </button>
  </div>
</template>

export default{

}

<style scoped>
.container {
  display: flex;
  justify-content: center;
  height: 100%;
  width: 100%;
}
.button {
  display: flex;
  background-color: green;
  width: 100px;
  height: 30px;
  justify-content: center;
  align-items: center;
  border-radius: 5px;
}
.title {
  color: white;
}
</style>