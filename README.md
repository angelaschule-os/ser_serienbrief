# Erstellung Elternbrief für die Elternvertreter

```shell
pdflatex elternbrief.tex
```

## Testdaten erstellen

Testdaten erstellen mittels <https://www.mockaroo.com/>.

Konfiguration:
- Nachname - Last name
- Vorname - First name
- mw - Gender (abbrev) : `if this == 'M' then 'm' else 'w' end`
- Account - Username: `concat(lower(field('Vorname')), ".", lower(field('Nachname')))`
- Passwort - Password

## Export csv aus IServ

TODO
