# QR code — Tenuta Baroni Campanino

I QR code in questa cartella puntano alla pagina multilink del progetto:

```
https://thomas-neo-anderson.github.io/campanino-links/
```

| File | Uso |
|---|---|
| `qr-instagram.png` | 1080×1080, grafica completa con logo e colori della Tenuta — pronto per post o storia Instagram |
| `qr-campanino.png` | 1960×1960, solo QR su fondo crema — per stampa, menù, vetrina, biglietti da visita |
| `qr-campanino.svg` | vettoriale, scalabile a qualsiasi dimensione senza perdita di qualità |

Correzione d'errore livello H: il codice resta leggibile anche con una parte
rovinata o coperta.

## Se cambia l'indirizzo della pagina

I QR sono statici: rigenerarli con

```bash
pip install segno
python3 -c "import segno; segno.make('NUOVO_URL', error='h').save('qr/qr-campanino.svg', scale=10, border=4, dark='#23301f', light='#f5f0e4')"
```

## Pubblicazione della pagina

L'indirizzo sopra funziona con GitHub Pages attivo su questo repository
(Settings → Pages → Source: `main`, cartella `/root`).
