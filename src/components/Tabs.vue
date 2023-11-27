<script setup>
    const props = defineProps({
        names: {
            type: Array,
            required: true
        },
        selectedTab: {
            type: String,
            required: false
        }
    })

    const emit = defineEmits(['changeTab'])

    const clickOnTab = (tabName) => {
        emit('changeTab', tabName)
    }
</script>

<template>
    <div class="component-body">
        <div class="main-title">Концерты</div>
        <div class="tab-nav">
            <span v-for="tab in names"
            :key="tab.name"
            :class="['tab-nav-item', {'selected': tab.name === selectedTab}]"
            @click="clickOnTab(tab.name)">
                {{ tab.name }}
            </span>
        </div>
        <div class="tab-content">
            <slot/>
        </div>
    </div>
    
</template>

<style>
    .main-title {
        color: #ffffff;
        font-size: 80px;
        text-transform: uppercase;
        padding-left: 50px;
        padding-top: 40px;
        padding-bottom: 50px;
        margin: 0;
    }
    .component-body {
        width: 1366px;
        background-color: #000000;
    }
    .tab-nav {
        display: flex;
        background-color: #000000;
    }
    .tab-nav-item {
        padding-left: 100px;
        padding-right: 100px;
        padding-bottom: 40px;
        font-size: 32px;
        color: #ffffff;
        text-transform: uppercase;
    }

    .selected{
        color: #F7F4A4;
    }

    .tab-content {
        color: #ffffff;
        text-transform: uppercase;
    }
</style>