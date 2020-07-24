<template>
    <div>
        <ion-card v-for="databook in data">
            <ion-card-content>
                <ion-card-title>{{ databook.title }}</ion-card-title>
                <ion-card-subtitle>{{ databook.author}} </ion-card-subtitle>
                <ion-card-subtitle>{{ databook.pageCount}} pages</ion-card-subtitle>
                <img style="width: 50%; text-align: center;padding-top: 10px;" v-bind:src="databook.thumbnailUrl">
                <ion-col class="ion-padding-top">
                    <ion-text>
                        <p>{{ databook.shortDescription }}</p>
                    </ion-text>
                </ion-col>
            <ion-button style="width: 50%;" @click="deleteBook(databook.isbn)" expand="block" color="danger">Delete</ion-button>
            </ion-card-content>
        </ion-card>
        <ion-fab vertical="bottom" horizontal="end" slot="fixed">
            <ion-fab-button @click="addBook">
                <ion-icon name="add"></ion-icon>
            </ion-fab-button>
        </ion-fab>
    </div>
</template>

<script>

    import dataBooks from "../assets/data.json"
    import modal from "../components/modal.vue"

    export default {
        name: 'Books',
        data() {
            return {
                data: dataBooks,
            }

            return
        },
        methods :{
            deleteBook: function (isbn) {
                this.data = this.data.filter(function (databook) {
                    return databook.isbn !== isbn
                })
            },
            addBook: function () {
                this.$ionic.modalController
                    .create({
                        component: modal
                    })
                    .then(m => m.present())
            },
        },
    }
</script>

<style>
</style>