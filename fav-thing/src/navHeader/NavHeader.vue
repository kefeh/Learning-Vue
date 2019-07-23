<template>
    <nav class="header cat-header">
        <span class="cat-title">{{title}}</span>
    </nav>
</template>

<script>
export default {
    name: "NavHeader",
    props: ['title'],
}
</script>
