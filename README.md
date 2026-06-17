# home-assistant-automations

Raccolta delle mie automazioni [Home Assistant](https://www.home-assistant.io/).

## Struttura

Ogni cartella contiene un gruppo di automazioni correlate con:
- `README.md` — descrizione, logica, prerequisiti
- File `.yaml` pronti per l'importazione
- `helpers.yaml` — helper necessari (input_boolean, input_datetime, ecc.)

## Automazioni

| Cartella | Descrizione | Complessità |
|----------|-------------|-------------|
| [morning-alarm](./morning-alarm/) | Sveglia forzata via sensore porta — suona ogni minuto finché non apri la veranda | ⭐⭐ |

## Requisiti generali

- Home Assistant OS / Supervised / Core
- iOS Companion App (per notifiche critiche)
- Tapo T110 — sensore porta/finestra
- Presence detection via iPhone (zone `home`)

## Come importare

1. Copia il contenuto del file `.yaml`
2. HA → **Impostazioni → Automazioni → ⋮ → Importa da YAML**
3. Adatta gli entity ID al tuo setup

## Autore

Italo Guerrieri · [@guerital92](https://www.tiktok.com/@guerital92)
