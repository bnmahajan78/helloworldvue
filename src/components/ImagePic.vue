<template>
    <div class="post">
        <div v-if="loading" class="loading">
            Loading... Please refresh once the ASP.NET backend has started.
            See <a href="https://aka.ms/jspsintegrationvue">https://aka.ms/jspsintegrationvue</a> for more details.
        </div>

        <div v-if="post" class="content">


            <table>
                <thead>
                    <tr>
                        <th>Date</th>
                        <th>Temp. (C)</th>
                        
                    </tr>
                </thead>
                <tbody>


                    <tr v-for="forecast in post" :key="forecast.date">
                        <td>{{ forecast.date }}</td>
                        <td>{{ forecast.temperatureC }}</td>
                        
                    </tr>




                </tbody>
            </table>
        </div>
    </div>
</template>

<script lang="js">

    // eslint-disable-next-line
    import Vue from 'vue';

    import { defineComponent } from 'vue';



    export default defineComponent({
        // export default Vue.extern({

        data() {
            return {
                loading: false,
                post: null
            };
        },
        created() {
            // fetch the data when the view is created and the data is already being observed
            this.fetchData();
        },
        watch: {
            // call again the method if the route changes
            '$route': 'fetchData'
        },
        methods: {
            fetchData() {
                this.post = null;
                this.loading = true;

                fetch('image') // Name of Controller in small case
                    .then(r => r.json())
                    .then(json => {
                        this.post = json;
                        this.loading = false;
                        return;
                    });
            }
        },
    });
</script>