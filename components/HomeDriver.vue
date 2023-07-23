<script setup>
    import { ref, onMounted } from 'vue'
    import Shepherd from 'shepherd.js';
    import 'shepherd.js/dist/css/shepherd.css';

    let tour;
    onMounted(() => {
        const stepOne = ref(null)

        tour = new Shepherd.Tour({
            defaultStepOptions: {
                classes: 'shadow-md bg-purple-dark',
                scrollTo: true
            }
        });

        tour.addStep({
            title: 'Bienvenido a este tutorial!',
            text: 'Tour 1',
            attachTo: {
                element: '#stepOne',
                on: 'bottom-end'
            },
            buttons: [
                {
                    action: tour.cancel,
                    classes: 'shepherd-button-secondary',
                    text: 'Exit'
                },
                {
                    action: tour.next,
                    text: 'Next'
                }
            ]
        });

        tour.addStep({
            title: 'Bienvenido a este tutorial!',
            text: 'Paso 2.',
            attachTo: {
                element: '#stepTwo',
                on: 'bottom-start'
            },
            buttons: [
                {
                    action: tour.cancel,
                    classes: 'shepherd-button-secondary',
                    text: 'Exit'
                },
                {
                    action: tour.next,
                    text: 'Next'
                }
            ]
        });

        tour.addStep({
            title: 'Bienvenido a este tutorial!',
            text: 'Paso 3.',
            attachTo: {
                element: '#stepThree',
                on: 'bottom-end'
            },
            buttons: [
                {
                    action: tour.cancel,
                    classes: 'shepherd-button-secondary',
                    text: 'Exit'
                },
                {
                    action: tour.next,
                    text: 'Next'
                }
            ]
        });
    })

    const startTour = () => {
        tour.start();
    }

    
</script>

<style>

    .HomeDrive{
        display: flex;
        gap: 30px;
        flex-direction: column;
    }

    .container-step{
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 30px;
        padding: 10px 20px;
    }

    .container-step > div{
        width: 100px;
        height: 100px;
        background-color: #fff;
        border-radius: 50%;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 20px;
        font-weight: bold;
        color: #000;
    }

    .btn{
        font-size:24px;
        font-family:Arial;
        height:50px;
        border-width:0px;
        color:#fff;
        text-transform: capitalize;
        font-weight:bold;
        border-top-left-radius:8px;
        border-top-right-radius:8px;
        border-bottom-left-radius:8px;
        border-bottom-right-radius:8px;
        box-shadow: 0px 10px 14px -7px #276873;
        text-shadow: 0px 1px 0px #3d768a;
        background:linear-gradient(#599bb3, #408c99);
        cursor: pointer;
    }
</style>

<template>
    <div class="HomeDrive">
        <div class="container-step">
            <div ref="stepOne" id="stepOne">
            <h3>Step 1</h3>
            </div>
            <div ref="stepOne" id="stepTwo">
                <h3>Step 2</h3>
            </div>
            <div ref="stepOne" id="stepThree">
                <h3>Step 3</h3>
            </div>
        </div>
        <button class="btn btn-full" @click="startTour">
            start Tour
        </button>
    </div>
</template>