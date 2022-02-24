<script>
import Footer from "../components/Footer.vue";
import Logo from "../components/Logo.vue"
import Subtitle from "../components/Subtitle.vue"
import Card from "../components/Card.vue"
import Contact from "../components/Contact.vue"
import List from "../components/List.vue"
export default {
  components: {
    Footer,
    Logo,
    Subtitle,
    Card,
    Contact
  },
    head() {
    return {
      script: [{ src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' }],
    };
  },
            async asyncData({ $content, params, error }) {
    let home=[];
    try {
      home = await $content("home", params.slug).fetch();
      
    } catch (e) {
      error({ message: "home not found" });
    }
    console.log(home,'test')
    return {
      home,
    };
    },
  props: {
    // title: {
    //   type: String,
    //   required: true,
    //   default: () => [],
    // },
    // description: {
    //   type: String,
    //   required: true,
    //   default: () => [],
    // },
  },
  render() {
    return (
        <div>

            {this.home.map((home) => (
<div class="flex-col ">
    <div class="border-b shadow-sm border-[#535559] border-opacity-10 ">
      <div class="mx-auto max-w-6xl">
        <Logo />
      </div>  
    </div>
    <main  class="space-y-16 pt-24 ">
    <div class=" grid grid-rows-3 grid-flow-col mx-auto max-w-6xl space-y-16 ">
        <div class=" col-span-2 space-y-8 ">
        <Subtitle title={home.maintitle}/>
        <Description description={home.maindescription}/>
        
        </div>
        <div class=" row-span-3 ml-auto  ">
        <Image />
        </div>
    </div>

    <div class="mx-auto space-y-16 max-w-6xl">
      <div class="space-y-8 ">
        <Subtitle title={home.firsttitle} />
        <Description description={home.firstdescription} />
        
        <div class=" inline-flex space-x-6 p-3">
          <Card icon={home.iconone} titlecard={home.titlecardone} descard={home.descriptioncardone} />
          <Card icon={home.icontwo} titlecard={home.titlecardtwo} descard={home.descriptioncardtwo} />
          <Card icon={home.iconthree} titlecard={home.titlecardthree} descard={home.descriptioncardthree} />
          <Card icon={home.iconfour} titlecard={home.titlecardfour} descard={home.descriptioncardfour} />
        </div>
      </div>
    </div> 
      <div class=" grid grid-rows-3 grid-flow-col  space-y-16 ">
        <div class=" col-span-2 space-y-8 ml-auto max-w-8xl    ">
        <Subtitle title={home.secondtitle} />
        <Description description={home.seconddescription} />
        <List text={home.list} />
        <List text={home.list} />
        <List text={home.list} />
        </div>
        <div class=" row-span-3 pl-28 rounded-l-full bg-[#fb4275] bg-opacity-5  max-w-full ">
          <img  class=" p-12   " src="../static/img/marketing-img.svg"     width="600"
              height="600" />
        </div>
      </div>
      <div class="mx-auto space-y-16 max-w-6xl">
        <Subtitle title={home.threetitle} />
        <Description description={home.threedescription} />
        <Contact />
      </div>
      
    </main>
    <div  class="mx-auto space-y-16 max-w-6xl">  
      <div class="border-b  drop-shadow-sm border-[#535559] border-opacity-10 ">
        <Logo />
        
      </div>
      <Footer footertitle={home.footertitle}  />
    </div>
</div>
            ))}
            
  </div>
    );
  },
};
</script>
