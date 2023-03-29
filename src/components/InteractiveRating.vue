<script setup>
import {ref} from "vue"
    const ratingNumbers = ref([
        {
            rating: 1,
            selected: false
        },
        {
            rating: 2,
            selected: false
        },
        {
            rating: 3,
            selected: false
        },
        {
            rating: 4,
            selected: false
        },
        {
            rating: 5,
            selected: false
        }
    ]) 

    const selectedRating = ref(null);

    function selectRating (index) {
        ratingNumbers.value.forEach((rating) => (rating.selected =false));
        ratingNumbers.value[index].selected = true;
        selectedRating.value = ratingNumbers.value[index];
    }
</script>

<template>
    <div class="card-wrapper">
        <div class="card-content">
            <div class="star">
                <img src="../assets/images/icon-star.svg" alt="">
            </div>
            <h1>How do we do?</h1>
            <p>  
                Please let us know how we did with your support request. All feedback is appreciated 
                to help us improve our offering!
            </p>
            <div class="rating-wrap">
                <div class="rating" :class="{'selected-rating': rating.selected}" v-for="(rating, index) in ratingNumbers" :key="index" @click="selectRating(index)">
                    {{ rating.rating }}
                </div>
            </div>
            <button>Submit</button>
        </div>

    </div>
</template>

<style  scoped>

.card-wrapper{
    display: grid;
    place-items: center;
    height: 100vh;
    background: var(--very-dark-blue);
}

.card-content{
    background: var(--dark-blue);
    color: #fff;
    max-width: 450px;
    width: 100%;
    padding: 30px;
    border-radius: 20px;
}

.star{
    background: var(--dark-medium-grey);
    height: 40px;
    width: 40px;
    border-radius: 50%;
    display: grid;
    place-items: center;
    margin-bottom: 1.2rem;
}

h1{
    font-size: 22px;
    margin-bottom: 1rem;
}

p{
    color: var(--light-grey);
    line-height: 1.8;
    max-width: 380px;
    margin-bottom: 1rem;
}

.rating-wrap{
    display: flex;
    justify-content: space-around;
    gap: 15px;
    flex-wrap: wrap;
    margin-bottom: 1rem;
}

.rating{
    color: var(--light-grey);
    background: var(--dark-medium-grey);
    height: 50px;
    width: 50px;
    border-radius: 50%;
    display: grid;
    place-items: center;
    cursor: pointer;
    transition: 200ms ease all;
}

.selected-rating{
    background: var(--medium-grey);
    color: var(--white);
}

.rating:hover{
    background: var(--orange);
    color: var(--white);
}

button{
    width: 100%;
    background: var(--orange);
    color: #fff;
    padding: .8rem 2rem;
    border-radius: 2rem;
    border: none;
    outline: none;
    cursor: pointer;
    text-transform: uppercase;
    font-weight: 700;
    transition: 200ms ease all;
}

button:hover{
    color: var(--orange);
    background: var(--white);
}
</style>