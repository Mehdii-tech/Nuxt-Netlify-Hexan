
<template>
    <div class=" pt-5 flex justify-center ">
        <div class="pb-7">
            <span class="inline-flex space-x-1 text-base text-center font-medium font-sans ">{{ footertitle }}<p class="text-[#535559] text-opacity-25 "></p><p class="text-[#fb4275]">Hexan</p></span>
    </div>
    </div>
</template>

<script>

export default ({
    name:"Footer",
      props: {
    footertitle:String,
  },
})
</script>