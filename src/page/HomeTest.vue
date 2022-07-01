<template>
  <div class="home">
    <p>Nos Restaurants</p>
    <RestaurantRow v-for="(data, i) in data_restaurant" :key="i" :three_restaurant="data"/>
  </div>
</template>

<script>
import BDD from '../BDD';
import { onMounted, ref } from 'vue';


//component
import RestaurantRow from '@/components/RestaurantRow.vue';


export default {
    name: 'HomeTest',
    components:{
        RestaurantRow
    },
    
    setup(){
        class Restaurant {
            constructor(name, note, image, time){
                this.name = name
                this.note = note
                this.image = image
                this.time = time
            }
        }

    let data_restaurant = ref([]);


        const makeDataRestaurant = () =>{
            let three_restaurant = [];
            for (const restaurant of BDD){
                const new_restaurant = new Restaurant(restaurant.name, restaurant.note, restaurant.image, restaurant.time)

                if(three_restaurant.length === 2){
                    three_restaurant.push(new_restaurant);
                    data_restaurant.value.push(three_restaurant);
                    three_restaurant = [];
                }
                else{
                    three_restaurant.push(new_restaurant);
                }
            }
        }

        onMounted(makeDataRestaurant);
        //return derniere chose du setup
        return{
            data_restaurant,
        }
    }

}
</script>

<style>

</style>