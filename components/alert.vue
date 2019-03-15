<template>
    <div :class="alertClasses" v-show="show">
        <slot></slot>
        <span class="close" @click="show = false">x</span>
    </div>
</template>
<script>
export default {
    props: ['type'],
    data: function() {
        return{
            show: true
        }
    },
    computed: {
        alertClasses: function() {
            var type = this.type;
            return {
                'alert': true,
                'alert--success': type == 'success',
                'alert--error': type == 'error' 
            }
        }
    },
    ready: function() {
        console.log(this);
    }
}
</script>

