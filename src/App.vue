<template>
  <div class="container">
    <AdaptiveComponent />
  </div>
</template>

<script>
import AdaptiveComponent from './components/AdaptiveComponent.vue';

export default {
  name: 'App',
  components: {
    AdaptiveComponent,
  },
};
</script>

<style>
.container {
  display: flex; /* Используем flexbox для расположения элементов */
  justify-content: space-between; /* Распределяем пространство между элементами */
  align-items: flex-start; /* Выровнять элементы по верхнему краю */
  padding: 20px; /* Отступ внутри контейнера */
}
</style>
