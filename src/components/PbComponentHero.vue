<template>
  <div class="hero" :style="bgStyle">
    <div class="info">
      <div class="sub-title">{{subTitle}}</div>
      <div class="title">{{title}}</div>
      <div class="desc">{{desc}}</div>
      <a :href="buttonUrl">
        <span class="button" v-if="button">{{button}}</span>
      </a>

    </div>
  </div>
</template>

<script lang="ts">
import { computed, defineComponent } from 'vue';

export default defineComponent({
  name: 'PbPanelBackground',
  props: {
    backgroundImage: {
      type: String,
    },
    height: {
      type: Number,
      default: 500,
    },
    subTitle: {
      type: String,
      default: 'GIFT GUIDE',
    },
    title: {
      type: String,
      default: 'here\'s to joy',
    },
    desc: {
      type: String,
      default: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do.',
    },
    button: {
      type: Object,
    },
    buttonUrl: {
      type: String,
    },
  },
  components: {
  },
  setup(props, context) {
    const bgStyle = computed(() => ({
      backgroundImage: props.backgroundImage ? `url(${props.backgroundImage})` : '',
      height: `${props.height}px`,
    }));
    return {
      bgStyle,
    };
  },
});
</script>
<style lang="scss">
.hero {
  background-image: url('../assets/bg.jpg');
  background-size: cover;
  background-position: center;
  display: flex;
  justify-content: center;
  align-items: center;

  .info {
    text-align: center;
    .sub-title {
      font-size: 26px;
      font-weight: 600;
    }
    .title {
      font-size: 72px;
      font-weight: 400;
      margin-bottom: 10px;

    }
    .button {
      display: inline-block;
      -webkit-box-align: stretch;
      align-items: stretch;
      position: relative;
      flex-shrink: 0;
      box-sizing: border-box;
      margin-top: 20px;
      appearance: none;
      padding: 15px 25px;
      background-color: rgb(74, 74, 74);
      color: white;
      border-radius: 4px;
      text-align: center;
      cursor: pointer;
      width: auto;
      align-self: center;
    }
  }
}
</style>
