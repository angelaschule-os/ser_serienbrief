# Erstellung Elternbrief für die Elternvertreter

```shell
pdflatex elternbrief.tex
```

## Testdaten erstellen

Testdaten erstellen mittels <https://www.mockaroo.com/>.

Konfiguration:
- Nachname - Last name
- Vorname - First name
- mw - Gender (abbrev): `if this == 'M' then 'm' else 'w' end`
- Account - Username: `concat(lower(field('Vorname')), ".", lower(field('Nachname')))`
- Passwort - Password

## Erstellung CSV-Datei für den Serienbrief

### Schritt 1) Daten-Export aus DaNiS

1) DaNiS > Bericht > Berichte > Daten-Export > GremienSerienbriefdatei
2) Dann wie gewohnt für das Schuljahr Sek I und Sek II und darin alle Gruppen auswählen. OK
3) Im Auswahlfenster "Schulelternrat" auswählen. OK
4) Bericht als CSV speichern (UTF8 / ";")
5) CSV-Datei nachbereiten (Es kommt nur auf die Spalten "Mitglied1Vorname" und "Mitglied1Nachname" an.
6) Doppelte Einträge löschen
7) "Dr.", "Prof." usw. löschen
8) Leerzeichen bei Bindestrichen bereinigen
9) CSV in IServ über das Import-Modul importieren (siehe Schritt 2)

### Schritt 2) CSV-Datei in IServ über das Import-Modul importieren

TODO

### Schritt 3) CSV-Datei der neuen Accounts nachbearbeiten

Das Import-Modul speichert die Daten der neu hinzugefügten Accounts in einer Datei nach dem Schema

`Import-SER-<YYYY-MM-DD-hh-mm-ss>-Hinzugefügt.csv`

im Home-Verzeichnis des Administrators, der den Import angestoßen hatte.

Dieser Datei muss nun eine Spalte "mw" hinzugefügt werden mit den Abkürzungen "m" für männlich (und "w" für weiblich). 

TODO: 3. Form?

Die ergänzte Datei muss unter dem Namen `ser_neu.csv` im Verzeichnis mit der TeX-Datei abgespeichert werden.
