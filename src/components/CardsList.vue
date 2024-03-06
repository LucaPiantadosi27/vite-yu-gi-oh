<script>
import {store} from '../store'
import CardItem from './CardItem.vue';
export default {
    name: 'CardsList',
    data() {
        return {
            store,
        }
    },
    components: {
        CardItem,
    }
}
</script>
<template>
    <div id="carte">
        <span> Card List: </span>  
    </div>
    
    <ul id="cards-list">
        <CardItem v-for="currentCard in store.cards" :card="currentCard"></CardItem>
    </ul>
</template>
<style lang="scss">
@use '../styles/variables' as *;

#carte{
    border: solid rgb(212, 143, 56) 2px;
    
    width: 100%;
    font-size: x-large;
    font-weight: bolder;
    color: brown;
    background-color: rgb(253, 217, 172);
}
#carte span{
  
    background-color: rgb(253, 217, 172);
    margin-left: 43%;

}

#cards-list {
    background-image: url(/img/bck-img.jpg);
    
    border: solid 1,2px rgb(212, 143, 56);
    display: flex;
    flex-flow: wrap;
    gap: $cardListGap;
    padding: 10px;
    
}

#cards-list li{
    // background-image: url(/img/bck-img.jpg);

    border: solid rgb(212, 143, 56);

}
</style>