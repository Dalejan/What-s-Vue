<template>
    <div>
        <pre>
                    <code>
                        <slot>
                        </slot>
                    </code>
                    </pre>
    </div>
</template>

<script>
export default {
  name: "FeatureCode",
  props: {
    name
  }
};
</script>

<style scoped>
pre {
  color: white;
  background: black;
  margin: 0px;
  border-radius: 10px;
  overflow: auto;
  height: 40vh;
}

code {
  margin: 0px;
}
</style>