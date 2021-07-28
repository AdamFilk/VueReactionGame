<template>
    <p>Result is {{score}}ms</p>
    <div v-if="score<200">
        <p>Perfect! Your mother is proud of you</p>
    </div>
    <div v-else-if="score>200 && score < 500">
        <p>Not bad! Typical Gold Nova</p>
    </div>
    <div v-else-if="score>500 && score < 700">
        <p>It's cool almost potato but it's fine</p>
    </div>
    <div v-else>
        <p>Ayy Yoo! IT'S BADDDD!!!! You gotta check your cognitive abilities homie!</p>
    </div>
</template>

<script>
export default {
    props:['score']
}
</script>

<style>

</style>