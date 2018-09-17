<template>
    <div class="text-content-container">
        <div class="text-content-header">
            <h2> {{title | capitalize}} </h2>
        </div>
        <div class="text-content-subheader">
            {{subtitle}}
        </div>
        <div class="text-content-paragraph">
            <slot> </slot>
        </div>
    </div>
</template>
<script>
export default {
  name: "TextContent",
  props: {
    title: String,
    subtitle: String,
  },
  filters: {
    capitalize: function(value) {
      if (!value) return "";
      value = value.toString();
      return value.toUpperCase();
    }
  }
};
</script>
<style>

h1,h2,h3,h4 {
    margin: 0;
}

.text-content-container {
    display: flex;
    flex-flow: column nowrap;
    justify-content: flex-start;
}

.text-content-header {
    color: rgb(17, 31, 17);
    font-weight: bolder;
    margin: 0.4rem 0rem;
    border-bottom: solid rgba(153, 153, 153, 0.5) 1px;
}

.text-content-subheader {
    color: rgb(153, 153, 153);
    font-weight: 500;
    margin: 0.5rem 0rem;
}

.text-content-paragraph {
    text-align: justify;
}
</style>
