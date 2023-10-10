#!/bin/bash

# Function to generate a random number between min and max (inclusive)
generate_random_number() {
    local min="$1"
    local max="$2"
    echo $((RANDOM % (max - min + 1) + min))
}

# Function to generate an array of random numbers
generate_random_numbers() {
    local n="$1"
    local min="$2"
    local max="$3"
    local numbers=()

    for ((i = 0; i < n; i++)); do
        numbers+=($(generate_random_number "$min" "$max"))
    done

    echo "${numbers[*]}"
}

# Default values
n=4
min=23
max=322
op="+"

# Check if there are command-line arguments and update values if provided
if [ "$#" -ge 1 ]; then
    n="$1"
fi

if [ "$#" -ge 2 ]; then
    min="$2"
fi

if [ "$#" -ge 3 ]; then
    max="$3"
fi

if [ "$#" -ge 4 ]; then
    op="$4"
fi

# Generate random numbers
random_numbers=($(generate_random_numbers "$n" "$min" "$max"))

# Combine random numbers into a string separated by the specified operator
result=$(IFS=$op; echo "${random_numbers[*]}")

# Display the result
echo "Random numbers in the same line separated by commas: $result"
