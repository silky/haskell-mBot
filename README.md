# MBot Bibliotheek


Om je robot te programmeren hebben we voor jullie een bibliotheek geïmplementeerd die draadloos instructies naar de robot stuurt. Op de robot zelf draait er een programma dat staat te wachten op instructies en deze één voor één uitvoert. Deze bibliotheek laat toe om de motors te sturen en de sensoren uit te lezen. Een sketch van de verschillende sensoren kan hieronder bekijken. 

## Connectie 
De eerste stap om de robot te programmeren is dus om eerst een connectie met de robot te maken. Dat doe je met de functie openMBot. Het type van deze functie is IO (Device) je zal deze dus enkel kunnen oproepen vanuit de IO monad. 

## Commandos 
Eens je een device hebt kan je gebruik maken van de functie sendCommand. Deze functie verwacht twee argumenten een Command en een Device. De MBot ondersteunt twee commando’s. Het eerste commando SetRBG dient om de RGB leds aan te schakelen. Om deze uit te schakelen kan je de drie kleuren op 0 zetten. Het tweede commando dient om de motors aan te schakelen. Merk op dat je MBot meteen zal beginnen rijden. Hij zal dus niet stoppen als je de motors daarna niet uitschakelt. Dat doe je door de motor snelheid op 0 te plaatsen. Als je het complement van de snelheid neemt zal de motor achterwaarts draaien (voorbeeld code kan je terugvinden in MBot.hs). Om de MBot te doen draaien schakel je één motor in terwijl de andere stilstaat.   

## Sensoren
Er zijn twee sensoren op de MBot die je kan uitlezen met respectievelijk readUltraSonic en readLineFollower. De readUltraSonic functie geeft een getal terug dat aangeeft hoever een object voor de sensor staat.  De line sensor bestaat uit twee sensoren die meten of de vloer eerder zwart of wit is. De  readLineFollower functie geeft een waarde van het type Line terug.  Deze waardes zijn ofwel  LEFTB, RIGHTB, BOTHB, BOTHW  dit geeft aan welke kleur de linker en rechter sensor uitleest.  
