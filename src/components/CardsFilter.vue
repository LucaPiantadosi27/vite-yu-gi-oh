<script>
import {store } from '../store';
import CardsNumber from './CardsNumber.vue';

export default {
    name: 'CardsFilter',
    data() {
        return  {
            store,
        }
    },
}
</script>

<template>

    <div id="cards-filter">

        <select 
            name="archetype-filter" 
            id="archetype-filter" 
            @change="$emit('filter')"
            v-model="store.filterValue"
        >
            <option 
                v-for="currentArchetype in store.archetypes" 
                :value="currentArchetype.archetype_name"
            >
                {{ currentArchetype.archetype_name }}
            </option>
        </select>

        <CardsNumber></CardsNumber>

    </div>

</template>

<style lang="scss">
#cards-filter {
    
    padding: 12px 0;
    border-bottom: 1px solid #777;
    margin-left: 12px;
    // margin-bottom: 2px;
    display: flex;
    justify-content: space-between;
    align-items: center;

    
    select {
        padding: 5px 10px;
        background-color: rgba(77, 75, 91, 0.87);

    }
}
</style>