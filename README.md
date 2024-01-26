# trackmap

## Usage

```
GET /?timeline=<payload>
```

where payload is a JSON base64-encoded string that accepts a list of objects that must contain:

- `coords`, [lat, lon] (optional)
- `name`, place name (optional, will be used for geocoding if `coords` is not set)
- `date`, timestamp

## Example with name geocoding

```bash
echo -n '[
  {"date": "2024-1-1", "name": "BUENOS AIRES, ARGENTINA"},
  {"date": "2024-1-2", "name": "CHAD"},
  {"date": "2024-1-3", "name": "COLOMBO, SRI LANKA"},
  {"date": "2024-1-4", "name": "KYOTO, JAPAN"}
]' | base64
WwogIHsiZGF0ZSI6ICIyMDI0LTEtMSIsICJuYW1lIjogIkJVRU5PUyBBSVJFUywgQVJHRU5USU5BIn0sCiAgeyJkYXRlIjogIjIwMjQtMS0yIiwgIm5hbWUiOiAiQ0hBRCJ9LAogIHsiZGF0ZSI6ICIyMDI0LTEtMyIsICJuYW1lIjogIkNPTE9NQk8sIFNSSSBMQU5LQSJ9LAogIHsiZGF0ZSI6ICIyMDI0LTEtNCIsICJuYW1lIjogIktZT1RPLCBKQVBBTiJ9Cl0=
```

https://trackmap.vercel.app/?timeline=WwogIHsiZGF0ZSI6ICIyMDI0LTEtMSIsICJuYW1lIjogIkJVRU5PUyBBSVJFUywgQVJHRU5USU5BIn0sCiAgeyJkYXRlIjogIjIwMjQtMS0yIiwgIm5hbWUiOiAiQ0hBRCJ9LAogIHsiZGF0ZSI6ICIyMDI0LTEtMyIsICJuYW1lIjogIkNPTE9NQk8sIFNSSSBMQU5LQSJ9LAogIHsiZGF0ZSI6ICIyMDI0LTEtNCIsICJuYW1lIjogIktZT1RPLCBKQVBBTiJ9Cl0=

## Example with coords

```bash
echo -n '[
  {"date": "2024-1-1", "coords": [-34.61, -58.38]},
  {"date": "2024-1-2", "coords": [12.11, 15.03]},
  {"date": "2024-1-3", "coords": [6.93, 79.85]},
  {"date": "2024-1-4", "coords": [35.01, 135.76]}
]' | base64
WwogIHsiZGF0ZSI6ICIyMDI0LTEtMSIsICJjb29yZHMiOiBbLTM0LjYxLCAtNTguMzhdfSwKICB7ImRhdGUiOiAiMjAyNC0xLTIiLCAiY29vcmRzIjogWzEyLjExLCAxNS4wM119LAogIHsiZGF0ZSI6ICIyMDI0LTEtMyIsICJjb29yZHMiOiBbNi45MywgNzkuODVdfSwKICB7ImRhdGUiOiAiMjAyNC0xLTQiLCAiY29vcmRzIjogWzM1LjAxLCAxMzUuNzZdfQpd
```

https://trackmap.vercel.app/?timeline=WwogIHsiZGF0ZSI6ICIyMDI0LTEtMSIsICJjb29yZHMiOiBbLTM0LjYxLCAtNTguMzhdfSwKICB7ImRhdGUiOiAiMjAyNC0xLTIiLCAiY29vcmRzIjogWzEyLjExLCAxNS4wM119LAogIHsiZGF0ZSI6ICIyMDI0LTEtMyIsICJjb29yZHMiOiBbNi45MywgNzkuODVdfSwKICB7ImRhdGUiOiAiMjAyNC0xLTQiLCAiY29vcmRzIjogWzM1LjAxLCAxMzUuNzZdfQpd

