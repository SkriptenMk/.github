# Skripten

Diese Organisation soll in Zukunft meine den Schülern zur Verfügung gestellten Skripten aufnehmen. Ich möchte diese Gerne als Jupyter Books publizieren. Entsprechend findte sich hier eine rudimentäre Anleitung.

## Erstellen eines Jupyter Book

Für die Anleitung zum erstellen eines Jupyter Book kann auf die 
[Anleitung](https://jupyterbook.org/en/stable/start/your-first-book.html)
verwiesen werden. 

## Puplizieren des Inhaltes mit GitHub Pages

Die Beschreibung des Publikationsprozesses geht von folgender Dateistruktur aus:

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

