# Provenienza delle immagini — Pendolo

**Nessuna immagine di questa cartella è una fotografia.** Sono tutti render
sintetici, generati con un modello text-to-image il 16 settembre 2026 per
popolare questo template: il prodotto "Pendolo" non esiste, e prezzi, specifiche
e disponibilità sono segnaposto dichiarati (vedi `PRODUCT.md` e il piede di
pagina).

Se vendi un prodotto vero, **sostituisci tutti i file qui sotto con le foto del
tuo**, mantenendo lo stesso nome e le stesse proporzioni: il markup non cambia.
Aggiorna poi questo file con la provenienza delle tue immagini — fotografo,
data, diritti — perché una pagina prodotto che non sa dire da dove vengono le
sue immagini non è finita.

| File | Misure | Peso | Sorgente | Dove si vede |
|---|---|---|---|---|
| `alluminio.webp` | 1400 × 912 | 37 KB | `_assets/v2/lamp-hero.png` | Prodotto, finitura alluminio naturale (prima schermata e blocco d'acquisto) |
| `nero.webp` | 1400 × 912 | 32 KB | `_assets/v2/lamp-black.png` | Prodotto, finitura nero anodizzato |
| `sabbia.webp` | 1400 × 912 | 38 KB | `_assets/v2/lamp-sand.png` | Prodotto, finitura sabbia anodizzato |
| `profilo.webp` | 1500 × 571 | 35 KB | `_assets/v2/lamp-side.png` | Sezione "Un contrappeso, non una molla": il braccio che percorre il suo arco |
| `contrappeso.webp` | 1300 × 775 | 83 KB | `_assets/v2/lamp-detail.png` | Stessa sezione, il dettaglio a filo di finestra |
| `parti.webp` | 1900 × 342 | 220 KB | `_assets/v2/lamp-parts6.png` | Sezione "Sei pezzi. Tutti sostituibili." |
| `scrivania-wide.webp` | 2000 × 857 | 34 KB | `_assets/v2/desk-wide.png` | Sezione "La luce è la specifica": la fotografia a tutta finestra |
| `scrivania.webp` | 1600 × 905 | 27 KB | `_assets/v2/lamp-desk.png` | Ritaglio 16:9 della stessa scena, **di scorta**: non è referenziato dalla pagina |

I PNG sorgente stanno fuori dall'app, in `bonus2-kit/_assets/v2/`; i `.webp` di
questa cartella sono la loro riduzione alla dimensione di visualizzazione. Il
prompt di generazione non è stato conservato insieme ai file: il PNG sorgente è
la copia di riferimento.

## Due file portano misure dentro il codice

Sostituendoli, ricontrolla anche questi numeri — sono l'unico punto in cui il
markup dipende dal contenuto di un'immagine.

- **`parti.webp`** — i sei oggetti stanno a queste posizioni (percentuali della
  larghezza del file: centro, bordo sinistro, bordo destro). Sono in
  `lib/copy.ts` → `parti.elenco`, e servono a far cadere l'etichetta n sotto
  l'oggetto n e a isolare un pezzo coprendo esattamente gli altri.

  | Pezzo | centro | da | a |
  |---|---|---|---|
  | Base | 10,5 % | 2,1 % | 18,9 % |
  | Perno | 23,9 % | 21,3 % | 26,5 % |
  | Braccio | 38,3 % | 28,7 % | 47,8 % |
  | Contrappeso | 57,2 % | 49,3 % | 65,1 % |
  | Testa | 74,5 % | 67,3 % | 81,7 % |
  | Cavo | 91,7 % | 84,7 % | 98,7 % |

- **`profilo.webp`** — il perno sta a 45,9 % × 11,7 % del riquadro; il braccio
  occupa la fascia alta fino al 18,2 % dell'altezza e la colonna riparte al
  17,2 %, così la giunzione resta coperta mentre il braccio ruota. I tre numeri
  stanno in `components/Arco.tsx`.

## Formato

WebP, qualità visiva pari alla dimensione di visualizzazione (≈2× per i display
a densità doppia). I render del prodotto hanno il canale alpha: il fondo bianco
della pagina è la loro materia, non un ritaglio.
