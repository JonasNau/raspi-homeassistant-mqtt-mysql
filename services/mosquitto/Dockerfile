# Use the eclipse-mosquitto image
FROM eclipse-mosquitto

# Set the working directory inside the container
WORKDIR /mosquitto

# Copy the username_passwords.txt file to the working directory inside the container
COPY ./username_passwords.txt /mosquitto/credentials/username_passwords.txt

# Run the mosquitto_passwd command to create the username_passwords_hashed.txt file
RUN mosquitto_passwd -U /mosquitto/credentials/username_passwords.txt

RUN chmod 0700 /mosquitto/credentials/username_passwords.txt

# Expose port 1883 for MQTT and port 9001 for WebSockets MQTT Bridge
EXPOSE 1883 9001

# Start the mosquitto service
CMD ["mosquitto", "-c", "/mosquitto/config/mosquitto.conf"]
