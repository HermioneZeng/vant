<template>
  <demo-section>
    <transition name="fade">
      <div class="mask" v-show="show" @click="show=false"></div>
    </transition>
    
    
    <demo-block :title="$t('basicUsage')">
      <van-switch v-model="checked" />
    </demo-block>

    <demo-block :title="$t('disabled')">
      <van-switch
        v-model="checked"
        disabled
      />
    </demo-block>

    <demo-block :title="$t('loadingStatus')">
      <van-switch
        v-model="checked"
        loading
      />
    </demo-block>

    <demo-block :title="$t('customSize')">
      <van-switch
        v-model="checked2"
        size="24px"
      />
    </demo-block>

    <demo-block :title="$t('customColor')">
      <van-switch
        v-model="checked3"
        active-color="#07c160"
        inactive-color="#f44"
      />
    </demo-block>

    <demo-block :title="$t('asyncControl')">
      <van-switch
        :value="checked4"
        @input="onInput"
      />
    </demo-block>
  </demo-section>
</template>

<script>
export default {
  i18n: {
    'zh-CN': {
      title: '提醒',
      message: '是否切换开关？',
      customSize: '自定义大小',
      customColor: '自定义颜色',
      asyncControl: '异步控制'
    },
    'en-US': {
      title: 'Confirm',
      message: 'Are you sure to toggle switch?',
      customSize: 'Custom Size',
      customColor: 'Custom Color',
      asyncControl: 'Async Control'
    }
  },

  data() {
    return {
      checked: true,
      checked2: true,
      checked3: true,
      checked4: true,
      show:false
    };
  },

  methods: {
    onInput(checked) {
      /*this.$dialog.confirm({
        title: this.$t('title'),
        message: this.$t('message')
      }).then(() => {
        this.checked4 = checked;
      });*/
      this.show=!show
    }
  }
};
</script>

<style lang="less">
.demo-switch {
  .van-switch {
    margin: 0 15px;
  }
}
.mask{
    position: absolute;
    top:0;
    left:0;
    right:0;
    bottom:0;
    background:#000;
    opacity: 0.6;
  }
  .fade-enter-active, .fade-leave-active {
    transition: opacity .5s;
  }
  .fade-enter, .fade-leave-to {
    opacity: 0;
  }
</style>
