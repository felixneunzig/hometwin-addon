# hometwin

Digitaler Zwilling der Wohnung für Home Assistant. Die App bringt den Editor als
Seite in der Seitenleiste mit, speichert die Projekte und veröffentlicht das
Szenenpaket für die Dashboard-Card.

## Bedienung

- Seitenleiste, „hometwin“: Editor. Lampen, Sensoren und Szenen setzen und
  zuordnen, Möbel verschieben, Licht berechnen.
- „Für Home Assistant“ im Editor: rechnet das Licht und veröffentlicht das
  Paket nach `/config/www/hometwin`. Die Card ist als Dashboard-Ressource
  eingetragen.
- Hochladen (Pfeil oben rechts im Editor): Möbelmodelle als GLB kommen in die
  Bibliothek und stehen dann bei jedem Möbel unter „Modell“ zur Wahl. Ein Scan
  der iPhone-App als Zip wird zum neuen Plan, gibt es den Plan schon, lassen
  sich nur die Raumumrisse übernehmen. Projektdateien (`.plan.json`, dazu
  passend `.twin.json`) werden zu einem Projekt.
- Card im Dashboard: `type: custom:hometwin-card`, `scene: /local/hometwin/<name>`.

## Erster Start

Die App bringt als Beispiel eine erfundene Testwohnung mit. Eigene Wohnungen
kommen als Scan der iPhone-App oder als Projektdateien über „Hochladen“ dazu.

## Daten

Projekte, Möbelmodelle und hochgeladene Scans liegen im Konfigurationsordner
der App (`/addon_configs/<Kennung>_hometwin`) und sind Teil jeder Sicherung. Die App
nimmt Anfragen nur über Home Assistant an, nicht direkt aus dem internen Netz.

Das Licht rechnet der Browser, in dem der Editor offen ist. Auf einem Mac geht
das schneller als auf einem iPad.
