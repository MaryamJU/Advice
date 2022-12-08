<template>
    <div class="result-box">
        <p class="result-title">Here is your advice</p>
        <p class="result-text" :style="{color : color}">{{advice}} </p>
    </div>
</template>

<script>
export default{
    name:'FormResult',
    props:['advice', 'color']
}
</script>
<style scoped>
.result-box{
    margin: 2rem 0;
    padding: 2rem;
    border-radius: 10px;
    background: linear-gradient(80deg, #e5e5e5, lightblue);
}
.result-title{
    padding: 1rem;
    font-size: 1.5rem;
    font-weight: bold;
    color:  rgb(47, 209, 242);
    border-radius: 10px;
    background: linear-gradient(80deg,rgb(99, 99, 99), rgb(2, 2, 98));
}
.result-text{
    font-size: 2rem;
    line-height: 3rem;
}
</style>