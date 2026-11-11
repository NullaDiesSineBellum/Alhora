# Alhora · Mapa de calor per barris de Barcelona

Mapa interactiu dels barris de Barcelona acolorit segons la **suma de vots de JUNTS, ERC i CUP-PR** a les Eleccions Generals del 23 de juliol de 2023.

**Veure el mapa:** https://nulladiessinebellum.github.io/Alhora/

## Què mostra

- Cada barri es pinta amb una escala de color càlida: com més fosc, més vots absoluts sumen les tres candidatures.
- En passar el cursor per sobre d'un barri (o tocar-lo al mòbil) apareix:
  - el total de vots,
  - el percentatge sobre electors,
  - la posició al rànquing (de 71).
- A sota del mapa hi ha un **rànquing de barris ordenat de més a menys vots**. Si cliques un barri del rànquing, es ressalta al mapa.
- Funciona amb mode clar i mode fosc, i s'adapta a pantalles de mòbil.

## Com interpretar-lo

El mapa utilitza **vots absoluts**, no percentatges. Per això reflecteix en bona part la **mida de cada barri**: un barri gran tindrà més vots encara que el pes relatiu de les tres candidatures sigui menor. Per comparar la intensitat del vot entre barris, és més fiable el percentatge sobre electors, que també es mostra al detall de cada barri.

L'escala de color és lineal entre el mínim (46 vots) i el màxim (8.249 vots). Com que la distribució és asimètrica (la mediana ronda els 1.850 vots), molts barris queden en tons clars i pocs en fosc.

## Limitacions

- **Falten dos barris:** Porta i Torre Baró (Nou Barris) surten en gris com a "sense dades", perquè no hi havia fitxers per a aquests barris. Hi ha 71 barris amb dades dels 73 de la ciutat.
- Es tracta només de la suma de tres candidatures; no es mostra cap altra formació ni el resultat global del barri.

## Dades

| Element | Origen |
|---|---|
| Resultats electorals per barri | Un fitxer Excel per barri (Eleccions Generals 23-07-2023). *[Completar: font oficial de les dades]* |
| Límits dels barris | [`martgnz/bcn-geodata`](https://github.com/martgnz/bcn-geodata), a partir de les dades obertes de l'Ajuntament de Barcelona |

### Tractament

1. Els 71 fitxers Excel es van unificar en una sola taula amb les columnes `Barri`, `Partit`, `Vots`, `% vots vàlids` i `% sobre electors`. El nom del barri es va agafar del títol de cada fitxer.
2. Per a cada barri, es van sumar els vots de **JUNTS**, **ERC** i **CUP-PR**.
3. Els límits geogràfics es van projectar i simplificar a camins SVG, i es van incrustar a la pàgina juntament amb les dades.

## Estructura del repositori

```
.
├── index.html   # Mapa complet: HTML, CSS, JavaScript, dades i geometries en un sol fitxer
└── README.md
```

La pàgina és **autònoma**: no depèn de cap llibreria, servei extern ni connexió a internet un cop carregada.

## Publicació

El mapa es serveix amb GitHub Pages des de la branca `main`, carpeta arrel. Per actualitzar-lo, només cal substituir `index.html` i fer commit.

## Llicència

*[Pendent de triar]*
