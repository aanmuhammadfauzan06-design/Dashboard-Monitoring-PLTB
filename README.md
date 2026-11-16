# PLTB Trainer Monitoring V13

## MQTT realtime integration

Dashboard sudah terintegrasi dengan demo ESP32 MQTT yang sebelumnya berhasil.

- Broker WebSocket browser: `wss://broker.hivemq.com:8884/mqtt`
- MQTT topic: `pltb/demo/esp32-001`
- Payload: `wind_speed`, `gen_voltage`, `gen_current`, `gen_power`, `out_voltage`, `out_current`, `out_power`, `efficiency`
- Library browser: MQTT.js dari `https://unpkg.com/mqtt/dist/mqtt.min.js`

Saat MQTT tersambung, simulasi dashboard berhenti dan data ESP32 menjadi sumber realtime. Jika MQTT belum tersambung, simulasi tetap berjalan sebagai fallback.

## Jalankan

Gunakan VS Code + Live Server atau hosting HTTPS. Jangan mengubah topic jika masih memakai firmware demo.

## File

- `index.html` — dashboard V13
- `polines-logo.png` — logo Polines
- `esp32_mqtt_demo.ino` — firmware demo ESP32 yang sudah cocok dengan topic
- `mqtt_browser_demo.html` — subscriber MQTT demo sederhana


## V14 MQTT data freshness
The dashboard now marks MQTT as OFFLINE when no MQTT data packet is received for 5 seconds, even if the WebSocket broker connection remains open.
