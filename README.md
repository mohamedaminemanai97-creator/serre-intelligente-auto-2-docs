# Serre intelligente autonome (ESP32 + MicroPython)

[![Wokwi](https://img.shields.io/badge/Simulate-Wokwi-00a58f?logo=wokwi)](https://wokwi.com/projects/440650914275907585)
[![MicroPython](https://img.shields.io/badge/MicroPython-ESP32-2c3e50?logo=micropython)](https://micropython.org/)
[![Licence](https://img.shields.io/badge/Licence-Éducatif-blue)](#licence)

Serre connectée qui surveille et pilote automatiquement l’arrosage, l’éclairage et la ventilation en fonction des capteurs (DHT22, humidité du sol, luminosité LDR) et du niveau d’eau (HC‑SR04), avec affichage sur OLED SSD1306.

Lien Wokwi (simulation) : https://wokwi.com/projects/440650914275907585

## Démonstration

<div>
  <img src="serre-demo-01.jfif" alt="Serre démo 01" width="32%" />
  <img src="serre-demo-02.jfif" alt="Serre démo 02" width="32%" />
  <img src="serre-demo-03.jfif" alt="Serre démo 03" width="32%" />
</div>
<div>
  <img src="serre-demo-04.jfif" alt="Serre démo 04" width="32%" />
  <img src="serre-demo-05.jfif" alt="Serre démo 05" width="32%" />
  <img src="serre-demo-06.jfif" alt="Serre démo 06" width="32%" />
</div>

## Matériel
- ESP32 DevKit C V4
- DHT22 (température et humidité de l’air)
- Potentiomètre simulant l’humidité du sol (ADC sur GPIO14)
- LDR (luminosité sur GPIO33)
- Servo moteur (GPIO18)
- Buzzer (GPIO17)
- Écran OLED SSD1306 I2C (SDA=GPIO23, SCL=GPIO22)
- Module ultrason HC‑SR04 (TRIG=GPIO26, ECHO=GPIO5)

## Schéma & Simulation
- Schéma de câblage : voir `diagram.json` (export Wokwi)
- Simuler ce projet : https://wokwi.com/projects/440650914275907585 (voir aussi `wokwi-project.txt`)

## Fonctionnalités
- Lecture des capteurs (température, humidité de l’air, humidité du sol, luminosité, niveau d’eau)
- Pilotage de la pompe, lampe et ventilation (servo) selon des seuils
- Alerte buzzer lorsque le niveau d’eau est critique
- Affichage des états et mesures sur l’écran OLED

## Seuils utilisés
- Humidité du sol : SEUIL_SOL = 30%
- Luminosité : SEUIL_LUMI = 500 (ADC)
- Température : SEUIL_TEMP = 28°C
- Humidité de l’air : SEUIL_HUM_AIR = 80%
- Niveau d’eau critique : SEUIL_EAU_CRIT = 10%

## Fichiers
- `main.py` : boucle principale et logique de contrôle
- `ssd1306.py` : driver OLED
- `hscr04.py` : utilitaires HC‑SR04
- `diagram.json` : schéma de câblage Wokwi
- `wokwi-project.txt` : source/lien Wokwi

## Déploiement (ESP32 + MicroPython)
1. Flasher MicroPython sur l’ESP32.
2. Copier `main.py`, `ssd1306.py`, `hscr04.py` sur la carte (via Thonny/mpremote).
3. Redémarrer la carte : `main.py` s’exécute automatiquement.

## Licence
Projet éducatif publié par Mohamed Amine Manai.