# ESPHome Guition 3.5" Display - LVGL Projekt

ESPHome-Konfiguration für ein Guition ESP32-S3 3.5" Display (480x320) mit LVGL.

## Features

### 💡 Lampenseite (Seite 1)
- Alle Lichter Gruppenschalter
- Stehlampe Bibi
- Garderobe Licht
- Wohnzimmerschrank
- Esszimmer Licht (Gruppe)
- Küchen Unterlicht
- Flur Licht
- Licht Aktenschrank Markus
- Bibis Ecke Licht

### 🌡️ Heizungsseite (Seite 2)
- Wohnzimmer Heizung
- Büro Markus Heizung
- Schlafzimmer Heizung
- Temperaturanzeige
- Solltemperatur-Steuerung
- Batteriestatus

### ☁️ Wetterseite (Seite 3)
- Aktuelles Wetter für Freudenstadt
- Temperatur, Luftfeuchtigkeit
- Wetterzustand mit Icon
- Windgeschwindigkeit
- Niederschlagswahrscheinlichkeit
- Vorhersage für morgen

## Hardware

- **Display**: Guition ESP32-S3 3.5" (JC3248W535)
- **Auflösung**: 480x320 Pixel
- **Controller**: ESP32-S3
- **Framework**: ESP-IDF

## Installation

1. **secrets.yaml erstellen**:
```yaml
wifi_ssid: "DeinWLAN"
wifi_password: "DeinPasswort"
api_encryption_key: "dein-32-zeichen-key"
ota_password: "dein-ota-password"
```

2. **Kompilieren und Flashen**:
```bash
esphome run guition-display.yaml
```

3. **OTA Updates**:
Nach dem ersten Flash per USB können alle weiteren Updates Over-The-Air erfolgen.

## Struktur

```
.
├── guition-display.yaml      # Hauptkonfiguration
├── common.yaml              # Gemeinsame Einstellungen
├── secrets.yaml             # WLAN & API Secrets (nicht im Repo)
├── pages/
│   ├── lights.yaml          # Lampenseite
│   ├── heating.yaml         # Heizungsseite
│   └── weather.yaml         # Wetterseite
├── devices/
│   └── JC3248W535.yaml      # Display Hardware-Config
└── layouts/
    └── 480x320.yaml         # Layout-Definitionen
```

## Navigation

Swipe links/rechts um zwischen den Seiten zu wechseln:
- Seite 1: Lampen
- Seite 2: Heizung
- Seite 3: Wetter

## Anpassungen

Alle Entity-IDs sind in den jeweiligen Page-Dateien definiert. Passe sie an deine Home Assistant Konfiguration an.

## Home Assistant Integration

Das Display wird automatisch in Home Assistant erkannt und bietet:
- Light-Entities für Backlight-Steuerung
- Sensor-Entities für WLAN-Status
- Switch-Entity für Neustart

## Lizenz

MIT License - Frei verwendbar

## Credits

Erstellt für Home Assistant + ESPHome mit LVGL