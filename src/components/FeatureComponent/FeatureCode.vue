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
}

code {
  margin: 0px;
}
</style>