<template>
    <div class="main-container">
        <b-container class="bv-example-row">
            <b-row style="padding: 5px;">
                <b-col style="width: 326px; height: 420px; border: 1px solid black; margin: 10px; background-color:white; border:no;" v-for="(Body6,index) in Urunler" :key="index">
                    <div>
                        <p>{{Body6.baslik}}</p>
                        <b-card v-bind:img-src="Body6.image" >
                            <b-form-text>
                                {{Body6.acıklama}}
                            </b-form-text>

                            <a href="#" variant="primary"><small>{{Body6.buton}}</small></a>

                        </b-card>
                    </div>
                </b-col>
            </b-row>
        </b-container>
    </div>
</template>

<script>
    const API_URL = "http://localhost:7000/home"
    export default {

        data: () => ({

            Urunler: []

        }),

        mounted() {

            fetch(API_URL)
                .then(response => response.json())
                .then(result => {
                    this.Urunler = result.Body6;
                    /* eslint-disable */
                    console.log(this.Urunler)
                })

        }

    }
</script>

<style scoped>

</style>