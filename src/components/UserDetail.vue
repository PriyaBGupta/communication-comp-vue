<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <p>User Name: {{myName}}</p>
        <p>Lets reverse the name {{switchName()}}</p>
        <p>User Age :{{userAge}}</p>
        <button @click="resetName">Reset Name</button>
        <button @click="resetFn()">Reset Name from callback</button>
    </div>
</template>

<script>
export default{
    props:{
        myName:{
            type:String
        },
        resetFn:Function,
        userAge:Number
    },
    methods:{
        switchName(){
            return this.myName.split("").reverse().join("");
        },
        resetName(){
            this.myName='Max';
            this.$emit('nameWasReset',this.myName)
        }

    }   
}
//props name sjould be equal in all three places should be equal 
//we use props as if it data property
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
