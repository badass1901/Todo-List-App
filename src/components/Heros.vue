<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div class="d-flex flex-column align-items-center justify-content-center">
        <h1 class="mt-4"> Todo List App</h1>
        <ul class="p-4 mt-5 w-100 card">
            <form @submit.prevent='submit(newHero)'
                class="d-flex p-3 mb-4 card flex-row align-items-center justify-content-between">
                <input :[abstract]='classes' v-model="newHero" placeholder="Enter Todos..." />
                <button class="btn red">
                    <i class="fa fa-check"></i>
                </button>
            </form>
            <li class="card card-body mb-1 p-3 d-flex flex-row justify-content-between" v-for="hero in heros"
                :key="hero">
                <span>{{ hero }}</span>
                <span class="hover-shadow" @click="del(hero)"><i class="fa fa-x" /></span>
            </li>

        </ul>
    </div>
</template>

<script>
export default {
    data() {
        return {
            abstract: 'class',
            classes: ' inputField',
            heros: [],
            newHero: '',
        }
    },
    methods: {
        submit(newHero) {
            var item;
            item = newHero;
            for (let i = 0; i < this.heros.length; i++) {

                if (this.heros[i] === item) {
                    console.log("Found")

                    alert("Already Exists");
                    this.newHero = "";
                    return;
                }
                else {
                    console.log("Not Found")
                }
            }

            if (item !== '') {
                this.heros.push(item);
                this.newHero = '';
            }

            else {

                alert("Enter Todos");




            }
        },
        del(hero) {
            this.heros.splice(this.heros.indexOf(hero), 1);
        }
    }

}
</script>

<style sscoped>
.inputField {
    width: 80%;
    height: 35px;
    border-radius: 5px;
    border: none;
}

.inputField:focus {
    outline: none;

}

.inputField::placeholder {
    color: #999;
}
</style>