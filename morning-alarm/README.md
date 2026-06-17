# Morning Alarm

Sveglia forzata con Home Assistant: l'unico modo per fermarla è alzarsi e aprire la porta della veranda.

## Come funziona

```
Ore 08:00 (configurabile)
    └─ [se Italo è a casa]
        └─ Attiva flag "Morning Alarm Italo" → ON
        └─ Manda notifica iPhone

Ogni minuto
    └─ [se "Morning Alarm Italo" = ON]
        └─ Manda notifica CRITICA su iPhone
           (suona anche con telefono in silenzioso)

Porta veranda aperta
    └─ [se "Morning Alarm Italo" = ON]
        └─ Disattiva flag → OFF
        └─ Manda notifica: "Giorno iniziato"
```

## File

| File | Contenuto |
|------|-----------|
| `morning_alarm_start.yaml` | Automazione 1 — attiva la sveglia all'orario configurato |
| `morning_alarm_ring.yaml` | Automazione 2 — suona ogni minuto finché il flag è ON |
| `morning_alarm_stop.yaml` | Automazione 3 — spegne tutto all'apertura della porta |
| `helpers.yaml` | Helper: input_datetime + input_boolean |

## Hardware richiesto

- **Tapo T110** — sensore porta/finestra sulla porta della veranda
- **iPhone** con Home Assistant Companion App installata
- Presence detection configurata (zone `home` via GPS iPhone)

## Helper

| Entity | Tipo | Scopo |
|--------|------|-------|
| `input_datetime.morning_alarm_time` | input_datetime (solo ora) | Orario della sveglia — modificabile dall'app senza toccare il codice |
| `input_boolean.morning_alarm_italo` | input_boolean | Flag che connette le 3 automazioni — ON = sveglia attiva |

## Adatta al tuo setup

Prima di importare, modifica:

- `binary_sensor.veranda_door_sensor_porta` → entity ID del tuo sensore porta
- `notify.mobile_app_iphone_di_italo` → notify del tuo telefono
- `person.italo_guerrieri` → la tua person entity

## Video

TikTok: [@guerital92](https://www.tiktok.com/@guerital92)
