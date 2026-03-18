# Skripten

Diese Organisation soll in Zukunft meine den Schülern zur Verfügung gestellten Skripten aufnehmen. Ich möchte diese gerne als Jupyter Books publizieren. Entsprechend findte sich hier eine rudimentäre Anleitung.

## Erstellen eines Jupyter Book

Für die Anleitung zum erstellen eines Jupyter Book kann auf die 
[Anleitung](https://jupyterbook.org/en/stable/start/your-first-book.html)
verwiesen werden. 

## Publizieren des Inhaltes mit GitHub Pages

Die Beschreibung des Publikationsprozesses geht von folgender Dateistruktur aus:

```{txt}
|-.github/  
|   |-workflows  
|       |-deploy-book.yml  
|-docs/  
|   |-_build/  
|   |-content1/  
|   |   |-file.md  
|   |   |-file.md  
|   |-content2/  
|   |-.nojekyll  
|   |-_config.yml  
|   |-_toc.yml
|   |-intro.md
|   |-logo.png
|-.gitignore
|-.nojekyll
|README.md
```

Entsprechend werden die Inhalte aus dem Ordner docs publiziert. Nachdem
die Inhalte mit dem Befehl `jupyter-book build .` aus dem Ordner docs
heraus in HTML konvertiert worden sind, können Sie mit einem einfachen
`git push origin main` publiziert werden. Die durch das in 
`.github/workflows/deploy-book.yml` gesteuerte GitHub Action erledigt alle
für die Publikation erforderlichen Schritte. Der Inhalt des Files 
[deploy-book.yml](../sources/deploy-book.yml)
ist verlinkt.

Damit das funktioniert, muss das GitHub Repository folgendermassen
vorbereitet werden:

1. Aktivieren von GitHub Pages im Repository:
   * "Settings" → "Pages"
   * "GitHub Actions" als Quelle auswählen
2. Sicherstellen, dass die GitHub Actions die nötigen Berechtigungen haben:
   * "Settings" → "Actions" → "General" → "Workflow permissions"
   * Erforderliche Berechtigungen: pages: write, id-token: write, contents: write
3. Installation der erforderlichen Pakete (nur für lokale Entwicklung und Tests):
   * `pip install jupyter-book`
   * `pip install ghp-import` (optional, nur wenn Sie lokale Builds testen möchten)
4. Konfiguration der wichtigen Dateien:
   * `_config.yml`: Enthält alle Metainformationen zum Buch (Titel, Autor, etc.)
   * `_toc.yml`: Definiert die Struktur und Navigation des Buches
5. Hinzufügen der deploy-book.yml Datei zum Pfad `.github/workflows/`

Nach diesen Vorbereitungen werden Änderungen automatisch bei jedem Push
auf den main-Branch veröffentlicht. Die GitHub Action kümmert sich um
den Build und die Veröffentlichung - ein manueller Deploy ist nicht mehr
nötig.

Die effektiv erfoderlichen Arbeitsschritte sind:

1. `git add ./*`
2. `git commit`
3. `git push oritin main`



