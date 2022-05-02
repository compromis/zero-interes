<template>
  <svg version="1.1" x="0px" y="0px" viewBox="0 0 1400 933" preserveAspectRatio="xMidYMid slice" class="text">
    <image style="overflow:visible;" width="1400" height="933" xlink:href="../assets/images/base.jpg"></image>
    <g class="big-zero">
      <rect x="658.41" y="235.25" class="st0" width="360.21" height="408.01"/>
      <text transform="matrix(1 0 0 1 658.4061 559.3109)" class="st1 st2 st3 st4">{{ number }}</text>
      <g>
        <rect x="897.73" y="458.88" transform="matrix(0.9959 -0.0904 0.0904 0.9959 -41.8513 89.1443)" class="st0" width="130.36" height="95.18"/>
        <text transform="matrix(0.9959 -0.0904 0.0904 0.9959 902.1575 558.1541)" class="st1 st2 st5 st6">%</text>
      </g>
    </g>
    <image style="overflow:visible;" width="1400" height="933" xlink:href="../assets/images/transparent.png"></image>
    <g>
      <rect x="595.44" y="544.12" class="st7" :width="wider ? 460.33 : 418.33" height="215.78"/>
      <g>
        <rect x="579.39" y="558.82" class="st0" width="444.33" height="83.44"/>
        <text transform="matrix(1 0 0 1 616.6531 628.0162)" class="st1 st8 st9 st10">{{ interest }}</text>
      </g>
      <rect x="620.83" y="646.71" class="st0" width="490.32" height="131.92"/>
      <text transform="matrix(1 0 0 1 620.8328 662.5001)">
        <Transition>
          <tspan x="0" y="0" class="st1 st11 st12" v-if="sentence > 0">{{ sentences[0] }}</tspan>
        </Transition>
        <Transition>
          <tspan x="0" y="27.08" class="st1 st11 st12" v-if="sentence > 1">{{ sentences[1] }}</tspan>
        </Transition>
        <Transition>
          <tspan x="0" y="54.15" class="st1 st11 st12" v-if="sentence > 2">{{ sentences[2] }}</tspan>
        </Transition>
        <Transition>
          <tspan x="0" y="81.23" class="st1 st11 st12" v-if="sentence > 3">{{ sentences[3] }}</tspan>
        </Transition>
      </text>
    </g>
    <a xlink:href="#bailout" class="button">
      <rect x="595.39" y="769.82" :width="wider ? 142.33 : 134.33" height="46.44" class="cta"></rect>
      <text transform="matrix(1 0 0 1 619.8328 798.5001)" class="cta-text">{{ cta }}</text>
    </a>
  </svg>
</template>

<script setup>
import { ref, onMounted } from 'vue'

defineProps({
  interest: {
    type: String,
    default: 'd’interés'
  },
  cta: {
    type: String,
    default: 'M’interesa'
  },
  sentences: {
    type: Array,
    default: () => [
      'a tornar els diners dels rescat',
      'a atendre’t presencialment',
      'a mantindre les oficines obertes',
      'a mantindre llocs de treball'
    ]
  },
  wider: {
    type: Boolean,
    default: false
  }
})

const number = ref(9)
const sentence = ref(0)

onMounted(() => {
  countdown()
  showSentences()
})

const countdown = () => {
  const interval = setInterval(() => {
    number.value--
    if (number.value === 0) {
      clearInterval(interval)
    }
  }, 100)
}

const showSentences = () => {
  const interval = setInterval(() => {
    sentence.value++
    if (sentence.value === 4) {
      clearInterval(interval)
    }
  }, 1000)
}

</script>

<style lang="scss" scoped>
.st0{fill:none;}
.st1{fill:var(--blue);}
.st2{font-family:var(--font-bank); font-weight: bold; font-style: italic;}
.st3{font-size:462.9492px;}
.st4{letter-spacing:-23;}
.st5{font-size:133.6767px;}
.st6{letter-spacing:-6;}
.st7{fill:var(--white);}
.st8{font-family:var(--font-bank); font-weight: 900; font-style: italic;}
.st9{font-size:98.8521px;}
.st10{letter-spacing:-0.04em;}
.st11{font-family:var(--font-bank);}
.st12{font-size:22.5641px;}

.v-enter-active,
.v-leave-active {
  transition: 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
  transform: translateX(-10%);
}

.big-zero {
  animation: big-zero 2s ease infinite;
  animation-delay: 1.25s;
  transform-origin: center;
}

.cta {
  fill: var(--yellow);
  cursor: pointer;

  &:hover {
    fill: darken(#f5c53e, 10%);
  }
}

.cta-text {
  font-size: 18px;
  pointer-events: none;
  fill: var(--black);
}

@keyframes big-zero {
  0% {
    transform: scale(1);
  }

  50% {
    transform: scale(0.95);
    opacity: .8;
  }

  100% {
    transform: scale(1);
  }
}
</style>
