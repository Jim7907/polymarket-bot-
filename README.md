version: "3.9"
services:
  bot:
    build: .
    image: polymarket-weather-bot:latest
    container_name: polymarket-bot
    restart: unless-stopped
    ports:
      - "3001:3001"
    env_file: .env
    volumes:
      - ./logs:/app/logs
    logging:
      driver: json-file
      options:
        max-size: "10m"
        max-file: "3"
