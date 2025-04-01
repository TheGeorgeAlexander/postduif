# Postduif
Postduif is een programma om bestanden te delen.

## Hoe het werkt

### Voor de gebruiker
Neem aan dat je persoon **A** en persoon **B** hebt.
- **A** doet `postduif ontvang`
  - **A** krijgt een koppelode te zien
- **B** doet `postduif stuur`
  - **B** vult koppelcode van **A** in
  - **B** kiest het bestand om te versturen
- **A** krijgt te zien dat **B** wilt versturen
- **A** accepteert de verbinding
- **A** kiest een locatie om het bestand in op te slaan
- Bestand wordt verstuurd
- `postduif` sluit af bij **B**


### Op de achtergrond
Neem aan dat je persoon **A** en persoon **B** hebt.
- **A** doet `postduif ontvang`
  - **A** krijgt een koppelode te zien
- **B** doet `postduif stuur`
  - **B** vult koppelcode van **A** in
  - **B** kiest het bestand om te versturen
- *B-client maakt TCP connectie met A-client en verstuurt een request met de naam en de grootte van het bestand, en een public-key voor encryptie*
- **A** krijgt te zien dat **B** wilt versturen
- **A** accepteert de verbinding
- **A** kiest een locatie om het bestand in op te slaan
- *A-client stuurt response terug met shared key voor encryptie*
- *B-client comprimeert het bestand*
- *B-client versleutelt het gecomprimeerde bestand*
- *B-client stuurt het bestand op*
- Bestand wordt verstuurd
- *A-client ontvangt het bestand*
- *A-client ontsleutelt het bestand*
- *A-client decromprimeert het bestand*
- `postduif` sluit af bij **B**