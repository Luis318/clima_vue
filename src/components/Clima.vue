<script setup>
    import useClima from '../composable/useClima';

    const { formaterTemperatura } = useClima()

    defineProps({
        clima: {
            type: Object,
            required: true
        }
    })
</script>

<template>
    <div class="resultado">
        <h2>Clima de: {{ clima.name }}</h2>
        <p class="actual">{{ formaterTemperatura(clima.main.temp) }} &deg;C</p>
        <div class="temperaturas">
            <p>Min: {{ formaterTemperatura(clima.main.temp_min) }} <span>&deg;C</span></p>
            <p>Max: {{ formaterTemperatura(clima.main.temp_max) }} <span>&deg;C</span></p>
        </div>
    </div>
</template>