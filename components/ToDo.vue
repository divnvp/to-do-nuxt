<script setup>
import UIHeader from './UIHeader.vue';
import UIMain from './UIMain.vue';

</script>

<template>
  <div>
    <header class="margin-left">
      <UIHeader />
    </header>

    <main>
      <UIMain />
    </main>
  </div>
</template>

<style lang="scss">
.margin-left {
  margin-left: 40px;
}
</style>
