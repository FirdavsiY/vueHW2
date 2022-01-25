<template>
  <div class="item">
    <div class="item-main">
      <p class="abcTitle">{{ block.title }}</p>

      <svg
        @click="$emit('delete_item', block.id)"
        class="krestik"
        viewBox="0 0 16 15"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M7.99992 14.3333C11.6818 14.3333 14.6666 11.3486 14.6666 7.66667C14.6666 3.98477 11.6818 1 7.99992 1C4.31802 1 1.33325 3.98477 1.33325 7.66667C1.33325 11.3486 4.31802 14.3333 7.99992 14.3333Z"
          stroke="white"
          stroke-linecap="white"
          stroke-linejoin="white"
        />
        <path
          d="M10 5.6665L6 9.6665"
          stroke="white"
          stroke-linecap="white"
          stroke-linejoin="white"
        />
        <path
          d="M6 5.6665L10 9.6665"
          stroke="white"
          stroke-linecap="round"
          stroke-linejoin="round"
        />
      </svg>
    </div>

    <p class="time">{{ block.time }}</p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  // Принимаем данные от родителя
  props: ["block", "delete_item"],
};
</script>

<style>
.item {
  width: 282px;
  height: 110px;
  background: #f0f0f0;
  border: 2px solid #007fff;
  box-sizing: border-box;
  border-radius: 10px;
  padding: 0px 25px 20px 25px;
  transition: 300ms ease;
  cursor: pointer;
  opacity: 1;
}
.item:hover {
  background-size: 110%;
  border: 2px solid rgba(255, 255, 255, 0.603);
  background: #faf9f9;
  box-shadow: 5px 5px 12px rgb(109, 109, 109);
}
.time {
  font-style: italic;
  font-weight: 500;
  font-size: 14px;
  line-height: 17px;
  /* identical to box height */

  color: rgba(0, 0, 0, 0.55);
}
.abcTitle {
  font-style: normal;
  font-weight: 600;
  font-size: 18px;
  line-height: 22px;

  color: #000000;
}
.item-main {
  display: flex;
  width: 100%;
  justify-content: space-between;

  align-items: center;
}
.item-main svg {
  transition: 200ms ease;
  width: 25px;
  height: 25px;
  display: block;
}
.item-main svg:hover {
  fill: rgb(196, 49, 49);
  stroke: rgb(196, 49, 49);
}
.active {
  opacity: 0;
  transition: 200ms;
}
</style>
