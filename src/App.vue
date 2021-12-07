<template>
  <div class="appVue">
    <vueHeader msg="Popular TV Shows" id="vueHeader"/>
    <vueCard id="vueCard"/>
  </div>
</template>

<script>
import vueHeader from './components/vueHeader.vue';
import 'bootstrap';
import 'bootstrap/dist/css/bootstrap.min.css';
import vueCard from './components/vueCard.vue';

export default {
  name: 'App',
  components: {
    vueHeader,
    vueCard
  }
}
</script>
