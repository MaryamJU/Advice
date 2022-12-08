<template>
    <form class="form">
        <fieldset class="form-fieldset">
            <legend class="form-legend">Choose a number</legend>
            <label class="form-label">Luck Number</label>
            <input type="number" class="form-input" v-model="userNumber">
        </fieldset>
        <fieldset class="form-fieldset">
            <legend class="form-legend">Text Color</legend>
            <label class="form-label">Color</label>
            <input type="color" class="form-input" v-model="userColor">
        </fieldset>
        <FormResult :color="userColor" :advice="getAdvice"/>
    </form>
</template>

<script>
import FormResult from './FormResult.vue';
export default{
    name:'PageForm',
    components:{
        FormResult,
    },
    inject:['newarr', 'message'],
    data() {
        return {
            userNumber:5,
            userColor:"000000",
            quotes:["quote 1", "quote 2", "quote 3", "quote 4"],
        }
    },
    computed:{
        getAdvice(){
            const advice = this.newarr.find((q, i) => i === this.userNumber)
            if(!advice) return 'unlucky enough, no advice for you'
            return advice.quoteText;
        }
    }
}
</script>

<style scoped>
.form{
    margin: 5rem auto;
    max-width: 70%;
}
.form-fieldset{
    margin: 2rem 0;
    padding: 2rem;
    border-radius: 10px;
    background: linear-gradient(80deg, #e5e5e5, lightblue);
}
.form-legend{
    display: block;
    text-align: left;
    padding: 1rem;
    font-size: 1.5rem;
    font-weight: bold;
    color:  rgb(47, 209, 242);
    border-radius: 10px;
    background: linear-gradient(80deg,rgb(99, 99, 99), rgb(2, 2, 98));
}
.form-label{
    display: block;
    padding: 1rem;
    font-size: 2rem;
    font-weight: bold;
}
.form-input{
    outline: none;
    border: none;
    font-size: 2rem;
    color: tomato;
    text-align: center;
    max-width: 30%;
}
</style>