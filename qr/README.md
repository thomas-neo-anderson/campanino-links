# QR code — Tenuta Baroni Campanino

Tutti i codici in questa cartella puntano alla pagina multilink:

```
https://thomas-neo-anderson.github.io/campanino-links/
```

| File | Uso |
|---|---|
| `locandina-A5.pdf` | **da portare in tipografia** — A5 (148×210 mm), una pagina, QR vettoriale |
| `locandina-A5.png` | stessa locandina a 300 dpi, per anteprima o stampa casalinga |
| `qr-instagram.png` | 1080×1080, grafica social |
| `qr-campanino.png` | 1640×1640, solo QR su fondo crema — menù, vetrina, biglietti da visita |
| `qr-campanino.svg` | vettoriale, scalabile senza perdita di qualità |
| `*.src.html` | sorgenti delle grafiche, per rigenerarle se cambia il testo |

Correzione d'errore livello H: il codice resta leggibile anche con una parte
rovinata o coperta.

## Pubblicazione

Il workflow `.github/workflows/pages.yml` pubblica la pagina su GitHub Pages a
ogni push su `main`, e attiva Pages da solo alla prima esecuzione. Non serve
toccare nessuna impostazione.

## Dominio personalizzato (facoltativo, per dopo)

Per servire la pagina su `link.campanino.it` invece che sull'indirizzo GitHub.
Il DNS di `campanino.it` è delegato a **OVH** (`ns19.ovh.net`, `dns19.ovh.net`),
quindi il record va creato dalla zona DNS nel pannello OVH:

| Tipo | Sottodominio | Destinazione |
|---|---|---|
| CNAME | `link` | `thomas-neo-anderson.github.io.` |

Quando il record risolve, aggiungere un file `CNAME` nella radice del repository
contenente `link.campanino.it` e impostare il dominio in Settings → Pages.

**I QR già stampati continuano a funzionare:** GitHub reindirizza
automaticamente l'indirizzo `github.io` verso il dominio personalizzato. Per
questo i codici puntano all'indirizzo GitHub e non al dominio: è quello che
regge in entrambi gli scenari.

## Se cambia l'indirizzo della pagina

I QR sono statici, vanno rigenerati:

```bash
pip install segno
python3 -c "import segno; segno.make('NUOVO_URL', error='h').save('qr/qr-campanino.svg', scale=10, border=4, dark='#23301f', light='#f5f0e4')"
```
