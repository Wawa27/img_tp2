## Variation de quantification

- En terme de quantification, cette opération permet de réduire le nombre niveaux de gris possible. 
La composante bleue est donc codée sur 4 bits au lieux de 8. 
Il reste donc 2^4 = 16 niveaux de gris possible par pixel.

- On gagne 4 bits par composant bleu, 3 par composante rouge et 1 par composante verte, on gagne un total
de 9 bits par pixel (de 24 bits à 16). On a donc un gain théorique de 33% par rapport à l'image source.

## Sous échantillonnage

- Cette opération est appelée sous-échantillonange d'un facteur 4 car on regroupe chaque pixels par 4.
- En sous-échantillonant avec un facteur 4 on peut réduire de 4 le nombre de bits par composante, soit une réduction de 4/3 (1.33x) sur le nombre
  de bits totale de l'image par composante.
- On constate une dégradation drastique de l'image recomposé en terme de qualité. Cela est surement dû au faite que l'oeil est
beaucoup plus sensible au vert que le rouge et le bleu.
  
Taille mémoire de l'image source = Nx * Ny * n * m = 512 * 512 * 3 * 8 = 6 291 456 bits
Taille mémoire de l'image après les modifications = TailleComposanteRouge + TailleComposanteVerte + TailleComposanteBleue
avec:
TailleComposanteRouge = Nx * Ny * n * m = 256 * 256 * 5 = 327 680 bits
TailleComposanteVerte = Nx * Ny * n * m = 512 * 512 * 6 = 1 572 864 bits
TailleComposanteBleue = Nx * Ny * n * m = 128 * 128 * 4 = 65 536 bits

TailleTotale = 1 966 080 bits

- On a un gain de 4 325 376 bits soit près de 4Mo par rapport à l'image source soit à peu près 3x moins que l'image source.
