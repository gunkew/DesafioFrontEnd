<template>
<div class="container">
    <div class="container-wrapper">
        <div class="card" id="City_1" v-on:click="select(1)" value="1">
            <div class="card-contour">
                <div class="card-header"> Urubici, BR</div>
                <div class="content">
                    <div class="loading"></div>
                    <div class="card-body" :class="{blue: this.city_1_temperature <= 5, orange: this.city_1_temperature > 5 && this.city_1_temperature <= 25, red: this.city_1_temperature > 25}"> 19º</div>
                    <div class="card-details" v-show="city_1_details_visible">
                        <div class="detail-row">
                            <div class="detail-content"><p>HUMIDITY</p><p class="unit-value">78<span class="unit-of-measurement">%</span></p></div>
                            <div class="detail-content"><p>PRESSURE</p><p class="unit-value">892<span class="unit-of-measurement">hPA</span></p></div>
                        </div>
                    </div>
                    <div class="card-footer">Updated at 02:48:32 PM</div>
                </div>
            </div>
        </div>
        <div class="card" id="City_2" v-on:click="select(2)" value="2">
            <div class="card-contour">
                <div class="card-header"> Nuuk, GL</div>
                <div class="content">
                    <div class="loading"></div>
                    <div class="card-body" :class="{blue: this.city_2_temperature <= 5, orange: this.city_2_temperature > 5 && this.city_2_temperature <= 25, red: this.city_2_temperature > 25}"> -4º</div>
                    <div class="card-details" v-show="city_2_details_visible">
                        <div class="detail-row">
                            <div class="detail-content"><p>HUMIDITY</p><p class="unit-value">93<span class="unit-of-measurement">%</span></p></div>
                            <div class="detail-content"><p>PRESSURE</p><p class="unit-value">491<span class="unit-of-measurement">hPA</span></p></div>
                        </div>
                    </div>
                    <div class="card-footer">Updated at 02:48:32 PM</div>
                </div>
            </div>
        </div>
        <div class="card" id="City_3" v-on:click="select(3)" value="3">
            <div class="card-contour">
                <div class="card-header"> Nairobi, KE</div>
                <div class="content">
                    <div class="loading"></div>
                    <div class="card-body" :class="{blue: this.city_3_temperature <= 5, orange: this.city_3_temperature > 5 && this.city_3_temperature <= 25, red: this.city_3_temperature > 25}"> 31º</div>
                    <div class="card-details" v-show="city_3_details_visible">
                        <div class="detail-row">
                            <div class="detail-content"><p>HUMIDITY</p><p class="unit-value">28<span class="unit-of-measurement">%</span></p></div>
                            <div class="detail-content"><p>PRESSURE</p><p class="unit-value">1128<span class="unit-of-measurement">hPA</span></p></div>
                        </div>
                    </div>
                    <div class="card-footer">Updated at 02:48:32 PM</div>
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
    font-weight: 500;
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
    export default {
    data() {
        return {
            city_1_details_visible: false,
            city_2_details_visible: false,
            city_3_details_visible: false,
            city_1_temperature: 19,
            city_2_temperature: -4,
            city_3_temperature: 31
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
        weather: function() {
            $.ajax({
                url: 'https://api.openweathermap.org/data/2.5/weather?lat=57&lon=-2.15&appid=80c9a5feddbd8903bd2eb31e52b61e30&units=metric',
                method: 'GET',
                success: function(data) {
                this.comments = data;
                }
            });
        }
    }
}
</script>