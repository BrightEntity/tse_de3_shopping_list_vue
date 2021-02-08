<template>
    <div>
        <form @submit="$event.preventDefault(); ajouterElement(message)">
            <input type="text" placeholder="Message" v-model="message" /> <input type="button" value="Ajouter" @click="ajouterElement(message)" />
        </form>
        <ul>
            <li v-for="element in elements" :key="element.key">{{ element.message }} <input type="button" @click="supprElement(element.key)" value="Supprimer" /></li>
        </ul>
    </div>

</template>

<script>
    import {v4 as uuidv4} from 'uuid';

    export default {
        name: "ShoppingList",
        data: function () {
            return {
                elements: [],
                message: ""
            }
        },
        methods: {
            supprElement(key) {
                this.elements = this.elements.reduce((acc, n) => {
                    if(n.key != key) {
                        acc.push(n);
                    }
                    return acc;
                }, []);
            },
            ajouterElement(message) {
                this.elements.push({
                    "key": uuidv4(),
                    "message": message
                })

                this.message = ""
            }
        }
    }
</script>