<template>
  <div class="conversor">
    <h2>Currency Converter</h2>
    <div class="from-to">
      <label>From: </label>
      <input type="text" v-model="A" v-bind:placeholder="defaultA" />
      <label>To: </label>
      <input type="text" v-model="B" v-bind:placeholder="defaultB" />
      <label>Value: </label>
      <input type="number" v-model="A_value" />
    </div>

    <input class="button" type="button" value="Convert" v-on:click="convert" />
    <h2>OUTPUT: {{ B_value.toFixed(2) }}</h2>

    <h3>Available:</h3>
    <p class="currency">
      &lt;AED&gt;Dirham dos Emirados&lt;/AED&gt;<br />
      &lt;AFN&gt;Afghani do Afeganistão&lt;/AFN&gt;<br />
      &lt;ALL&gt;Lek Albanês&lt;/ALL&gt;<br />
      &lt;AMD&gt;Dram Armênio&lt;/AMD&gt;<br />
      &lt;ANG&gt;Guilder das Antilhas&lt;/ANG&gt;<br />
      &lt;AOA&gt;Kwanza Angolano&lt;/AOA&gt;<br />
      &lt;ARS&gt;Peso Argentino&lt;/ARS&gt;<br />
      &lt;AUD&gt;Dólar Australiano&lt;/AUD&gt;<br />
      &lt;AZN&gt;Manat Azeri&lt;/AZN&gt;<br />
      &lt;BAM&gt;Marco Conversível&lt;/BAM&gt;<br />
      &lt;BBD&gt;Dólar de Barbados&lt;/BBD&gt;<br />
      &lt;BDT&gt;Taka de Bangladesh&lt;/BDT&gt;<br />
      &lt;BGN&gt;Lev Búlgaro&lt;/BGN&gt;<br />
      &lt;BHD&gt;Dinar do Bahrein&lt;/BHD&gt;<br />
      &lt;BIF&gt;Franco Burundinense&lt;/BIF&gt;<br />
      &lt;BND&gt;Dólar de Brunei&lt;/BND&gt;<br />
      &lt;BOB&gt;Boliviano&lt;/BOB&gt;<br />
      &lt;BRL&gt;Real Brasileiro&lt;/BRL&gt;<br />
      &lt;BRLT&gt;Real Brasileiro Turismo&lt;/BRLT&gt;<br />
      &lt;BSD&gt;Dólar das Bahamas&lt;/BSD&gt;<br />
      &lt;BTC&gt;Bitcoin&lt;/BTC&gt;<br />
      &lt;BWP&gt;Pula de Botswana&lt;/BWP&gt;<br />
      &lt;BYN&gt;Rublo Bielorrusso&lt;/BYN&gt;<br />
      &lt;BZD&gt;Dólar de Belize&lt;/BZD&gt;<br />
      &lt;CAD&gt;Dólar Canadense&lt;/CAD&gt;<br />
      &lt;CHF&gt;Franco Suíço&lt;/CHF&gt;<br />
      &lt;CHFRTS&gt;Franco Suíço&lt;/CHFRTS&gt;<br />
      &lt;CLP&gt;Peso Chileno&lt;/CLP&gt;<br />
      &lt;CNH&gt;Yuan chinês offshore&lt;/CNH&gt;<br />
      &lt;CNY&gt;Yuan Chinês&lt;/CNY&gt;<br />
      &lt;COP&gt;Peso Colombiano&lt;/COP&gt;<br />
      &lt;CRC&gt;Colón Costarriquenho&lt;/CRC&gt;<br />
      &lt;CUP&gt;Peso Cubano&lt;/CUP&gt;<br />
      &lt;CVE&gt;Escudo cabo-verdiano&lt;/CVE&gt;<br />
      &lt;CZK&gt;Coroa Checa&lt;/CZK&gt;<br />
      &lt;DJF&gt;Franco do Djubouti&lt;/DJF&gt;<br />
      &lt;DKK&gt;Coroa Dinamarquesa&lt;/DKK&gt;<br />
      &lt;DOGE&gt;Dogecoin&lt;/DOGE&gt;<br />
      &lt;DOP&gt;Peso Dominicano&lt;/DOP&gt;<br />
      &lt;DZD&gt;Dinar Argelino&lt;/DZD&gt;<br />
      &lt;EGP&gt;Libra Egípcia&lt;/EGP&gt;<br />
      &lt;ETB&gt;Birr Etíope&lt;/ETB&gt;<br />
      &lt;ETH&gt;Ethereum&lt;/ETH&gt;<br />
      &lt;EUR&gt;Euro&lt;/EUR&gt;<br />
      &lt;FJD&gt;Dólar de Fiji&lt;/FJD&gt;<br />
      &lt;GBP&gt;Libra Esterlina&lt;/GBP&gt;<br />
      &lt;GEL&gt;Lari Georgiano&lt;/GEL&gt;<br />
      &lt;GHS&gt;Cedi Ganês&lt;/GHS&gt;<br />
      &lt;GMD&gt;Dalasi da Gâmbia&lt;/GMD&gt;<br />
      &lt;GNF&gt;Franco de Guiné&lt;/GNF&gt;<br />
      &lt;GTQ&gt;Quetzal Guatemalteco&lt;/GTQ&gt;<br />
      &lt;HKD&gt;Dólar de Hong Kong&lt;/HKD&gt;<br />
      &lt;HNL&gt;Lempira Hondurenha&lt;/HNL&gt;<br />
      &lt;HRK&gt;Kuna Croata&lt;/HRK&gt;<br />
      &lt;HTG&gt;Gourde Haitiano&lt;/HTG&gt;<br />
      &lt;HUF&gt;Florim Húngaro&lt;/HUF&gt;<br />
      &lt;IDR&gt;Rupia Indonésia&lt;/IDR&gt;<br />
      &lt;ILS&gt;Novo Shekel Israelense&lt;/ILS&gt;<br />
      &lt;INR&gt;Rúpia Indiana&lt;/INR&gt;<br />
      &lt;IQD&gt;Dinar Iraquiano&lt;/IQD&gt;<br />
      &lt;IRR&gt;Rial Iraniano&lt;/IRR&gt;<br />
      &lt;ISK&gt;Coroa Islandesa&lt;/ISK&gt;<br />
      &lt;JMD&gt;Dólar Jamaicano&lt;/JMD&gt;<br />
      &lt;JOD&gt;Dinar Jordaniano&lt;/JOD&gt;<br />
      &lt;JPY&gt;Iene Japonês&lt;/JPY&gt;<br />
      &lt;JPYRTS&gt;Iene Japonês&lt;/JPYRTS&gt;<br />
      &lt;KES&gt;Shilling Queniano&lt;/KES&gt;<br />
      &lt;KGS&gt;Som Quirguistanês&lt;/KGS&gt;<br />
      &lt;KHR&gt;Riel Cambojano&lt;/KHR&gt;<br />
      &lt;KMF&gt;Franco Comorense&lt;/KMF&gt;<br />
      &lt;KRW&gt;Won Sul-Coreano&lt;/KRW&gt;<br />
      &lt;KWD&gt;Dinar Kuwaitiano&lt;/KWD&gt;<br />
      &lt;KYD&gt;Dólar das Ilhas Cayman&lt;/KYD&gt;<br />
      &lt;KZT&gt;Tengue Cazaquistanês&lt;/KZT&gt;<br />
      &lt;LAK&gt;Kip Laosiano&lt;/LAK&gt;<br />
      &lt;LBP&gt;Libra Libanesa&lt;/LBP&gt;<br />
      &lt;LKR&gt;Rúpia de Sri Lanka&lt;/LKR&gt;<br />
      &lt;LSL&gt;Loti do Lesoto&lt;/LSL&gt;<br />
      &lt;LTC&gt;Litecoin&lt;/LTC&gt;<br />
      &lt;LTC&gt;Litecoin&lt;/LTC&gt;<br />
      &lt;LYD&gt;Dinar Líbio&lt;/LYD&gt;<br />
      &lt;MAD&gt;Dirham Marroquino&lt;/MAD&gt;<br />
      &lt;MDL&gt;Leu Moldavo&lt;/MDL&gt;<br />
      &lt;MGA&gt;Ariary Madagascarense&lt;/MGA&gt;<br />
      &lt;MKD&gt;Denar Macedônio&lt;/MKD&gt;<br />
      &lt;MMK&gt;Kyat de Mianmar&lt;/MMK&gt;<br />
      &lt;MNT&gt;Mongolian Tugrik&lt;/MNT&gt;<br />
      &lt;MOP&gt;Pataca de Macau&lt;/MOP&gt;<br />
      &lt;MRO&gt;Ouguiya Mauritana&lt;/MRO&gt;<br />
      &lt;MUR&gt;Rúpia Mauriciana&lt;/MUR&gt;<br />
      &lt;MVR&gt;Rufiyaa Maldiva&lt;/MVR&gt;<br />
      &lt;MWK&gt;Kwacha Malauiana&lt;/MWK&gt;<br />
      &lt;MXN&gt;Peso Mexicano&lt;/MXN&gt;<br />
      &lt;MYR&gt;Ringgit Malaio&lt;/MYR&gt;<br />
      &lt;MZN&gt;Metical de Moçambique&lt;/MZN&gt;<br />
      &lt;NAD&gt;Dólar Namíbio&lt;/NAD&gt;<br />
      &lt;NGN&gt;Naira Nigeriana&lt;/NGN&gt;<br />
      &lt;NGNI&gt;Naira Nigeriana&lt;/NGNI&gt;<br />
      &lt;NGNPARALLEL&gt;Naira Nigeriana&lt;/NGNPARALLEL&gt;<br />
      &lt;NIO&gt;Córdoba Nicaraguense&lt;/NIO&gt;<br />
      &lt;NOK&gt;Coroa Norueguesa&lt;/NOK&gt;<br />
      &lt;NPR&gt;Rúpia Nepalesa&lt;/NPR&gt;<br />
      &lt;NZD&gt;Dólar Neozelandês&lt;/NZD&gt;<br />
      &lt;OMR&gt;Rial Omanense&lt;/OMR&gt;<br />
      &lt;PAB&gt;Balboa Panamenho&lt;/PAB&gt;<br />
      &lt;PEN&gt;Sol do Peru&lt;/PEN&gt;<br />
      &lt;PGK&gt;Kina Papua-Nova Guiné&lt;/PGK&gt;<br />
      &lt;PHP&gt;Peso Filipino&lt;/PHP&gt;<br />
      &lt;PKR&gt;Rúpia Paquistanesa&lt;/PKR&gt;<br />
      &lt;PLN&gt;Zlóti Polonês&lt;/PLN&gt;<br />
      &lt;PYG&gt;Guarani Paraguaio&lt;/PYG&gt;<br />
      &lt;QAR&gt;Rial Catarense&lt;/QAR&gt;<br />
      &lt;RON&gt;Leu Romeno&lt;/RON&gt;<br />
      &lt;RSD&gt;Dinar Sérvio&lt;/RSD&gt;<br />
      &lt;RUB&gt;Rublo Russo&lt;/RUB&gt;<br />
      &lt;RUBTOD&gt;Rublo Russo&lt;/RUBTOD&gt;<br />
      &lt;RUBTOM&gt;Rublo Russo&lt;/RUBTOM&gt;<br />
      &lt;RWF&gt;Franco Ruandês&lt;/RWF&gt;<br />
      &lt;SAR&gt;Riyal Saudita&lt;/SAR&gt;<br />
      &lt;SCR&gt;Rúpias de Seicheles&lt;/SCR&gt;<br />
      &lt;SDG&gt;Libra Sudanesa&lt;/SDG&gt;<br />
      &lt;SDR&gt;DSE&lt;/SDR&gt;<br />
      &lt;SEK&gt;Coroa Sueca&lt;/SEK&gt;<br />
      &lt;SGD&gt;Dólar de Cingapura&lt;/SGD&gt;<br />
      &lt;SOS&gt;Shilling Somaliano&lt;/SOS&gt;<br />
      &lt;STD&gt;Dobra São Tomé/Príncipe&lt;/STD&gt;<br />
      &lt;SVC&gt;Colon de El Salvador&lt;/SVC&gt;<br />
      &lt;SYP&gt;Libra Síria&lt;/SYP&gt;<br />
      &lt;SZL&gt;Lilangeni Suazilandês&lt;/SZL&gt;<br />
      &lt;THB&gt;Baht Tailandês&lt;/THB&gt;<br />
      &lt;TJS&gt;Somoni do Tajiquistão&lt;/TJS&gt;<br />
      &lt;TMT&gt;TMT&lt;/TMT&gt;<br />
      &lt;TND&gt;Dinar Tunisiano&lt;/TND&gt;<br />
      &lt;TRY&gt;Nova Lira Turca&lt;/TRY&gt;<br />
      &lt;TTD&gt;Dólar de Trinidad&lt;/TTD&gt;<br />
      &lt;TWD&gt;Dólar Taiuanês&lt;/TWD&gt;<br />
      &lt;TZS&gt;Shilling Tanzaniano&lt;/TZS&gt;<br />
      &lt;UAH&gt;Hryvinia Ucraniana&lt;/UAH&gt;<br />
      &lt;UGX&gt;Shilling Ugandês&lt;/UGX&gt;<br />
      &lt;USD&gt;Dólar Americano&lt;/USD&gt;<br />
      &lt;USDT&gt;Dólar Americano&lt;/USDT&gt;<br />
      &lt;UYU&gt;Peso Uruguaio&lt;/UYU&gt;<br />
      &lt;UZS&gt;Som Uzbequistanês&lt;/UZS&gt;<br />
      &lt;VEF&gt;Bolívar Venezuelano&lt;/VEF&gt;<br />
      &lt;VND&gt;Dong Vietnamita&lt;/VND&gt;<br />
      &lt;VUV&gt;Vatu de Vanuatu&lt;/VUV&gt;<br />
      &lt;XAF&gt;Franco CFA Central&lt;/XAF&gt;<br />
      &lt;XAGG&gt;Prata&lt;/XAGG&gt;<br />
      &lt;XBR&gt;Brent Spot&lt;/XBR&gt;<br />
      &lt;XCD&gt;Dólar do Caribe Oriental&lt;/XCD&gt;<br />
      &lt;XOF&gt;Franco CFA Ocidental&lt;/XOF&gt;<br />
      &lt;XPF&gt;Franco CFP&lt;/XPF&gt;<br />
      &lt;XRP&gt;XRP&lt;/XRP&gt;<br />
      &lt;YER&gt;Riyal Iemenita&lt;/YER&gt;<br />
      &lt;ZAR&gt;Rand Sul-Africano&lt;/ZAR&gt;<br />
      &lt;ZMK&gt;Kwacha Zambiana&lt;/ZMK&gt;<br />
      &lt;ZWL&gt;Dólar Zimbabuense&lt;/ZWL&gt;<br />
      &lt;XAU&gt;Ouro&lt;/ZWL&gt;<br />
    </p>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Conversor",
  data() {
    return {
      A: "",
      B: "",
      defaultA: "USD",
      defaultB: "BRL",
      A_value: 0,
      B_value: 0,
    };
  },
  methods: {
    convert() {
      let url = `https://economia.awesomeapi.com.br/last/${this.A}-${this.B}`;
      fetch(url)
        .then((res) => res.json())
        .then((data) => {
          let conversionRate = parseFloat(data[`${this.A}${this.B}`].bid);
          this.B_value = this.A_value * conversionRate;
        })
        .catch((error) => {
          console.error("An error ocurred:", error);
        });
    },
  },
};
</script>

<style scoped>
.conversor {
  min-height: 100vh;
  width: 100vw;
  background-color: rgb(70, 70, 70);
  font-size: 2.5rem;
}

.conversor h2 {
  margin-bottom: 10px;
}

.from-to {
  padding-top: 10px;
  display: flex;
  justify-content: center;
}

.from-to label {
  padding-left: 10px;
  padding-right: 10px;
}

.from-to input {
  padding: 10px;
  border-radius: 20px;
  border: none;
}

.conversor .button {
  padding: 10px 20px;
  border-radius: 20px;
  border: none;
}

.conversor .currency {
  font-size: 1rem;
}
</style>
