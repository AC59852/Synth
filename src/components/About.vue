<template>
  <section>
    <aside class="about__quote">{{ quote }}</aside>
    <div class="about__wrapper">
        <div class="about__imgBox" v-if="desktop">
            <img v-for="img in aboutImgs.slice(0,1)" :src="'/imgs/' + img.link" alt="Small Product Image" :key="img.id">
        </div>
        <div class="about__story">
            <h2 class="about__title">My Story</h2>
            <div class="about__paraWrapper">
                <p>{{ paraContent.para1 }}</p>
                <p v-if="desktop || storyExpanded">{{ paraContent.para2 }}</p>
                <p v-if="desktop || storyExpanded">{{ paraContent.para3 }}</p>
            </div>
            <button @click="setStory()" class="about__btn">{{ aboutBtn }}</button>
        </div>
        <div class="about__imgBox" v-if="desktop">
            <img v-for="img in aboutImgs.slice(2,3)" :src="'/imgs/' + img.link" alt="Small Product Image" :key="img.id">
        </div>
    </div>  
  </section>
</template>

<script>
export default {
    data() {
        return {
            mobile: true,
            desktop: false,

            storyExpanded: false,

            aboutBtn: 'Read More',

            quote: `I Couldn’t Find What I Needed, So I Made it Myself.`,

            paraContent: {
                para1: `Orci orci, sed tellus et, malesuada lacus cursus et. Suscipit quis sit felis accumsan pellentesque ullamcorper. Enim justo, elementum duis consectetur id enim non sodales. Dui, ac nulla a, ut fermentum nunc libero, faucibus cras. Nulla morbi ipsum, tincidunt commodo enim fusce feugiat sagittis imperdiet. Blandit dictum pharetra ac diam ornare id. Proin id augue nunc fermentum eget sem curabitur interdum gravida. Purus dictum diam, tellus luctus ultrices auctor feugiat in cursus. Non a, aenean eu sed quam phasellus ullamcorper. Velit amet integer metus vestibulum turpis dui lectus. Morbi quis velit felis mattis congue. Ligula ut et felis vitae adipiscing feugiat risus turpis malesuada. Augue phasellus enim sit vel odio amet. Augue amet pulvinar purus vitae, a, amet viverra adipiscing suspendisse. Dictumst sed in donec elit purus ut tincidunt quisque.`,

                para2: `Pretium a augue diam nunc mi. In auctor purus cursus vestibulum sit. Felis cras egestas urna semper auctor sed. Pulvinar ullamcorper amet neque, ut dictumst scelerisque turpis. Consequat nibh et risus tincidunt pellentesque lobortis proin in. Volutpat laoreet dictum tellus venenatis, quis et. In tempor maecenas pulvinar tempor, eget. Cursus vestibulum tortor cursus lacus enim amet laoreet pulvinar. Ac tempus ultrices at vitae potenti eget. Faucibus purus feugiat tortor vestibulum, est feugiat diam habitasse sagittis. Faucibus mattis et eu.`,

                para3: `Fames ut adipiscing commodo tincidunt vivamus leo pretium. In nibh fringilla massa pharetra enim. Euismod integer egestas ultricies fringilla velit commodo. Morbi duis eu, enim nibh. Rhoncus nibh convallis turpis in. Sapien mollis sed semper at. Semper nulla dictum consequat felis quisque fringilla. Id molestie purus eu leo in mattis cursus morbi diam. Aliquam velit maecenas duis erat condimentum arcu cursus augue eu. Nisi, vestibulum mi non cras.`,
            }
        }
    },

    methods: {
        setStory() {
            this.storyExpanded = !this.storyExpanded
            this.aboutBtn = this.storyExpanded ? 'Hide' : 'Read More';
        }
    }
}
</script>

<style>

</style>