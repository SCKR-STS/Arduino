# Spletni učbenik: Arduino
![Arduino](./Slike/arduino.jpeg)
## 1. Uvod v Arduino in IoT
### 1.1 Kaj je Arduino
Arduino je odprtokodna platforma, ki omogoča enostaven razvoj elektronskih projektov. Sestavlja jo programska (Arduino IDE) in strojna oprema (različne razvojne plošče). Glavna prednost Arduina je njegova preprostost, cenovna dostopnost in velika skupnost uporabnikov, ki omogoča hitro učenje in razvoj.

Arduino temelji na mikrokontrolerjih podjetja Atmel (npr. ATmega328) in omogoča interakcijo z različnimi senzorji, aktuatorji in komunikacijskimi moduli. Z Arduinom lahko nadzorujemo osvetlitev, motorje, temperaturo in druge elektronske komponente, zaradi česar je zelo priljubljen v projektih pametnega doma, robotike in interneta stvari (IoT).

#### Primeri Arduino plošč:
- **Arduino Uno** – Najbolj priljubljena razvojna plošča, temelji na ATmega328P, ima 14 digitalnih vhodno/izhodnih pinov, 6 analognih vhodov in USB povezavo.
![UNO](./Slike/UNO.png)

- **Arduino Mega** – Zmogljivejša različica z več vhodi in izhodi, primerna za kompleksne projekte.
![MEGA](./Slike/MEGA.svg)

- **Arduino IoT** – Razvojna plošča, posebej zasnovana za internet stvari (IoT).
Vsebuje integrirano WiFi ali Bluetooth povezljivost ter podporo za varno povezovanje z oblačnimi storitvami.
Idealen za projekte, ki zahtevajo oddaljeni dostop in obdelavo podatkov v realnem času.

![nano](./Slike/nano.png)

- **Arduino Leonardo** – Ima integriran USB, kar omogoča simulacijo tipkovnice ali miške.
  
![leonardo](./Slike/leonardo.png)

- **Arduino Due** – Temelji na 32-bitnem ARM procesorju, primeren za naprednejše projekte.
  
![due](./Slike/due.jpeg)

- **Arduino MKR serija** – Plošče z integrirano WiFi/Bluetooth povezljivostjo, namenjene IoT aplikacijam.

![MKR](./Slike/MKR.png)

### 1.2 Osnovne komponente Arduino sistema
### 1.3 Kaj je IoT in kako se povezuje z Arduinom?
### 1.4 Priprava razvojnega okolja (Arduino IDE, knjižnice)

## 2. Osnove programiranja v Arduinu
### 2.1 Struktura programa (setup in loop)
### 2.2 Izpis na serijsko konzolo
### 2.3 Spremenljivke in podatkovni tipi
### 2.4 Osnovne operacije in izrazi

## 3. Nadzor vhodov in izhodov
### 3.1 Digitalni vhodi in izhodi (LED, gumbi)
### 3.2 Analogni vhodi in izhodi (senzorji, PWM)
### 3.3 Branje in zapis podatkov

## 4. Krmilne strukture v Arduino
### 4.1 Pogojni stavki (if, else)
### 4.2 Zanke (for, while, do-while)
### 4.3 Funkcije in modulacija kode

## 5. Obdelava podatkov in prikaz rezultatov
### 5.1 Osnovna obdelava podatkov (matematične operacije)
### 5.2 Pretvarjanje podatkovnih tipov
### 5.3 Shranjevanje podatkov (EEPROM, SD kartica)
### 5.4 Prikaz podatkov na LCD in OLED zaslonih

## 6. Senzorji in aktuatorji
### 6.1 Delo s temperaturnimi in vlažnostnimi senzorji
### 6.2 Uporaba ultrazvočnih senzorjev za merjenje razdalje
### 6.3 Servo motorji in motorni pogoni

## 7. Komunikacija z drugimi napravami
### 7.1 Serijska komunikacija (UART)
### 7.2 I2C in SPI protokoli
### 7.3 Pošiljanje podatkov med Arduinom in računalnikom

## 8. Povezovanje Arduina z internetom
### 8.1 Uporaba WiFi in Ethernet modulov (ESP8266, ESP32)
### 8.2 HTTP zahteve in uporaba API-jev
### 8.3 MQTT protokol za IoT projekte

## 9. Mobilne aplikacije in Arduino
### 9.1 Povezava Arduina s pametnimi telefoni (Bluetooth, WiFi)
### 9.2 Pošiljanje podatkov v oblak (Google Firebase, ThingSpeak)
### 9.3 Upravljanje Arduina preko mobilne aplikacije

## 10. Napredne IoT rešitve in projekti
### 10.1 Pametni dom (nadzor luči, temperature, varnosti)
### 10.2 IoT vremenska postaja
### 10.3 Oddaljeno upravljanje naprav prek spleta

## 11. Optimizacija in varnost v IoT
### 11.1 Varčevanje z energijo (sleep mode)
### 11.2 Osnove kibernetske varnosti v IoT napravah
### 11.3 Šifriranje podatkov in zaščita komunikacije

## 12. TEST

$A =$ <script modify="false" input="range" step="0.1" min="0.5" max="5" value="1" output="A">@input</script>,  
$f =$ <script modify="false" input="range" step="0.1" min="0.1" max="5" value="1" output="f">@input</script>,  
$ϕ =$ <script modify="false" input="range" step="0.1" min="-π" max="π" value="0" output="phi">@input</script>

<script modify="false" run-once style="display: inline-block; width: 100%">
"LIASCRIPT: ### $$f(x) = @input(`A`) \sin(@input(`f`) x + @input(`phi`))$$"
</script>

<script run-once style="display: inline-block; width: 100%">
function func(x) {
  return @input(`A`) * Math.sin(@input(`f`) * x + @input(`phi`));
}

function generateData() {
  let data = [];
  for (let i = -15; i <= 15; i += 0.1) {
    data.push([i, func(i)]);
  }
  return data;
}

let option = {
  grid: { top: 40, left: 50, right: 40, bottom: 50 },
  xAxis: {
    name: 'x',
    minorTick: { show: true },
    splitLine: { lineStyle: { color: '#999' } },
    minorSplitLine: { show: true, lineStyle: { color: '#ddd' } }
  },
  yAxis: {
    name: 'y', min: -5, max: 5,
    minorTick: { show: true },
    splitLine: { lineStyle: { color: '#999' } },
    minorSplitLine: { show: true, lineStyle: { color: '#ddd' } }
  },
  series: [
    {
      type: 'line',
      showSymbol: false,
      data: generateData()
    }
  ]
};

"HTML: <lia-chart option='" + JSON.stringify(option) + "'></lia-chart>"
</script>


## 13. TEST2

## Discrete Closed-Loop Control System with PID  
$$ G(z) = \frac{b_0 + b_1 z^{-1} + b_2 z^{-2}}{1 + a_1 z^{-1} + a_2 z^{-2}} $$  
$b_0 =$ <script modify="false" input="range" step="0.1" min="-2" max="2" value="0.5" output="b0">@input</script>,  
$b_1 =$ <script modify="false" input="range" step="0.1" min="-2" max="2" value="0.5" output="b1">@input</script>,  
$b_2 =$ <script modify="false" input="range" step="0.1" min="-2" max="2" value="0" output="b2">@input</script>,  
$a_1 =$ <script modify="false" input="range" step="0.1" min="-2" max="2" value="-1.2" output="a1">@input</script>,  
$a_2 =$ <script modify="false" input="range" step="0.1" min="-2" max="2" value="0.36" output="a2">@input</script>   
$K_p =$ <script modify="false" input="range" step="0.1" min="0" max="10" value="1" output="Kp">@input</script>,  
$K_i =$ <script modify="false" input="range" step="0.01" min="0" max="1" value="0.1" output="Ki">@input</script>,  
$K_d =$ <script modify="false" input="range" step="0.1" min="0" max="5" value="0" output="Kd">@input</script>   
<select output="signalType"><option value="step">Step</option><option value="ramp">Ramp</option><option value="sin">Sine</option></select>  
<script modify="false" run-once style="display: inline-block; width: 100%">"LIASCRIPT: ### $$ C(z) = K_p + \\frac{K_i}{1 - z^{-1}} + K_d (1 - z^{-1}) $$"</script>  
<script run-once style="display: inline-block; width: 100%">  
function pidController(z) { let Kp = @input(`Kp`); let Ki = @input(`Ki`); let Kd = @input(`Kd`); return Kp + (Ki / (1 - z**-1)) + Kd * (1 - z**-1); }  
function plantTransferFunction(z) { let b0 = @input(`b0`); let b1 = @input(`b1`); let b2 = @input(`b2`); let a1 = @input(`a1`); let a2 = @input(`a2`); return (b0 + b1 * z**-1 + b2 * z**-2) / (1 + a1 * z**-1 + a2 * z**-2); }  
function closedLoopResponse(z) { let C = pidController(z); let G = plantTransferFunction(z); return (C * G) / (1 + C * G); }  
function inputSignal(n) { let type = "@input(`signalType`)"; if (type === "step") return 1; if (type === "ramp") return n * 0.1; if (type === "sin") return Math.sin(n * 0.1); return 0; }  
function simulateResponse() { let dataInput = []; let dataOutput = []; let y = 0; for (let n = 0; n <= 100; n++) { let u = inputSignal(n); let H = closedLoopResponse(n); y = H * u; dataInput.push([n, u]); dataOutput.push([n, y]); } return { input: dataInput, output: dataOutput }; }  
let response = simulateResponse();  
let option = { title: { text: 'Closed-Loop System Response' }, grid: { top: 40, left: 50, right: 40, bottom: 50 }, xAxis: { name: 'Time (n)', type: 'category' }, yAxis: { name: 'Amplitude' }, legend: { data: ['Input Signal', 'Output Response'] }, series: [{ name: 'Input Signal', type: 'line', data: response.input }, { name: 'Output Response', type: 'line', data: response.output }] };  
"HTML: <lia-chart option='" + JSON.stringify(option) + "'></lia-chart>"  
</script>  
