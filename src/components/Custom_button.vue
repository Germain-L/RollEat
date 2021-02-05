<template>
    <v-btn>{{ text }}</v-btn>
</template>


<script>
export default {
    name: 'CustomButton',
    props: {
        text: String,
    }
}
</script>