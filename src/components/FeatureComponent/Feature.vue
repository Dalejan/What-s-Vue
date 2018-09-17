<template>
<div>
    <div class="feature-title">{{name}}</div>
    <div class="feature-container">
    <FeatureDescription :name= "name" class="feature-subcontent">
        <slot name="description"></slot>
    </FeatureDescription>
    <FeatureCode class="feature-subcontent">
        <slot name="code"></slot>
    </FeatureCode>
    <FeatureExample class="feature-subcontent">
        <slot name="example"></slot>
    </FeatureExample>
</div> 
</div>
</template>

<script>
import FeatureCode from "./FeatureCode.vue";
import FeatureDescription from "./FeatureDescription.vue";
import FeatureExample from "./FeatureExample.vue";

export default {
  name: "Feature",
  components: {
    FeatureCode,
    FeatureDescription,
    FeatureExample
  },
  props: {
    name
  }
};
</script>

<style scoped>
.feature-container {
  display: flex;
  flex-flow: nowrap row;
}
.feature-subcontent {
  padding: 20px;
  text-justify: auto;
}
.feature-title{
      font-size: 1.2em;
    height: 1.3em;
}
</style>