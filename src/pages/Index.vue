<template>
<q-page >
     <q-img src="../assets/images/big-img.jpg" width="100%" alt="Home" id="home"></q-img>
    <div class="content">
        <div class="coluna">
            <div>
                <h1>Ragnachain is a private server of ragnarok online.</h1>
            </div>
            <div>Logo</div>
            <div class="bodyText" id="server">
                The Server will have the divroporsal to be evolutionary over the
                months, the player will be able to obtain crypto currency and real
                money with the proposed missions and objectives. In addition to being
                able to use its resources for trading inside the game. <br />
                ragnachain will be released at freburary'22.
            </div>
            <div>
                <q-img src="../assets/images/raid.jpg" width="300px" alt="Raid"></q-img>
            </div>
            <div id="download">IMG</div>
            <div>
                <q-btn flat class="downloadBtn">DOWNLOAD HERE</q-btn>
            </div>
        </div>
        <h2 align="center" id="currency">currency</h2>
        <div class="coluna">
            <div>you can trade inside the game using this currencies:</div>
            <div>
                bitcoin: US$ {{btcValor.high}} (Last Update: Now) <br>
                ethereum: US$ {{ethValor.high}} (Last Update: Now) <br>
                dogecoin: US$ {{dogeValor.high}} (Last Update: Now) <br>
            </div>

        </div>
    </div>
    <h3 align="center">Developed by cwb gamestudio</h3>
</q-page>
</template>

<script>
import {
    defineComponent
} from "vue";

export default defineComponent({
    name: "PageIndex",
    created() {
        // cotação Bitcoin
        fetch("https://economia.awesomeapi.com.br/last/BTC-USD")
            .then(response => response.json())
            .then(data => (this.btcValor = data.BTCUSD));
        // cotação Ethereum
        fetch("https://economia.awesomeapi.com.br/last/ETH-USD")
            .then(response => response.json())
            .then(data => (this.ethValor = data.ETHUSD));
        // Dogecoin
        fetch("https://economia.awesomeapi.com.br/last/DOGE-USD")
            .then(response => response.json())
            .then(data => (this.dogeValor = data.DOGEUSD));
    },
    data() {
        return {
            btcValor: [],
            ethValor: [],
            dogeValor: []
        }
    },
});
</script>
