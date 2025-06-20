🔧 TP Arduino – Contrôle d'un moteur DC avec L298N et PWM

Ce projet consiste à contrôler la vitesse d’un **moteur à courant continu** à l’aide d’un module **L298N** et d’une carte **Arduino UNO**, tout en observant le signal **PWM** généré via un **oscilloscope**.

## 🎯 Objectif

- Contrôler la vitesse du moteur en modulant le rapport cyclique du signal PWM.
- Visualiser le signal PWM avec un oscilloscope pour en valider la forme et la fréquence.

## 🧰 Matériel utilisé

- 1x Arduino UNO  
- 1x Module double pont en H L298N  
- 1x Moteur à courant continu (DC)  
- 1x Alimentation externe 12V  
- 1x Oscilloscope numérique  
- Câbles de connexion  
- 1x Ordinateur avec l’IDE Arduino  

## ⚙️ Schéma de câblage

- **D8** → IN1 (L298N)  
- **D9** → IN2 (L298N)  
- **D5 (PWM)** → ENA (L298N)  
- **GND Arduino** ↔ **GND L298N + GND Alim**  
- Moteur connecté à OUT1/OUT2 du L298N  
- Alimentation 12V sur le bornier `12V` du L298N  

## 💻 Code Arduino

```cpp
const int in1 = 8;
const int in2 = 9;
const int ena = 5;

void setup() {
  pinMode(in1, OUTPUT);
  pinMode(in2, OUTPUT);
  pinMode(ena, OUTPUT);

  digitalWrite(in1, HIGH);
  digitalWrite(in2, LOW);
  analogWrite(ena, 127); // 50% du cycle PWM
}

void loop() {
  // Signal stable pour l’oscilloscope
}

```
##📈 Observation à l’oscilloscope
Sonde branchée sur la broche D5 (ENA)

GND oscilloscope connecté au GND Arduino

Signal carré visible (~490 Hz) avec un rapport cyclique de 50%

✅ Résultats
Le moteur tourne à mi-vitesse.

Le signal PWM est clairement observable sur l’oscilloscope.

Le test confirme le bon fonctionnement du pilotage via PWM.

📎 Rapport complet
📄 Télécharger le rapport PDF

Réalisé par :
Devran Sayilir
Alexis Cantaloube
Pierre Tavergne
