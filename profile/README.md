# Skripten

Diese Organisation soll in Zukunft meine den Schülern zur Verfügung gestellten Skripten aufnehmen. Ich möchte diese Gerne als Jupyter Books publizieren. Entsprechend findte sich hier eine rudimentäre Anleitung.

## Erstellen eines Jupyter Book

Für die Anleitung zum erstellen eines Jupyter Book kann auf die 
[Anleitung](https://jupyterbook.org/en/stable/start/your-first-book.html)
verwiesen werden. 

## Puplizieren des Inhaltes mit GitHub Pages

Die Beschreibung des Publikationsprozesses geht von folgender Dateistruktur aus:

```{txt}
|-.github/  
|   |-workflows  
|       |-deploy-book.yml  
|-docs/  
|   |-_build/  
|   |-conetnt1/  
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



