<template>
<div class="feature-container">
    {{name}}
    <FeatureDescription name= "s" class="feature-subcontent"/>
    <FeatureCode class="feature-subcontent"/>
    <FeatureExample class="feature-subcontent"/>
</div> 
</template>

<script>
import FeatureCode from "./FeatureCode.vue"
import FeatureDescription from "./FeatureDescription.vue"
import FeatureExample from "./FeatureExample.vue"

export default{
    name:"Feature",
    components:{
        FeatureCode,
        FeatureDescription,
        FeatureExample
    },

    props:{
        name
    }
}
</script>

<style scoped>
.feature-container{
    display:flex;
}
.feature-subcontent{
    padding: 20px;
    margin: 20px;
}
</style>