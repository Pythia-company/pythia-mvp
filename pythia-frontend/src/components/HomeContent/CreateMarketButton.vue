<template>
        <span class="create-market-container">
            <button :disabled="!isLoggedIn" @click="click" class="create-market-button" :class="{'inactive-button': !isLoggedIn}">
                <i class="fa-solid fa-plus"></i>
                Create new market
            </button>
        </span>
</template>

<script>
export default {
    methods: {
        click(){
            this.$store.state.showForm = true;
        },
    },
    computed: {
        isLoggedIn(){
             if(this.$store.state.user){
                return true;
            }
            return false;
        }
    }
}
</script>

<style scoped>

    .create-market-container {
        display:flex;
        position: relative;
        align-items: center;
        justify-content: space-between;
        gap: 5px;
    }

    .create-market-button{
        display: flex;
        align-items: center;
        justify-content: space-evenly;
        border-radius: 8px;
        height: 40px;
        width: 180px;
        border: none;
        position:relative;
        background-color: #2060e6;
        font-weight: 400;
        color: #ffffff;
        font-size: 14px;
        font-family: 'Montserrat';
    }
    
    .create-market-button:hover{
        background-color: #4377e8;
    }

    

    .inactive-button {
        filter: brightness(40%);
        pointer-events: none;
    }

    .fas {
        font-family: "Font Awesome 5 Pro";
        font-weight: 1000;
        left: 5px;
        top: 1px;
        position: relative;
        font-size: 20px;
    }
</style>