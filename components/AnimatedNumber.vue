<template>
  <span class="animated-number me-1" :id="id">
    <number
      animation-paused
      ref="animatedNumber"
      :from="fromNumber"
      :to="toNumber"
      :format="numberFormat"
      :duration="1.25"
      easing="Power1.easeOut"/>
  </span>
</template>

<script setup>
import { onMounted, ref } from 'vue'
import gsap from 'gsap' 
import scrollTrigger from 'gsap/ScrollTrigger'

const props = defineProps({
  id: {
    type: String,
    required: true
  },
  toNumber: {
    type: Number,
    required: true
  },
  fromNumber: {
    type: Number,
    default: 0
  },
  currency: {
    type: Boolean,
    default: false
  }
})

const animatedNumber = ref(null)

const numberFormat = (number) => {
  const currency = props.currency ? { style: 'currency', currency: 'EUR' } : null
  return new Intl.NumberFormat('es-ES', { maximumSignificantDigits: 3, ...currency }).format(parseInt(number))
}

onMounted(() => {
  gsap.registerPlugin(scrollTrigger)
  scrollTrigger.create({
    trigger: `#${props.id}`,
    start: 'top bottom',
    onToggle () {
      setTimeout(() => {
        animatedNumber.value.play()
      }, 250)
    }
  })
})
</script>

<style lang="scss" scoped>
.animated-number {
  font-variant-numeric: tabular-nums;
}
</style>