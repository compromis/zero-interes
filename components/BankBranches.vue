<template>
  <article class="bank-branches" id="Branches">
    <div class="bank-branches-heading">
      <h3 id="BankBranchesHeading">
        {{ title}}
      </h3>
      <div class="bank-branches-number" aria-describedby="BankBranchesHeading">
        <span v-if="comparison === 'before'">
          {{ beforeBranches }}
        </span>
        <span v-else>
          <AnimatedNumber id="BBA" :from-number="beforeBranches" :to-number="afterBranches" />
        </span>
      </div>
    </div>
    <div class="bank-branches-dots">
      <span
        v-for="dot in maxBranches"
        :key="dot"
        :class="['dot', comparison === 'after' && dot > minBranches && 'closed']"
        :style="{ '--delay': `${((maxBranches / dot) + 0.25) - 1.25}s` }" />
    </div>
  </article>
</template>

<script setup>
import { computed, ref, onMounted } from 'vue'
import gsap from 'gsap' 
import scrollTrigger from 'gsap/ScrollTrigger'

const props = defineProps({
  before: {
    type: Array,
    required: true
  },
  after: {
    type: Array,
    required: true
  }
})

const comparison = ref('before')

const title = computed(() => {
  const [beforeTitle] = props.before
  const [afterTitle] = props.after

  return comparison.value === 'before' ? beforeTitle : afterTitle
})

const beforeBranches = computed(() => props.before[1])
const afterBranches = computed(() => props.after[1])
const maxBranches = computed(() => parseInt(beforeBranches.value / 10))
const minBranches = computed(() => parseInt(afterBranches.value / 10))
const animationNumber = ref(null)

onMounted(() => {
  gsap.registerPlugin(scrollTrigger)
  scrollTrigger.create({
    trigger: `#Branches`,
    start: 'top center',
    scrub: true,
    onToggle () {
      comparison.value = comparison.value === 'before' ? 'after' : 'before'
    }
  })
})

const numberFormat = (number) => {
  return parseInt(number).toLocaleString('de-DE')
}
</script>

<style lang="scss" scoped>
.bank-branches {
  &-heading {
    display: flex;
    margin-bottom: 1rem;
    font-size: 2rem;
    align-items: baseline;
    font-weight: bold;

    h3 {
      font-size: inherit;
    }
  }

  &-number {
    margin-left: auto;
    padding-left: 1rem;
  }

  &-dots {
    display: flex;
    flex-wrap: wrap;
    gap: .5em;

    .dot {
      display: block;
      height: .95em;
      width: .95em;
      background: var(--orange);
      border-radius: 100%;
      transition: 0s ease;
      transition-delay: var(--delay);

      &.closed {
        opacity: .25;
      }
    }
  }
}
</style>