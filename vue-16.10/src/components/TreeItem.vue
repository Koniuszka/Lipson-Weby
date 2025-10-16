<script setup>
    import { ref, computed } from 'vue';

    const props = defineProps({
        model: Object
    });

    const isOpen = ref(false);
    const isFolder = computed(() => {
        return props.model.children && props.model.children.length;
    })

    function toggle() {
        isOpen.value = !isOpen.value;
    }

    function changeType() {
        if (!isFolder.value)
        {
            props.model.children = [];
            addChildren();
            isOpen.value = true;
        }
    }

    function addChildren() {
        props.model.children.push({name: "CONFUSED LEAF"});
    }

</script>

<template>
    <li>
        <div
            :class="{ bold : isFolder}"
            @click="toggle"
            @dblclick="changeType"
        >
        {{ model.name }}
        <span v-if="isFolder"> [{{ isOpen ? '-' : '+' }}]</span>
        </div>
        <ul v-show="isOpen" v-if="isFolder">
            <TreeItem
                class="item"
                v-for="model in model.children"
                :model="model" />
        </ul>
        <!-- <li class="add" @click="addChildren">+</li> -->
    </li>
</template>
