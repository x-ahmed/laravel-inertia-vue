<template>
    <layout>
        <div>this is the welcome page {{ foo }}.</div>
    </layout>
</template>

<script>
import Layout from "./Shared/Layout";

export default {
    components: {
        Layout
    },
    props: ["foo"]
};
</script>
