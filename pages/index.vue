<template>
<div class="flex-col ">
    <div class="border-b shadow-sm border-[#535559] border-opacity-10 ">
      <div class="mx-auto max-w-6xl">
        <Logo />
      </div>  
    </div>
    <main class="space-y-16">
    <div class=" grid grid-rows-3 grid-flow-col mx-auto max-w-6xl space-y-16 ">
        <div class=" col-span-2 space-y-8 ">
        <Subtitle :document="home"/>
        <!-- <Description /> -->
        </div>
        <!-- <div class=" row-span-3   ">
        <nuxt-img preload src="../static/img/banner.png"     width="165"
            height="50" />
        </div> -->
    </div>

    <div class="mx-auto space-y-16 max-w-6xl">
      <div class="space-y-8 ">
        <Subtitle />
        <Description />
        
        <div class=" inline-flex space-x-6 p-3">
          <Card />
          <Card />
          <Card />
          <Card />
        </div>
      </div>
    </div> 
      <div class=" grid grid-rows-3 grid-flow-col  space-y-16 ">
        <div class=" col-span-2 space-y-8 mx-auto max-w-8xl    ">
        <Subtitle />
        <!-- <Description /> -->
        </div>
        <div class=" row-span-3 pl-28 rounded-l-full bg-[#fb4275] bg-opacity-5  max-w-full ">
          <img  class=" p-12   " src="../static/img/marketing-img.svg"     width="600"
              height="600" />
        </div>
      </div>
      
    </main>
    <div  class="mx-auto space-y-16 max-w-6xl">  
      <div class="border-b  drop-shadow-sm border-[#535559] border-opacity-10 ">
        <Logo />
        
      </div>
      <Footer v-for="item in home" v-bind:key="item.footertitle" />
    </div>
</div>
</template>

<script lang="ts">


export default {
  head() {
    return {
      script: [{ src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' }],
    };
  },
    async asyncData({ $content, params, error }:any) {
    let home:any;
    try {
      home = await $content("home", params.slug).fetch();
      // OR const article = await $content(`articles/${params.slug}`).fetch()
    } catch (e) {
      error({ message: "home not found" });
    }
    console.log(home,'test')
    return {
      home,
    };
  },
};
</script>
