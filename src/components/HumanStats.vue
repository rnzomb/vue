<template>

    <div>
          
     <form @submit.prevent="onSubmit">
         
            <label for="name"> name </label>  
            <template v-if="male">Mr.</template> 
            <template v-else>Ms.</template>       
            <input id="name" v-model.trim="name" type="text">
            <br>

            <label for="male"> male </label>
            <input id="male" v-model="male" type="checkbox"> 
            <br>

            <label for="age"> age </label>
            <input id="age" v-model.number="age" type="text"> 
            <br> 
            <button type="submit">Add</button>
     </form>
    </div>
</template>

<script>
export default {

    data() {
        return{
           name: undefined,
           male: true,
           age: undefined,
           people: []

        }
    },
    methods: {
        onSubmit(){

           console.log('submit') 

        }
    }
    
}

</script>
>