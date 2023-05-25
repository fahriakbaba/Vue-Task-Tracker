<template>
    <section class="footer">
        <p>Copyright <span>&copy;</span> {{ currDate }} </p>
    </section>
</template>

<script>
export default {
    name: "Footer", 
    data() {
        return {
            currDate: new Date().getFullYear(), 
        }
    }
}
</script>

<style scoped>
.footer {
    text-align: center;
    margin-top: .75rem;
    font-size: .7rem;
    font-weight: 600;
    letter-spacing: .75px;
}
</style>