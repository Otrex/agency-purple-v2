<template> 
  <div class="py-[14rem] pt-[8rem]"> 
    <div class="b-wrapper" >
      <h2 class="text-center mb-[8.4rem] max-w-[76rem] mx-auto pb-[2rem] text-gradient">What Our Partners Are saying</h2>

      <div class="grid sm:grid-cols-2 gap-[2rem] text-black">
        <template v-for="(testimonial, idx) in testimonials" :key="idx">
          <div class="flex-none w-full bg-white border-gradient border-solid border py-[5.5rem] px-[4.5rem] rounded-[2.1rem]">
            <div class="mb-[4rem] p md light"> {{ testimonial.description }} </div>
            <div class="flex items-center gap-3"> 
              <div class="w-[6.4rem] aspect-square ">
                <img :src="testimonial.image" class="w-full h-full object-cover rounded-full" alt="testimonial.image" />
              </div>
              <div>{{ testimonial.title }}</div>
            </div>
          </div>
        </template>
        
        <!-- ... more items ... -->
      </div>
      
    </div>
  </div>
</template>

<script setup lang="ts"> 
import { WizardResponse } from '~/type';
const props = defineProps<{ data?: WizardResponse }>();

const testimonials = computed(() => {
  const served = props.data?.agency_wizard.testimonials.map(s => ({
    description: s.description,
    image: s.metaImage || "",
    title: s.name,
  }))

  return (served || []).length ? served : [
    {
      image: "/img/help.jpeg",
      title: "John D., CEO, Tizz Company",
      description: "[COMPANY NAME] transformed our online presence, delivering exceptional results. Highly recommended!"
    },
    {
      image: "/img/help.jpeg",
      title: "John D., CEO, Tizz Company",
      description: "[COMPANY NAME] transformed our online presence, delivering exceptional results. Highly recommended!"
    },
    {
      image: "/img/help.jpeg",
      title: "John D., CEO, Tizz Company",
      description: "[COMPANY NAME] transformed our online presence, delivering exceptional results. Highly recommended!"
    },
    {
      image: "/img/help.jpeg",
      title: "John D., CEO, Tizz Company",
      description: "[COMPANY NAME] transformed our online presence, delivering exceptional results. Highly recommended!"
    },
  ]
})

</script>

<style> 
/* .border-gradient {
  border-image: linear-gradient(159.26deg, #AB3ADD 37.5%, #3B57F4 144.65%);
  border-image-source: linear-gradient(159.26deg, #AB3ADD 37.5%, #3B57F4 144.65%);
  border-image-slice: 1;
} */

</style>