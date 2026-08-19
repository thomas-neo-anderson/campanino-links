# QR code — Tenuta Baroni Campanino

I QR code in questa cartella puntano alla pagina multilink:

```
https://link.campanino.it/
```

| File | Uso |
|---|---|
| `qr-instagram.png` | 1080×1080, grafica completa con logo e colori della Tenuta — pronto per post o storia Instagram |
| `qr-campanino.png` | 1640×1640, solo QR su fondo crema — per stampa, menù, vetrina, biglietti da visita |
| `qr-campanino.svg` | vettoriale, scalabile a qualsiasi dimensione senza perdita di qualità |
| `locandina-A5.pdf` | **da portare in tipografia** — A5 (148×210 mm), una pagina, QR vettoriale |
| `locandina-A5.png` | stessa locandina a 300 dpi, per anteprima o stampa casalinga |

La locandina è il pezzo da tavolo per fine serata: *«Ti è piaciuta la serata?
Resta con noi.»* Il file PDF non ha abbondanza (bleed): se la tipografia la
chiede, va rigenerato con 3 mm per lato.

Correzione d'errore livello H: il codice resta leggibile anche con una parte
rovinata o coperta.

## Configurazione del dominio

Il file `CNAME` nella radice del repository dichiara il dominio personalizzato.
Perché funzioni servono due cose:

1. **DNS** — dal pannello di `campanino.it`, un record:

   | Tipo | Nome | Valore |
   |---|---|---|
   | CNAME | `link` | `thomas-neo-anderson.github.io.` |

2. **GitHub Pages** — Settings → Pages → Source: `main`, cartella `/root`;
   in *Custom domain* compare `link.campanino.it`. Quando il DNS si è
   propagato, spuntare **Enforce HTTPS**.

## Se cambia l'indirizzo della pagina

I QR sono statici: vanno rigenerati.

```bash
pip install segno
python3 -c "import segno; segno.make('NUOVO_URL', error='h').save('qr/qr-campanino.svg', scale=10, border=4, dark='#23301f', light='#f5f0e4')"
```
