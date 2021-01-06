<template>
    <div class="w-4/5 m-auto text-white py-14 ">
         <h1 class="text-5xl text-dropboxyellow w-3/4">File storage and sharing are just the beginning</h1>

         <div class="flex mt-6 text-gray-400">
             <div id="scroll-snap-text" class="w-4/12">
                <div class="mt-6 cursor-pointer active-section pl-5 snap-text"  data-index="1" @click="slide" id="organise">
                    <h1 class="text-3xl mb-8 font-bold">Be organized</h1>
                    <p class="text-xl">Bring traditional files, cloud content, Dropbox Paper docs, and web shortcuts together in one place—and work the way that works for you.</p>
                </div>

                 <div class="mt-6 pl-5 cursor-pointer snap-text"  data-index="1" @click="slide" id="focussed">
                    <h1  class="text-3xl mb-8 font-bold" data-index="2" @click="slide">Stay focussed</h1>
                    <p class="text-xl">Personalized suggestions give you files and folders when you need them so you spend less time searching</p>
                </div>

                <div class="mt-6 pl-5 cursor-pointer snap-text"  data-index="1" @click="slide" id="sync">
                    <h1  class="text-3xl mb-8 font-bold">Get in sync</h1>
                    <p class="text-xl">Coordinate with your team and push projects forward with the tools you use every day—all within Dropbox.</p>
                </div>
             </div>

             <div id="scroll-snap-image" class="w-8/12 relative">
                <div class="snap-item"> <img src="../../public/organized.png" alt=""></div>
                 <div class="snap-item"> <img src="../../public/focussed.png" alt=""></div>
                  <div class="snap-item">  <img src="../../public/sync.png" alt=""></div>
             </div>

         </div>

        <div class="my-12">
            <hr>
        </div>
    </div>
</template>

<script>
export default {
  data () {
    return {
      slideLoc: 1
    }
  },
  methods: {
    slide (event) {
      const parentNode = event.target.parentNode
      if (parentNode.classList.contains('snap-text')) {
        document.querySelectorAll('.snap-text').forEach((el) => el.classList.remove('active-section'))
        parentNode.classList.add('active-section')
        const index = parentNode.getAttribute('data-index')
        const imageContainer = document.querySelector('#scroll-snap-image')
        console.log(imageContainer.style.top)
        if (index === 2 && this.slideLoc === 1) {
          imageContainer.style.top = '1000px'
        }
      }
    }
  }
}
</script>
<style scoped>

    #scroll-snap-image {
        max-height: 100vh;
        overflow-y: hidden;
        scroll-snap-type: mandatory;
        scroll-snap-type: y mandatory;
    }

    .active-section {
        border-left: 2px solid #ffe7aa;
        color:white;
    }

    #snap-item {
        scroll-snap-align: start;
    }
</style>
