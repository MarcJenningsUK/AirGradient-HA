# AirGradient-HA

This repo contains an adapted version of the base AirGradient sketch to allow a Home Assistant restful sensor to query the device.

## HA Configuration

```rest:
  - resource: http://<AirGradient-IP>:8080/
    scan_interval: 300
    sensor:
      - name: "AirGradient Temperature"
        value_template: "{{ value_json.tmp }}"
        unit_of_measurement: "°C"
        unique_id: ag1tmp
      - name: "AirGradient Humidity"
        value_template: "{{ value_json.hum }}"
        unit_of_measurement: "%"
        unique_id: ag1hum
      - name: "AirGradient CO2"
        value_template: "{{ value_json.co2 }}"
        unit_of_measurement: "pppm"
        unique_id: ag1co2
      - name: "AirGradient PM2"
        value_template: "{{ value_json.pm2 }}"
        unit_of_measurement: "μg/m³"
        unique_id: ag1ppm2
      - name: "AirGradient AQI"
        value_template: "{{ value_json.aqi }}"
        unique_id: ag1aqi
        unit_of_measurement: "aqi"
```
