<template>
  <div class="root-home">
    <div class="btn-container"></div>
    <UIButton
      @click="onClick" 
      :xsmall="xsmall"
      :small="small"
      :large="large"
      :xlarge="xlarge"
      :tile="tile"
      :rounded="rounded"
      :circle="circle"
      :disabled="disabled"
      >yyr 刘送命</UIButton
    >
    <div class="btn-group">
      <UIButton class="btn" @click="resize('xsmall')">超小</UIButton>
      <UIButton class="btn" @click="resize('small')">小</UIButton>
      <UIButton class="btn" @click="resize('normal')">普通</UIButton>
      <UIButton class="btn" @click="resize('large')">大</UIButton>
      <UIButton class="btn" @click="resize('xlarge')">超大</UIButton>
    </div>

    <div class="btn-group">
      <UIButton class="btn" @click="changeRadius('tile')">矩形</UIButton>
      <UIButton class="btn" @click="changeRadius('normal')">正常</UIButton>
      <UIButton class="btn" @click="changeRadius('rounded')">半圆</UIButton>
      <UIButton class="btn" @click="changeRadius('circle')">圆角</UIButton>
    </div>

    <div class="btn-group">
      <UIButton class="btn" @click="changeDisabled('disabled')">禁用</UIButton>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import UIButton from '@/components/UiKit/UIButton.vue'
@Component({
  components: {
    UIButton,
  },
})
export default class Home extends Vue {
  // eslint-disable-next-line
  private xsmall: boolean = false // eslint-disable-next-line
  private small: boolean = false // eslint-disable-next-line
  private large: boolean = false // eslint-disable-next-line
  private xlarge: boolean = false // eslint-disable-next-line
  private tile: boolean = false // eslint-disable-next-line
  private rounded: boolean = false // eslint-disable-next-line
  private circle: boolean = false // eslint-disable-next-line
  private disabled: boolean = false 

  private resize(name: string) {
    switch (name) {
      case 'xsmall':
        this.xsmall = true
        this.small = false
        this.large = false
        this.xlarge = false
        break
      case 'small':
        this.xsmall = false
        this.small = true
        this.large = false
        this.xlarge = false
        break
      case 'normal':
        this.xsmall = false
        this.small = false
        this.large = false
        this.xlarge = false
        break
      case 'large':
        this.xsmall = false
        this.small = false
        this.large = true
        this.xlarge = false
        break
      case 'xlarge':
        this.xsmall = false
        this.small = false
        this.large = false
        this.xlarge = true
        break
    }
  }

  private changeRadius(name: string) {
    switch (name) {
      case 'tile':
        this.tile = true
        this.rounded = false
        this.circle = false
        break
      case 'normal':
        this.tile = false
        this.rounded = false
        this.circle = false
        break
      case 'rounded':
        this.tile = false
        this.rounded = true
        this.circle = false
        break
      case 'circle':
        this.tile = false
        this.rounded = false
        this.circle = true
        break
    }
  }

  private onClick(event: MouseEvent) {
    // 因为是内部处理这个按钮的点击事件 所以可以使用 private让方法变成私有
    console.log(event)
  }

  private changeDisabled() {
    this.disabled = !this.disabled
  }
}
</script>

<style lang="stylus" scoped>
.btn-container {
    width: 160px;
    height: 160px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.btn-group
    margin-top 40px
</style>
