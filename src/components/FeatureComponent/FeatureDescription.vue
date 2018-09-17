<template>
    <div>

        <div>
            <slot></slot>
        </div>
    </div>
</template>

<script>
export default {
  name: "FeatureDescription",
  props: {
    name
  }
};
</script>

<style scoped>
.feature-title {
}
</style>