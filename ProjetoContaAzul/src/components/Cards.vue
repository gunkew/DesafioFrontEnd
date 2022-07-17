<template>
<div class="container">
    <div class="container-wrapper">
        <div class="card" id="City_1" v-on:click="select(1)" value="1">
            <div class="card-contour">
                <div class="card-header"> Urubici, BR</div>
                <div class="content">
                    <div class="loader" v-show="this.city_1_loading === true"> 
                        <img src="..\assets\loader.svg" alt="carregando" width="125" height="125">
                    </div>
                    <div class="card-body" v-show="this.city_1_loading === false" v-if="this.city_1.temp >= 0" :class="{blue: this.city_1.temp <= 5, orange: this.city_1.temp > 5 && this.city_1.temp <= 25, red: this.city_1.temp > 25}"> {{this.city_1.temp}}º</div>
                    <div class="card-details" v-show="city_1_details_visible">
                        <div class="detail-row">
                            <div class="detail-content"><p>HUMIDITY</p><p class="unit-value">{{this.city_1.humidity}}<span class="unit-of-measurement">%</span></p></div>
                            <div class="detail-content"><p>PRESSURE</p><p class="unit-value">{{this.city_1.pressure}}<span class="unit-of-measurement">hPA</span></p></div>
                        </div>
                    </div>
                    <div class="card-footer">Updated at {{this.city_1.last_update}}</div>
                </div>
            </div>
        </div>
        <div class="card" id="City_2" v-on:click="select(2)" value="2">
            <div class="card-contour">
                <div class="card-header"> Nuuk, GL</div>
                <div class="content">
                    <div class="loader" v-show="this.city_2_loading === true"> 
                        <img src="..\assets\loader.svg" alt="carregando" width="125" height="125">
                    </div>
                    <div class="card-body" v-show="this.city_2_loading === false" v-if="this.city_2.temp >= 0" :class="{blue: this.city_2.temp <= 5, orange: this.city_2.temp > 5 && this.city_2.temp <= 25, red: this.city_2.temp > 25}" > {{this.city_2.temp}}º</div>
                    <div class="card-details" v-show="city_2_details_visible">
                        <div class="detail-row">
                            <div class="detail-content"><p>HUMIDITY</p><p class="unit-value">{{this.city_2.humidity}}<span class="unit-of-measurement">%</span></p></div>
                            <div class="detail-content"><p>PRESSURE</p><p class="unit-value">{{this.city_2.pressure}}<span class="unit-of-measurement">hPA</span></p></div>
                        </div>
                    </div>
                    <div class="card-footer">Updated at {{this.city_2.last_update}}</div>
                </div>
            </div>
        </div>
        <div class="card" id="City_3" v-on:click="select(3)" value="3">
            <div class="card-contour">
                <div class="card-header"> Nairobi, KE</div>
                <div class="content">
                    <div class="loader" v-show="this.city_3_loading === true"> 
                        <img src="..\assets\loader.svg" alt="carregando" width="125" height="125">
                    </div>
                    <div class="card-body" v-show="this.city_3_loading === false" v-if="this.city_3.temp >= 0" :class="{blue: this.city_3.temp <= 5, orange: this.city_3.temp > 5 && this.city_3.temp <= 25, red: this.city_3.temp > 25}"> {{this.city_3.temp}}º</div>
                    <div class="card-details" v-show="city_3_details_visible">
                        <div class="detail-row">
                            <div class="detail-content"><p>HUMIDITY</p><p class="unit-value">{{this.city_3.humidity}}<span class="unit-of-measurement">%</span></p></div>
                            <div class="detail-content"><p>PRESSURE</p><p class="unit-value">{{this.city_3.pressure}}<span class="unit-of-measurement">hPA</span></p></div>
                        </div>
                    </div>
                    <div class="card-footer">Updated at {{this.city_3.last_update}}</div>
                </div>
            </div>
        </div>
    </div>
  </div>
</template>

<style> 

.container {
    margin-top: 4rem;
}

.blue {
    color:#69a3ff
}

.orange {
    color: #ff9632;
}

.red {
    color: #ed1946;
}

.loader {
    width: 100%;
    display: flex;
    margin: auto;
    justify-content: center;
    height: 12rem;
    align-items: center;
}

.container-wrapper {
    display: inline-flex;
    width: 100vw;
    justify-content: center;
    flex-wrap: wrap;
    align-items: center;
}

.card > .card-contour {
    box-shadow: 0 0 8px 1px #3333331a;
    border-radius: 5px 5px 5px 5px;
}

.card-contour:hover {
    box-shadow: 0 0 8px 1px #3333335e;
}

.card-details {
    height: 4rem;
    background-color: var(--color-header-background);
    width: 100%;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    color: var(--color-text);
    opacity: 0.5;
    border-radius: 0px 0px 5px 5px;
}

.detail-row {
    width: 100%;
    height: 100%;
    display: inline-flex;
}

.detail-content {
    width: 50%;
    display: inline-flex;
    flex-direction: column;
    align-content: center;
    flex-wrap: nowrap;
    align-items: center;
    justify-content: center;
}

.unit-value {
    font-size: 18px;
    font-weight: 600;
}

.unit-of-measurement {
    font-size: 12px;
    color: var(--color-text);
}

@media (min-width: 601px) {
.card {
    margin: 2rem;
    display: inline-flex;
    flex-direction: column;
    width: 20em;
    min-height: 18rem;
    cursor: pointer;
}

.card-header {
    height: calc(3rem - 1px);
    background-color: var(--color-header-background);
    width: 100%;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    color: var(--color-text);
    border-radius: 5px 5px 0px 0px;
    border-bottom: 1px solid var(--color-card-divider);
    font-size: 20px;
}

.card-body {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: row;
    width: 100%;
    height: 12rem;
    background-color: var(--color-header-background);
    font-size: 7rem;
}

.card-footer {
    height: 3rem;
    background-color: var(--color-header-background);
    width: 100%;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    color: var(--color-text);
    border-bottom: 2px solid var(--color-app-background);
    opacity: 0.5;
    border-radius: 0px 0px 5px 5px;
}
}

@media (max-width: 600px) {
.container {
    margin-top: 4rem;
    margin-bottom: 2rem;
}

.container-wrapper {
    flex-wrap: wrap;
    flex-direction: column;
    align-content: center;
}

.card {
    margin-top: 2rem;
    display: flex;
    flex-direction: column;
    width: 100%;
    min-height: 18rem;
    max-width: 18em;
    cursor: pointer;
}

.card-header {
    height: calc(3rem - 1px);
    background-color: var(--color-header-background);
    width: 100%;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    color: var(--color-text);
    border-radius: 5px 5px 0px 0px;
    border-bottom: 1px solid var(--color-card-divider);
    font-size: 20px;
}

.card-body {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: row;
    width: 100%;
    height: 12rem;
    background-color: var(--color-header-background);
    font-size: 7rem;
}

.card-footer {
    height: 3rem;
    background-color: var(--color-header-background);
    width: 100%;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    color: var(--color-text);
    border-bottom: 2px solid var(--color-app-background);
    opacity: 0.5;
    border-radius: 0px 0px 5px 5px;
}

}

</style>

<script>
import { defineComponent, onMounted, ref } from "vue";
import axios from "axios";
 const cidade_1 = ref([]);
    export default {
    name: 'Cards',
    data() {
        return {
            city_1_details_visible: false,
            city_2_details_visible: false,
            city_3_details_visible: false,
            city_1_loading: true,
            city_2_loading: true,
            city_3_loading: true,
            city_1: {
                temp: 0,
                humidity: 0,
                pressure: 0,
                last_update: null
            },
            city_2: {
                temp: 0,
                humidity: 0,
                pressure: 0
            },
            city_3: {
                temp: 0,
                humidity: 0,
                pressure: 0
            },
            timer_city_1: [],
            timer_city_2: [],
            timer_city_3: [],
        }
    },
    methods: {
        select: function(elementValue) {
            if (elementValue == 1) {
                this.city_1_details_visible = true;
                this.city_2_details_visible = false;
                this.city_3_details_visible = false;
            }
            if (elementValue == 2){
                this.city_1_details_visible = false;
                this.city_2_details_visible = true;
                this.city_3_details_visible = false;
            }
            if (elementValue == 3){
                this.city_1_details_visible = false;
                this.city_2_details_visible = false;
                this.city_3_details_visible = true;
            }
        },
        sleep: function(ms){
            return new Promise(resolve => setTimeout(resolve, ms));
        },
        update: function(duration, method){

            var timer = duration, minutes, seconds;

            setInterval(function () {
                minutes = parseInt(timer / 60, 10);
                seconds = parseInt(timer % 60, 10);

                minutes = minutes < 10 ? "0" + minutes : minutes;
                seconds = seconds < 10 ? "0" + seconds : seconds;

                console.log("próxima atualização das cidades em " + minutes + ":" + seconds);

                if (--timer < 0) {
                    method();
                    timer = duration;
                }
            }, 1000);
            
        },
        async updateAllCities(){
            const randomNumber = Math.floor(Math.random() * 8) + 1;
            var timer_city1 = 3000;
            var timer_city2 = 5000;
            var timer_city3 = 7000;
            this.city_1_loading = true;
            this.city_2_loading = true;
            this.city_3_loading = true;

            await this.sleep(1000);
            this.getCityWeather(-28.014999, -49.591671, 1);

            await this.sleep(2000);
            this.getCityWeather(64.183472, -51.721569, 2);

            await this.sleep(1000);
            this.getCityWeather(-1.28333, 36.833328, 3);
        },
        async getCityWeather(lat, lon, citySelected) {
            

            await axios.get('https://api.openweathermap.org/data/2.5/weather?lat='+ lat + '&lon=' + lon + '&lang=pt_br&appid=80c9a5feddbd8903bd2eb31e52b61e30&units=metric')
            .then((response) => {
                const weather = response.data == null && !response.data.hasOwnProperty('data') ? null : response.data;
                
                console.log('Atualizando a cidade: ' + citySelected);
                //console.log(weather);
                if (weather != null && citySelected == 1) {
                    this.city_1.temp = weather.main.temp.toFixed(0);
                    this.city_1.humidity = weather.main.humidity;
                    this.city_1.pressure = weather.main.pressure;
                    this.city_1.last_update = new Date().toLocaleTimeString("en");
                    this.city_1_loading = false;
                }
                if (weather != null && citySelected == 2) {
                    this.city_2.temp = weather.main.temp.toFixed(0);
                    this.city_2.humidity = weather.main.humidity;
                    this.city_2.pressure = weather.main.pressure;
                    this.city_2.last_update = new Date().toLocaleTimeString("en");
                    this.city_2_loading = false;
                }
                if (weather != null && citySelected == 3) {
                    this.city_3.temp = weather.main.temp.toFixed(0);
                    this.city_3.humidity = weather.main.humidity;
                    this.city_3.pressure = weather.main.pressure;
                    this.city_3.last_update = new Date().toLocaleTimeString("en");
                    this.city_3_loading = false;
                }
            })
            .catch(error => (
                console.log(error)
            ));
        }
    },
    mounted() {
        // Urubici, BR
        this.getCityWeather(-28.014999, -49.591671, 1);  // lat e lon obtido da lista de cidades do https://openweathermap.org/
        
        // Nuuk, GL
        this.getCityWeather(64.183472, -51.721569, 2); // lat e lon obtido da lista de cidades do https://openweathermap.org/
        
        // Nairobi, KE
        this.getCityWeather(-1.28333, 36.833328, 3); // lat e lon obtido da lista de cidades do https://openweathermap.org/
        
        this.update(20, this.updateAllCities);//1 * 60
    }
}
</script>