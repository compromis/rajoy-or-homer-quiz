<template>
  <label :class="{
    'option': true,
    'option-rajoy': option.type == 'rajoy',
    'option-homer': option.type == 'homer',
    'disabled': disabled,
    'selected': selected,
    'option-is-correct': option.points > 0 && selected,
    'option-is-incorrect': option.points == 0 && selected
    }">
    <input
      type="radio"
      :value="option"
      :name="'q' + questionId"
      :checked="selected"
      :disabled="disabled"
      @change="$emit('change', option)" />

      <Cigar v-if="option.type == 'rajoy'" />
      <Doughnut v-if="option.type == 'homer'" />

      {{ option.name }}
  </label>
</template>

<script>
import True from '../assets/images/true.svg'
import False from '../assets/images/false.svg'
import Doughnut from '../assets/images/doughnut.svg'
import Cigar from '../assets/images/cigar.svg'

export default {
  name: 'quiz-option',

  props: {
    option: Object,
    disabled: Boolean,
    selected: Boolean,
    questionId: Number
  },

  components: {
    True,
    False,
    Doughnut,
    Cigar
  }
}
</script>

<style lang="scss" scoped>
@import '../variables';

input {
  display: none;
}

.option {
  display: block;
  cursor: pointer;
  padding: 0.75rem;
  padding-left: 60px;
  border-radius: 8px;
  font-size: 1.25rem;
  color: $white;
  position: relative;
  transition: 0.2s ease-in-out;

  svg {
    position: absolute;
    top: 50%;
    left: 1rem;
    width: 30px;
    height: 30px;
    margin-top: -15px;
  }

  &:hover {
    transform: translateY(-3px);
    box-shadow: 0 4px 15px -2px rgba(17, 36, 85, 0.25);
  }

  &:active {
    transform: translateY(3px);
  }

  &.disabled:hover {
    transform: scale(1);
    box-shadow: none;
  }
}

.option-rajoy {
  background: $rajoy-gradient;
}

.option-homer {
  background: $homer-gradient;
}

.disabled {
  opacity: 0.5;
}

.option-is-correct.selected,
.option-is-correct.selected:hover {
  box-shadow: 0 0 0 5px green;
}
.option-is-incorrect.selected,
.option-is-incorrect.selected:hover {
  box-shadow: 0 0 0 5px red;
}

@media (min-width: 769px) {
  .option {
    padding: 1rem;
    font-size: 1.5rem;
    padding-left: 60px;
  }
}
</style>
