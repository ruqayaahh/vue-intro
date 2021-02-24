<template>
    <div>
        <h1>Testimonials Page</h1>
        <HelloWorld @updateMessage="handleMessageUpdate" :msg="message"/>
    </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
export default {
    name: 'Testimonials',
    components: {
        HelloWorld,
    },
    data() {
        return {
            message: "Welcome to your testimonials page"
        }
    },
    methods: {
        handleMessageUpdate(payload) {
            this.message = payload.msg;
        }
    }
};
</script>
