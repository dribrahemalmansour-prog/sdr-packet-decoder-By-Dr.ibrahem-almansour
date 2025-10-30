# SDR Packet Decoder (Python)

This tool enhances SDR receiver output by:
1. Cleaning noisy hexadecimal lines
2. Extracting full packets based on a simple frame format
3. Validating them (length + checksum)
4. Decoding the payload into text/JSON-like data

Designed to make message extraction repeatable and user-friendly.

## Packet format (example)
- Preamble: `AABB`
- 1 byte: payload length (in bytes)
- N bytes: payload
- 1 byte: checksum = (sum of payload bytes) % 256

Example:
`AA BB 05 48 65 6C 6C 6F 9F` → payload= "Hello"

## Install
```bash
pip install -r requirements.txt
```

## Run
```bash
python -m src.run --file samples/noisy_hex.txt
```
Dr. Ibrahem Almansour
