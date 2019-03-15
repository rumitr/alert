<template>
    <div :class="alertClasses" v-show="show">
        <slot></slot>
        <span class="close" @click="show = false">x</span>
    </div>
</template>

<script>
export default {
    props: ['list'],
    events: {
        'add-alert':function(data) {
            this.list.push(data);
        }
    }
}
</script>

