<template>
  <router-view />
</template>

<style lang="scss">
html,
* {
  font-family: "Inter", sans-serif;
}

.view {
  width: 100%;
  height: 100%;
}

.flex-box {
  display: flex;
  flex: 1 1 auto;
  flex-flow: column wrap;
  align-content: center;
  justify-content: center;
}
</style>
