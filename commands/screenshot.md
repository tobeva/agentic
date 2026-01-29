---
allowed-tools: Bash(make screenshot*), Read(/tmp/screenshot*)
---

# Screenshot

Take a screenshot of the Orson web app using `make screenshot`.

## Arguments: $ARGUMENTS

If arguments are provided, interpret them as a natural language request and build the appropriate URL. Examples:
- `/screenshot Tarantino` → `d=138`
- `/screenshot Fincher vs Spielberg` → `d=7467,488`
- `/screenshot Brad Pitt` → `a=287`
- `/screenshot Scorsese with years` → `d=1032&years=1`
- `/screenshot Spielberg starting at 1990` → `d=488&years=1&sy=1990`

## URL Parameters

| Param | Description | Example |
|-------|-------------|---------|
| `d` | Director IDs (comma-separated) | `d=578` (Ridley Scott), `d=138,7467` (Tarantino & Fincher) |
| `a` | Actor IDs (comma-separated) | `a=287,500` (Brad Pitt & Tom Cruise) |
| `w` | Writer IDs (comma-separated) | `w=1234` |
| `movie` | Selected movie ID | `movie=65754` |
| `years` | Show year labels | `years=1` |
| `titles` | Show movie titles | `titles=1` |
| `debug` | Show debug overlay | `debug=1` |
| `sy` | Scroll to year | `sy=1990` |

## Common Director IDs

- 578 = Ridley Scott
- 138 = Quentin Tarantino
- 7467 = David Fincher
- 488 = Steven Spielberg
- 1032 = Martin Scorsese
- 1776 = Francis Ford Coppola
- 240 = Stanley Kubrick
- 7119 = Paul Thomas Anderson
- 525 = Christopher Nolan

## Usage

```bash
make screenshot URL="d=578&years=1"
make screenshot URL="d=138,7467" OUT=/tmp/comparison.png
```

The output defaults to `/tmp/screenshot-<port>.png`.

## Instructions

1. Run `make screenshot` with the URL params
2. Use the Read tool to view the resulting PNG at `/tmp/screenshot-*.png`
3. If it fails, ensure the dev server is running (`make serve`)
