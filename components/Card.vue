<template>
    <div class="flex-col shadow-md w-72 ">
        <div class="p-8   content ">
            <img  class=" mx-auto " src="../static/img/seo.svg"    width="60"
            height="60" />
            <h3 class="text-[#3f3f3f] text-opacity-90 text-center space-y-2 font-sans font-bold leading-10 text-lg ">{{titlecard}}</h3> 
            <p class=" text-base text-center leading-6  font-medium font-sans text-[#535559] text-opacity-40 ">{{descard}}</p>
        </div>
    </div>
</template>

<script>

export default {
    name:"Card",
        props: {
    icon: String,
    titlecard:String,
    descard:String
  },
}
</script>