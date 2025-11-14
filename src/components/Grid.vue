<script setup>
    import { workoutProgram } from '../utils';

    const workoutTypes = ['Push', 'Pull', 'Legs']
</script>

<template>
    <section id="grid">
        <button :key="workoutIds" v-for="(workout, workoutIds) in Object.keys(workoutProgram)" class="card-button plan-card">
            <div>
                <p>Day {{ workoutIds < 9 ? `0${workoutIds + 1}` : workoutIds + 1 }}</p>
                <i class="fa-solid fa-dumbbell" v-if="workoutIds % 3 == 0"></i>
                <i class="fa-solid fa-weight-hanging" v-if="workoutIds % 3 == 1"></i>
                <i class="fa-solid fa-bolt" v-if="workoutIds % 3 == 2"></i>
            </div>
            <h3>
                {{ workoutTypes[workoutIds % 3] }}
            </h3>
        </button>
    </section>
</template>

<style scoped>
    #grid {
        display: grid;
        grid-template-columns: repeat(3, minmax(0, 1fr));
        gap: 1rem;
    }

    #grid button {
        width: 100%;
    }

    .plan-card {
        display: flex;
        flex-direction: column;
    }

    .plan-card div {
        display: flex;
        align-items: center;
        justify-content: space-between;
        gap: 0.5rem;
    }

    .plan-card div p {
        text-align: left;
    }

    @media (min-width: 640px) {
        #grid {
            grid-template-columns: repeat(4, minmax(0, 1fr));
        }
    }
</style>
