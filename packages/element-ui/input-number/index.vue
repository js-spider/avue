<template>
  <el-input-number v-model="text"
                   class="avue-input-number"
                   @click.native="handleClick"
                   @focus="handleFocus"
                   @blur="handleBlur"
                   :precision="precision"
                   :size="size"
                   :min="minRows"
                   :max="maxRows"
                   :clearable="disabled?false:clearable"
                   :readonly="readonly"
                   :controls-position="controlsPosition"
                   :label="placeholder"
                   :disabled="disabled"></el-input-number>
</template>

<script>
import create from "core/create";
import props from "../../core/common/props.js";
import event from "../../core/common/event.js";
export default create({
  name: "input-number",
  mixins: [props(), event()],
  data () {
    return {};
  },
  props: {
    step: {
      type: Number,
      default: 1
    },
    controlsPosition: {
      type: String,
      default: "right"
    },
    precision: {
      type: Number,
      default: 0
    },
    minRows: {
      type: Number,
      default: -Infinity
    },
    maxRows: {
      type: Number,
      default: Infinity
    }
  },
  watch: {
    text: {
      handler () {
        this.handleChange(this.text);
      },
      immediate: true
    }
  },
  created () { },
  mounted () { },
  methods: {}
});
</script>