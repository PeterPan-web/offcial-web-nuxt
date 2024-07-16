<script setup lang="ts">
import MarqueeCpn from '~~/components/Marquee.vue'
import type Marquee from '~~/components/Marquee.vue'
import { COMPANY } from '~~/enums/appEnum'

type MarqueeInstance = InstanceType<typeof Marquee>

const descriptRef = ref<MarqueeInstance | null>(null)
const { $on, MITT_KEY } = useMitt()
const descript = ref<string>('是一家集研发生产销售为一体的APP，主营美妆护肤，由平台接单生产部生产，APP购买，售后部发货，快递配送让用户足不出户，在家即可完成购物需求;是一家集研发生产销售为一体的APP，主营美妆护肤，由平台接单生产部生产，APP购买，售后部发货，快递配送让用户足不出户，在家即可完成购物需求;')
$on(MITT_KEY.CHANGE_TO_ABOUT, () => {
  descriptRef.value?.append()
})
</script>

<template>
  <div ref="rootRef" class="about full  text-white text-xl font-500 grid grid-cols-12 items-center">
    <MarqueeCpn
      ref="descriptRef" class="card-content text-lg leading-8!  col-span-10 col-start-2 md:(col-span-6 col-start-2 text-xl leading-10!)" :time="0.1"
      :text="`&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp${COMPANY}${descript}`"
    />
  </div>
</template>

<style scoped lang='scss'>
.about {
  // background-image: url("/about.jpg");
  background-image: url("/about.jpg");
  .Marquee{
  }
}
</style>
