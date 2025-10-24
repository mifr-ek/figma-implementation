I denne opgave har jeg arbejdet med at genskabe et Figma-design 1:1 i Astro, og det har virkelig givet mig en forståelse for, hvor meget detalje-nørderi der ligger i at få et design til at se præcist rigtigt ud.
Jeg startede med at tro at “det nok bare handlede om at skrive noget HTML og lidt CSS”, men fandt hurtigt ud af at der ligger meget mere bag.

De største udfordringer var helt klart at få spacing, tekstknæk og placeringer til at matche Figma – især i sektionerne AboutHero og Services.
Jeg brugte virkelig meget tid på marginer og padding og lærte, hvor vigtigt det er at arbejde konsekvent, især når man har flere sektioner der overlapper eller bruger negative marginer for at opnå Figma-effekten.

Jeg begyndte også at arbejde med CSS-variabler i stedet for hårdkodede farver. Fx kunne jeg bare ændre --accent-color ét sted, og så blev alle de gule elementer opdateret på tværs af hele sitet. Det gav mig en meget bedre fornemmelse for, hvordan man holder sit design fleksibelt og vedligeholdelsesvenligt.

Et af de steder, jeg virkelig blev klogere, var i arbejdet med komponenter.
Jeg prøvede mit bedste på at følge DRY-princippet (Don’t Repeat Yourself) ved at genbruge ting som Nav.astro, Footer.astro og Newsletter.astro i stedet for at kopiere den samme kode igen og igen.
Det gav mig et meget mere professionelt workflow – og jeg begyndte at tænke i komponenter i stedet for “sider med kode”.

Et konkret eksempel var mine knapper.
I starten havde jeg forskellige knap-styles rundt omkring, men det blev hurtigt rodet og derfor samlede jeg det hele i én komponent – Button.astro – hvor alle varianterne styres med klasser som: ".btn--yellow:hover {
  background: #ffe5a2;
}
.btn--dark:hover {
  background: #fff;
  color: #181818;
}"

Jeg blev også udfordret med noget af det, jeg har sværest ved. Nemlig Grid og Flexbox.
Jeg brugte grid i Team-sektionen til at placere kortene i tre kolonner på desktop og automatisk skifte til én kolonne på mobil: ".cards {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 80px 51px;
}
@media (max-width: 700px) {
  .cards {
    grid-template-columns: 1fr;
  }
}"

Jeg valgte at holde al CSS komponent-specifik i stedet for at bruge et globalt stylesheet.
Det betyder, at hver .astro-fil indeholder sine egne <style>-regler, fx: "<style>
  .hero {
    display: flex;
    align-items: center;
    background: #f5f5f5;
  }
</style>"

Jeg arbejdede også med JSON-filer til at trække data ind i komponenter – fx i Projections.astro, hvor indholdet hentes fra financialProjections.json.
Det var lidt svært for mig i begyndelsen, men jeg syntes det var ret fedt, at jeg kunne opbygge kort dynamisk ved at mappe over dataene: "{
  "title": "Financial Projections",
  "values": [
    {
      "icon": "cal",
      "title": "The Balance Sheet",
      "description": "A summary of assets and liabilities."
    }
  ]
}"

Alt i alt har opgaven givet mig en bedre forståelse af:
- hvordan man tænker i komponenter og genbrug
- hvordan man får et design til at matche præcist med Figma
- hvordan man organiserer CSS lokalt i stedet for globalt
- og hvordan GitHub og Netlify bruges til at gøre et projekt offentligt
