<script setup>
import faqs from "../data/faqs.js";
import { ref } from "vue";

let isOpen = ref(1);
</script>

<template>
    <!-- Questions Section Start -->
    <div id="about" class="container mx-auto px-5 md:w-4/5">
        <section class="py-16 pt-18">
            <div class="w-4/5 md:w-3/5 mx-auto">
                <h2 class="text-3xl md:text-4xl font-theme-heading font-medium text-center">About Me</h2>
                <p class="text-theme-grayish-blue text-center mt-7 font-theme-content text-lg">I am a devoted follower of most sports, especially soccer (Liverpool) and 
                    American football (Eagles). I am an avid reader of science fiction and 
                    non-fiction business books.</p>
                <p class="text-theme-grayish-blue text-center mt-7 font-theme-content text-lg">My biggest loves are travel, playing guitar, and 
                    video gaming. I like to foster dogs in need of adoption and regularly donate to 
                    both human and animal charities. I am a podcast fanatic, my favourites being 
                    anything from The Ringer, Writing Excuses, and Triple-Click.</p>
            </div>

            <div class="mt-10 w-full lg:w-3/5 mx-auto">
                <ul class="shadow-lg">
                    <template v-for="(faq, index) in faqs" :key="faq.id">
                        <li @click="isOpen = faq.id" :class="isOpen === faq.id ? 'text-theme-secondary' : ''" class="font-theme-content font-medium text-xl cursor-pointer hover:text-theme-secondary py-5 flex justify-between items-center transition duration-200 bg-slate-100 px-6">
                            <a href="#">{{ faq.title }}</a>
                            <svg :class="isOpen === faq.id ? 'rotate-180 text-theme-secondary' : 'rotate-0 text-theme-primary'" class="transform" xmlns="http://www.w3.org/2000/svg" width="18" height="12"><path fill="none" stroke="currentColor" stroke-width="3" d="M1 1l8 8 8-8" /></svg>
                        </li>
                        <p v-show="isOpen === faq.id" class="bg-slate-50 px-6 font-theme-content text-md lg:text-lg py-5 text-gray-500 text-justify">{{ faq.description }}</p>
                    </template>
                </ul>
                <div class="flex justify-center mt-10">
                </div>
            </div>
        </section>
    </div>
    <!-- Questions Section End -->
</template>
