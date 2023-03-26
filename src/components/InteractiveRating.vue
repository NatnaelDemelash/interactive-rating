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
                <div class="rating" v-for="rating in ratingNumbers" :key="rating.rating">
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
    color: var(--medium-grey);
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
    background: var(--dark-medium-grey);
    height: 50px;
    width: 50px;
    border-radius: 50%;
    display: grid;
    place-items: center;
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
}
</style>