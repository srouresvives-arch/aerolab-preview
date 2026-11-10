# AeroLab al navegador

Prototip experimental d'interfície per a JSBSim WebAssembly. Les simulacions es calculen localment al navegador. Inclou condicions inicials, vent constant, un canvi de controls, casos superposats, trajectòria 3D esquemàtica, telemetria i CSV. Els casos viuen només a la sessió actual.

## Prova local

A l'arrel del repositori: `cd web`, `npm ci`, `npm run prepare:web`, `npm test`, i després `python -m http.server 8000 -d public`. Obre http://127.0.0.1:8000/.

El procés de construcció copia la versió fixada `@0x62/jsbsim-wasm@1.2.4-beta.4` i els arxius XML d'exemple al directori web. El paquet SDK és MIT i inclou JSBSim sota LGPL-2.1; [origen i termes](https://github.com/0x62/jsbsim-wasm). Conserva els avisos i termes corresponents a l'hora de redistribuir-lo. El model Skywalker X8 d'Alexander Quessy prové de [Fixedwing-Airsim](https://github.com/AOS55/Fixedwing-Airsim/tree/master/x8); el seu fitxer indica GPL i també que no es pot vendre: cal aclarir les condicions abans de distribuir-lo comercialment.

## Límits

El model X8 és ALPHA, sense validació ni trim automàtic. El fitxer del motor es diu `electric800W.xml` però declara **8 W**, dada sense verificar. No s'ha validat el model contra un UAV real i no és apte per a decisions de vol. La trajectòria mostra una projecció local aproximada. La versió WASM publicada és beta i usa una versió diferent de JSBSim de la del prototip Python: cal validar la paritat de resultats més enllà del cas bàsic. No hi ha persistència, importació de models, editor complet ni Monte Carlo.
