# mosquitto_dockercompose


version: '3.8'

services:
  mosquitto:
    image: eclipse-mosquitto:2.0
    container_name: mosquitto_broker
    ports:
      - "1883:1883"   # MQTT Port
      - "9001:9001"   # WebSocket Port (optional)
    volumes:
      - ./config:/mosquitto/config
      - ./data:/mosquitto/data
      - ./log:/mosquitto/log






persistence true
persistence_location /mosquitto/data/

log_dest file /mosquitto/log/mosquitto.log

listener 1883
allow_anonymous true

listener 9001
protocol websockets
