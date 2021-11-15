<template>
    <div class="container">
        <h3>Dynamic Components</h3>
        <button @click="activeTab = 'TabA'">Tab A</button>
        <button @click="activeTab = 'TabB'">Tab A</button>
        <button @click="activeTab = 'TabC'">Tab A</button>

        <!-- Both works  -->
        <!-- <TabA v-if="activeTab === 'TabA'"/>
        <TabB v-if="activeTab === 'TabB'"/>
        <TabC v-if="activeTab === 'TabC'"/> -->
        <!-- Both works  -->
        <component :is="activeTab" />
    </div>
</template>




<script>

    import TabA from "./TabA.vue"
    import TabB from "./TabB.vue"
    import TabC from "./TabC.vue"

    export default {
        name: "TabContainer",
        components: {
            TabA,
            TabB,
            TabC
        },
        data(){
            return{
                activeTab: 'TabA'
            }
        }
    }
</script>

<style scoped>

</style>