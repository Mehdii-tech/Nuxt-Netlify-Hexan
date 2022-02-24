<template>
<button class="bg-pink-500 font-semibold text-white hover:bg-pink-400 h-8 w-32 rounded-full">{{button}}</button>
    
</template>

<script>
export default {
    name:'Button',
    props:{
        button:String
    }
}
</script>