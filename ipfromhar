#!/bin/bash

while getopts "i:o:" opt; do
  case $opt in
    i)
      input_file=$OPTARG
      ;;
    o)
      output_file=$OPTARG
      ;;
    \?)
      echo "Invalid option: -$OPTARG" >&2
      exit 1
      ;;
  esac
done

if [ -z "$input_file" ] || [ -z "$output_file" ]; then
  echo "Usage: $0 -i <input_file> -o <output_file>"
  exit 1
fi

while IFS= read -r domain; do
    host -t A "$domain" | awk '{print $NF}' | sort | uniq
done < <(cat "$input_file" | jq '.log.entries[].request.url' -r | sed 's|^.*//||' | awk -F/ '{print $1}' | sort | uniq) | sort -u > "$output_file"

echo "IP addresses extracted and saved to $output_file"
