Elk van de startanimaties in het `animation. css`-bestand heeft een `animation`-eigenschapsgroep die aangeeft hoe de animatie moet worden uitgevoerd:

--- code ---
---
language: html
filename: animation.css
line_numbers: true
line_number_start: 1
line_highlights: 2
---
.spinme {
  animation: rotate-center linear 8s 2; /*Benodigde tijd voor de animatie en aantal herhalingen */
  display: inline-block;
}

--- /code ---

De `animation` regel in het `spinme` voorbeeld is opgesplitst in:

- `rotate-center`: de naam van de animatie
- `linear`: de timing van de animatie (linear is overal dezelfde afspeelsnelheid, andere voorbeelden zijn `ease`, `ease-in` en `ease-out`)
- `8s`: de duur van de animatie in seconden
- `2`: het aantal keren dat de animatie moet worden uitgevoerd (kan `infinite` (oneindig) zijn voor continu afspelen)

Wijzig een van deze waarden om de animatie te wijzigen. Een andere manier om de animatie aan te passen is door de `@keyframes`-regel aan te passen.  `@keyframes` bepalen hoe het element eruit moet zien wanneer een percentage van de lopende animatie is voltooid.

In de `rotate-center` animatie gebruikt door `spinme`, draait de animatie het object vanaf 0 graden aan het begin van de animatie (`0%`), tot 360 graden aan het einde van de animatie (`100%`).

--- code ---
---
language: html
filename: animation.css
line_numbers: true
line_number_start: 6
---
@keyframes rotate-center {
/* De spin me animatie code */
  0% { /* Rotateer van 0 tot 360 graden */
    transform: rotate(0);
  }
  100% {
    transform: rotate(360deg);
  }
}

--- /code ---

Op animaties kunnen specifieke stijlen worden toegepast op andere procentpunten tijdens de animatie-uitvoering. De `scale`-animatie heeft bijvoorbeeld vooraf bepaalde punten op 0%, 20%, 40%, 60% en 80%.

--- code ---
---
language: html
filename: animation.css
line_numbers: true
line_number_start: 6
---

@keyframes scale {
  /*De scale animatie code */
  0% {
    transform: scale(1, 1);
  }
  20% {
    transform: scale(1.1, 1.1);
  }
  40% {
    transform: scale(1.2, 1.2);
  }
  60% {
    transform: scale(1.1, 1.1);
  }
  80% {
    transform: scale(1, 1);
  }
}

--- /code ---

Bij de animatie kan op elk punt meer dan één stijl worden gewijzigd. De `bounce`-animatie verandert bijvoorbeeld de grootte en de y-coördinaat om een realistisch stuitereffect te creëren.

--- code ---
---
language: html
filename: animation.css
line_numbers: true
line_number_start: 22
---

@keyframes bounce {
  /* De bounce animatie code */
  0% {
    transform: scale(1, 1) translateY(0); /* Startpositie en huidige grootte */
  }
  10% {
    transform: scale(1.1, 0.9) translateY(0); /* Maak breder en minder hoog voor een pre-bounce squash effect */
  }
  30% {
    transform: scale(1, 1) translateY(-6rem); /* Keer terug naar huidige grootte en verplaats de emoji 100 px naar boven vanaf de huidige positie */

  }
  50% {
    transform: scale(1, 1) translateY(0); /* Verplaats emoji terug naar startpositie */
  }
}

--- /code ---

Je kunt kleur, positie, grootte, rotatie en nog veel meer eigenschappen veranderen als je de `@keyframes` code verandert.
