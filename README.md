De største udfordringer var at få design og spacing til at matche 1:1 med Figma – især i sektioner som AboutHero og Services. Jeg lærte vigtigheden af præcise marginer og padding samt at bruge CSS-variabler i stedet for enkelt vise-kodede farver, for at sikre konsistens på tværs af komponenter.

Et andet centralt punkt var at håndtere knappernes hover-effekter ensartet. Jeg løste det ved at samle alle varianter i én komponent (Button.astro) og styre farvevariationer gennem klasser som:
".btn--yellow:hover {
  background: #ffe5a2;
}
.btn--dark:hover {
  background: #fff;
  color: #181818;
}"

Jeg har prøvet mit bedste med at arbejde ud fra DRY-princippet (Don’t Repeat Yourself) ved at genbruge komponenter som Nav.astro, Footer.astro og Newsletter.astro på tværs af siderne.
Derudover er der brugt semantiske HTML-tags som <header>, <section> og <article> for at forbedre både struktur og tilgængelighed.

Jeg brugte også responsive grids og flexbox til layout, fx i team-sektionen:
".cards {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 80px 51px;
}
@media (max-width: 700px) {
  .cards {
    grid-template-columns: 1fr;
  }
}"

Jeg har valgt at holde al CSS komponent-specifik i stedet for at bruge en samlet global stylesheet.
Det betyder, at hver .astro-fil indeholder sine egne <style>-regler, fx:
"<style>
  .hero {
    display: flex;
    align-items: center;
    background: #f5f5f5;
  }
</style>"

Jeg har også arbejdet med JSON-filer til at hente data ind i komponenter — fx i Projections.astro, hvor dataene kommer fra financialProjections.json:
"{
  "title": "Financial Projections",
  "values": [
    {
      "icon": "cal",
      "title": "The Balance Sheet",
      "description": "A summary of assets and liabilities."
    }
  ]
}"


Gennem opgaven har jeg fået erfaring med at
- Arbejde med komponentstruktur i Astro
- Afprøve præcise designmatch med Figma
- Organisere CSS lokalt i komponenter
- Bruge Git og GitHub som versionsstyring
- Deploye en færdig side via Netlify.
