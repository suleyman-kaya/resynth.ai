
# 🎧 Werkzeug zur Analyse und Resynthese von Audiofrequenzen (mit Halleffekt)

Dieses Jupyter-Notebook ist ein interaktives Werkzeug zur Analyse, Bearbeitung und Neusynthese von `.wav`-Audiodateien. Es erlaubt Ihnen, Frequenzkomponenten zu analysieren, zu modifizieren, zeitbasierte Effekte wie Hall anzuwenden und das bearbeitete Ergebnis als neue Datei zu exportieren.

## 🚀 Projektziel

Ziel dieses Projekts ist es:

- Grundlagen der digitalen Audio-Signalverarbeitung praxisnah zu vermitteln  
- Eine intuitive Umgebung zur Frequenzanalyse bereitzustellen  
- Benutzern die Möglichkeit zu geben, gezielt Frequenzen zu verändern  
- Hall-Effekte innerhalb eines ausgewählten Zeitbereichs zu simulieren  
- Eine editierte Audiodatei als `.wav` speichern zu können

## 🔧 Funktionen

| Funktion | Beschreibung |
|----------|--------------|
| 📤 WAV-Datei hochladen | Laden Sie eine `.wav`-Datei von Ihrem Gerät hoch |
| 📊 Fourier-Analyse | Analyse des Frequenzspektrums mittels FFT |
| 🎚 Frequenzbearbeitung | Änderung der Amplitude bestimmter Frequenzen |
| 🎛 Frequenzverschiebung | Frequenzen im Spektrum verschieben |
| 🕒 Zeitbereichs-Halleffekt | Reverb-Effekt zwischen zwei Zeitpunkten anwenden |
| 💾 Speichern / Rückgängig machen | Änderungen speichern oder zurücksetzen |
| 📥 Exportieren | Bearbeitete Datei als neue `.wav` exportieren |

## 🧰 Verwendete Technologien

- `numpy`: Numerische Berechnungen  
- `matplotlib`: Plot-Erstellung  
- `scipy.io.wavfile`: Lesen/Schreiben von WAV-Dateien  
- `scipy.fft`: Fourier-Transformation  
- `ipywidgets`: Interaktive Steuerelemente  
- `IPython.display`: Darstellung von UI-Komponenten  
- `scipy.signal`: Anwendung des Halleffekts

## 🧪 Bedienungsanleitung

1. **WAV-Datei hochladen**  
   Nutzen Sie die Upload-Funktion im ersten Abschnitt des Notebooks.

2. **Frequenzanalyse durchführen**  
   Das Skript analysiert automatisch das Spektrum der Datei per FFT.

3. **Frequenz auswählen und anpassen**  
   Geben Sie eine Ziel-Frequenz in das Eingabefeld ein und passen Sie deren Amplitude an.

4. **Halleffekt anwenden**  
   Wählen Sie einen Zeitbereich (z. B. 3–5 Sekunden) und wenden Sie den Effekt an.

5. **Änderungen speichern oder rückgängig machen**  
   Jede Bearbeitung kann gespeichert oder rückgängig gemacht werden.

6. **Als WAV-Datei exportieren**  
   Exportieren Sie das finale Ergebnis über die Export-Schaltfläche.

## 📁 Projektstruktur

Wichtige Funktionen im Notebook:

- `upload_wav()` → Datei-Upload  
- `analyze_audio()` → FFT-Analyse  
- `apply_reverb(start_time, end_time)` → Reverb-Effekt im Zeitbereich  
- `update_spectrum()` → Aktualisierung des Spektrums  
- `save_audio()` → Export als WAV

## 🎓 Zielgruppe

- Studierende in Elektrotechnik, Akustik, Audio Engineering  
- Einsteiger in digitale Signalverarbeitung (DSP)  
- Entwickler mit Interesse an Frequenzmanipulation und Audiosynthese  
- Lehrpersonen, die praktische Audioanalyse demonstrieren möchten

## 📝 Hinweise

- Stereo-Audiodateien werden automatisch in Mono umgewandelt.  
- Die Audiodaten werden auf `float32` normalisiert.  
- Das Notebook funktioniert optimal in Umgebungen wie JupyterLab oder Google Colab.

## 📤 Offline-Nutzung

Für die lokale Nutzung stellen Sie sicher, dass die benötigten Pakete installiert sind:

```bash
pip install numpy scipy matplotlib ipywidgets
```

## 📣 Mitwirken

Dieses Projekt ist Open Source. Beiträge zur Funktionserweiterung oder Fehlerbehebung sind herzlich willkommen!
