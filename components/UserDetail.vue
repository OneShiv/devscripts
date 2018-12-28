<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <p> My name is {{switchName() }}</p>
        <p> User Age {{ usrAge }}</p>
        <button @click="resetName" >Reset</button>
        <button @click="resetFn" >Reset Durs</button>
    </div>
</template>

<script>
  import { eventBus } from '../main';

export default{
    props:{
        name:String,
        resetFn:Function,
        usrAge:Number
    },
    methods:{
        switchName(){
            return this.name.split("").reverse().join("");
        },
        resetName(){
            this.name='hhhhhhhhhhhhhhhhh';
            this.$emit('nameReset',this.name);
        }
    },
    created(){
            eventBus.$on('ageWasEdited',(age) => {
                this.usrAge=age;
            })
        }
}
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
