<template>
  <div>
    <hello-options v-model="optionsSuffix" />
    <p v-if="optionsSuffix">
      <output>{{ optionsOutput }}</output>
    </p>
    <hr />
    <hello-setup v-model="setupSuffix" />
    <p v-if="setupSuffix">
      <output>{{ setupOutput }}</output>
    </p>
    VUE 2
    <MyComponent />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "@vue/composition-api";
import { HelloOptions, HelloSetup } from "library/vue2";
import MyComponent from "@sigma-interactive/unbuild-lib/MyComponent"

export default defineComponent({
  components: {
    HelloOptions,
    HelloSetup,
    MyComponent,
  },
  data() {
    return {
      optionsSuffix: "",
      setupSuffix: "",
    };
  },
  computed: {
    optionsOutput(): string {
      return `Hello ${this.optionsSuffix}`;
    },
    setupOutput(): string {
      return `Hello ${this.setupSuffix}`;
    },
  },
});
</script>
<style>
.el-input--small {
  font-size: 14px;
}

.el-button--small {
  font-size: 14px;
}
</style>
