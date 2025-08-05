#!/bin/bash

# URL to fetch Pikachu data
URL="https://pokeapi.co/api/v2/pokemon/pikachu"

# Output files
OUTPUT_FILE="data.json"
ERROR_FILE="errors.txt"

# Make the API request and capture HTTP status code
HTTP_RESPONSE=$(curl -s -w "%{http_code}" -o "$OUTPUT_FILE" "$URL")

# Check if HTTP status is 200 OK
if [ "$HTTP_RESPONSE" -ne 200 ]; then
    echo "Error: Failed to fetch data from $URL. HTTP status: $HTTP_RESPONSE" >> "$ERROR_FILE"
    # Remove incomplete or invalid data.json if any
    [ -f "$OUTPUT_FILE" ] && rm "$OUTPUT_FILE"
fi
