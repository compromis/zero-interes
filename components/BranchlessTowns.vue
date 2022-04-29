<template>
  <ul class="branchless-towns list-reset" id="BranchlessTowns">
    <li v-for="([name, closed, open], i) in data" :key="name" class="branchless-town">
      <span class="branchless-town-name">{{ name }}</span>
      <div class="branchless-town-bar">
        <span :class="['closed', { animated }]" :id="`PB${i}`" :style="{ '--width': percentage(closed, open), '--delay': `${i * 0.25}s` }">
          <span class="d-block p-1"><AnimatedNumber :id="`CN${i}`" :to-number="closed" /></span>
        </span>
        <span class="open">
          <span class="d-block p-1">de {{ closed + open }}</span>
        </span>
      </div>
    </li>
  </ul>
</template>

<script setup>
import { onMounted, ref } from 'vue'
import gsap from 'gsap' 
import scrollTrigger from 'gsap/ScrollTrigger'

const props = defineProps({
  data: {
    type: Array,
    required: true
  }
})

const percentage = (closed, open) => {
  const total = closed + open
  const percentage = closed / total * 100

  return `${percentage}%`
}

const animated = ref(false)

onMounted(() => {
  gsap.registerPlugin(scrollTrigger)
  scrollTrigger.create({
    trigger: `#BranchlessTowns`,
    start: 'top 70%',
    onToggle () {
      animated.value = true
    }
  })
})
</script>

<style lang="scss" scoped>
.branchless-town {
  margin-top: 1.5rem;

  &:not(:last-child) {
    margin-bottom: 1rem;
  }

  &-name {
    display: block;
    margin-bottom: .5rem;
  }

  &-bar {
    display: flex;
    border: 1px solid var(--black);

    .closed {
      background: var(--black);
      color: var(--white);
      width: 0;
      overflow: hidden;

      &.animated {
        animation: fillBar 1s forwards;
        animation-delay: var(--delay);
      }
    }

    .open {
      margin-left: auto;
    }
  }
}

@keyframes fillBar {
  0% {
    width: 0;
  }
  100% {
    width: var(--width);
  }
}
</style>