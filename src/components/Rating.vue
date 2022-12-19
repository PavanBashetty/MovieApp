<template>
    <h2 class="text-center">{{titleName}}</h2>
    <!-- <button v-on:click="backToHomePage()" >Back to home page</button> -->
    <div class="text-center">    
        <v-rating length="10" v-model="rating" @update:model-value="setRating(rating,titleName)" :item-labels="labels">   
            <template v-slot:item-label="props">  
                <span class="font-weight-black text-caption" :class="`text-${colors[props.index]}`">
    
                    {{ props.label }}
    
                </span>
    
    
    
            </template>
    
        </v-rating>
    
        
    
    </div>
    
    <h5 class="text-center">You rated {{ rating }} stars for {{titleName}} Movie</h5>
    
    </template>
    
    
    
        
    
    <script>
    
    export default {
    
        name: 'RatingPageComp',
    
        props: ['title'],
    
        emits: ["rated"],
    
        methods: {
    
    
    
            backToHomePage() {
    
                return this.$router.push({
    
                    name: 'HomePage'
    
                })
    
            },
    
            //         addRating(a,b) {
    
            //   return  console.log({title: b,rating: a});
    
            // },
    
            setRating(a,b) {
    
                this.$emit("rated",
    
                 {
    
                    title: b,
    
                    rating: a
    
                }
    
                )
    
                // return console.log(a,b, "setrating")
    
            }
    
        },
    
        data() {
    
            return {
    
    
    
                titleName:this.title,
    
                rating: 3,
    
                colors: ['red', 'orange', 'grey', 'cyan', 'green','red', 'orange', 'grey', 'cyan', 'green'],
    
                labels: ['Worst', 'Very bad','Bad', 'ok','average', 'good', 'very good', 'Excellent', 'Stunning', 'Fantastic'],
    
            }
    
        },
    
    
    
    }
    
    </script>
    
    
    
        
    
    <style>
    
    
    
        </style>