<template>
  <el-config-provider :size="size" :z-index="zIndex" :locale="locale">
    <router-view />
  </el-config-provider>
</template>

<script>
import { defineComponent } from 'vue';
import { ElConfigProvider } from 'element-plus';
import En from 'element-plus/dist/locale/en.mjs';
import { mapState } from 'pinia';
import store from '@/store';

export default defineComponent({
  components: {
    ElConfigProvider
  },
  computed: {
    ...mapState(store.app, ['size'])
  },
  data() {
    return {
      locale: En,
      zIndex: 3000
    };
  }
});
</script>

<style lang="scss">
html,
body,
#app {
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0;
}
</style>
