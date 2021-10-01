<template>
  <div class="demo">
    <PbComponentHero button="SHOP"></PbComponentHero>
  </div>

</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import PbComponentHero from '@/components/PbComponentHero.vue';
// @ is an alias to /src

export default defineComponent({
  name: 'Home',
  components: {
    PbComponentHero,
  },
  setup() {
    const css = ref({
      backgroundColor: '#fff',
    });
    return {
      activeNames: ['1'],
      css,
    };
  },
});
</script>
<style lang="scss">
html,
body {
  margin: 0;
}
.demo {

}

</style>
