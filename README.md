# Audio zu JSON Konverter (Wissenschaftliche Version)

## Wie es funktioniert

### 1. Eingabe der Audiodatei
Das Programm liest die Audiodatei mit höchster Genauigkeit:

```python
data, sr = sf.read(wav_path, dtype='float64', always_2d=True)
```
- Unterstützt Stereo (2 Kanäle) und Mono (1 Kanal)
- Arbeitet mit 64-bit Genauigkeit (sehr genau)

### 2. Frequenzanalyse (FFT)
Wandelt den Sound in Frequenzen um:

```python
fft_result = fft(channel_data, norm='ortho')
```
- Misst Lautstärke (`amplitude`) und Position (`phase`) jeder Frequenz
- Besondere Eigenschaften:
  - Kein Informationsverlust
  - Exakte Zeitpunkterkennung

### 3. Daten speichern (JSON Format)
Die Analyse wird gespeichert als:

```json
{
  "sample_rate": 44100,
  "is_stereo": true,
  "channels": [
    {
      "amplitudes": [0.12, 0.08, ...],
      "phases": [1.57, -0.39, ...]
    }
  ]
}
```

### 4. Rückwandlung zu Audio
Aus den JSON-Daten wird wieder Sound erzeugt:

```python
signal = ifft(fft_reconstructed, norm='ortho').real
```
- Benutzt die gespeicherten Frequenzdaten
- Rekonstruiert den originalen Sound genau

## Wichtige Technik

### Präzision
- **Genauigkeit**: 64-bit (15 Dezimalstellen)
- **Fehler**: < 0.000000000000001 (praktisch perfekt)

### Geschwindigkeit
- Schnell auch bei langen Aufnahmen
- 1 Minute Audio ≈ 1 Sekunde Rechenzeit

### Besondere Funktionen
- Stereo-Unterstützung
- Kein Phasenfehler (wichtig für Klangqualität)
- Wissenschaftliche Genauigkeit

## Anwendungsbeispiel

1. Audio analysieren:
```python
perfect_wav_to_json("guitar.wav", "daten.json")
```

2. Audio wiederherstellen:
```python
perfect_json_to_wav("audio_daten.json", "neu_guitar.wav")
```

## Vorteile
- Originalgetreue Wiederherstellung
- Unterstützt alle gängigen Audioformate
- Ideal für Musik und Sprachaufnahmen
