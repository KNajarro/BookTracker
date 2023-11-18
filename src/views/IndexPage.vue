<template>
    <ion-page>
        <ion-header :translucent="true">
            <ion-toolbar>
                <ion-buttons slot="start">
                    <ion-menu-button color="primary"></ion-menu-button>
                </ion-buttons>
                <ion-title>Inicio</ion-title>
            </ion-toolbar>
        </ion-header>

        <ion-content :fullscreen="true">
            <ion-header collapse="condense">
                <ion-toolbar>
                    <ion-title size="large">Hello, App!</ion-title>
                </ion-toolbar>
            </ion-header>

            <div id="container">
                <ion_grid>
                    <ion-row>
                        <ion-col size="12" sizeSm="6" sizeMd="4" sizeLg="3" v-for="book in currentBooks"
                            v-bind:key="book.id">
                            <ion-card>
                                <ion-row>
                                    <ion-col>
                                        <img :src="book.bookCover" alt="Book Cover"
                                            style="width: autopx; height: 250px; border-radius: 15px; margin-left: 15px; margin-top: 10px;" />
                                    </ion-col>
                                    <ion-col>
                                        <ion-card-header>
                                            <ion-card-title>{{ book.bookName }}</ion-card-title>
                                            <ion-card-subtitle>{{ book.author }}</ion-card-subtitle>
                                        </ion-card-header>
                                        <ion-card-content>
                                            <p class="book-description">Lorem ipsum dolor sit amet consectetur adipisicing elit. Rem deleniti incidunt optio. Ex dicta blanditiis, eum, corporis voluptatibus voluptatem molestiae nam deserunt nostrum ea eius iure recusandae alias qui magnam.</p>
                                        </ion-card-content>
                                    </ion-col>
                                </ion-row>
                            </ion-card>
                        </ion-col>
                    </ion-row>
                </ion_grid>
            </div>
        </ion-content>
    </ion-page>
</template>

<script setup lang="ts">
import { Ref, ref } from 'vue';
import { IonContent, IonHeader, IonPage, IonToolbar } from '@ionic/vue';

const currentBooks = ref(
    [
        {
            id: 1,
            bookName: "100 Años de Soledad",
            bookCover: 'https://m.media-amazon.com/images/I/81rEWmLXliL._AC_UF1000,1000_QL80_.jpg',
            author: "Gabriel Garcia Márquez"
        },
        {
            id: 2,
            bookName: "La Sombra del Viento",
            bookCover: "https://m.media-amazon.com/images/I/61zOWUcvMbL._AC_UF1000,1000_QL80_.jpg",
            author: "Carlos Ruiz Zafón"
        },
        {
            id: 3,
            bookName: "El Viejo y El Mar",
            bookCover: "https://d28hgpri8am2if.cloudfront.net/book_images/onix/cvr9781982104948/el-viejo-y-el-mar-spanish-edition-9781982104948_hr.jpg",
            author: "Ernest Hemingway"
        },
        {
            id: 4,
            bookName: "Contacto",
            bookCover: "https://image.isu.pub/190527021008-8d5a63691597b945629265e28e6d85ea/jpg/page_1_thumb_large.jpg",
            author: "Carl Sagan"
        }
    ]
);
</script>

<style scoped>
    ion-card {
        max-height: 500px;
    }

    .book-description {
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
    }
</style>