# Opdrachtbeschrijving

## Inleiding

Je bent net begonnen als developer bij een bedrijf dat TV's verkoopt: Tech It Easy. Tijdens de cursus Spring Boot ga jij een backend applicatie programmeren voor het bedrijf. De winkel heeft een inventaris van televisies die moet worden bijgehouden. Na iedere les gaan we deze applicatie een stukje verder uitbouwen door middel van de huiswerkopdrachten. Zo krijg je stap-voor-stap meer ervaring in het bouwen van een backend applicatie. Aan het einde van de cursus zullen we een werkende Tech It Easy backend applicatie hebben!

## Recap van vorige opdracht

Je hebt inmiddels je applicatie draaiende gekregen. Je hebt ook je database gevuld door middel van het `data.sql` bestand en je hebt de applicatie uitgebreid met een RemoteController, een CIModule en een WallBracket.

## Opdrachtbeschrijving
In deze opdracht ga je een aantal belangrijke functionaliteiten van jou applicatie visualiseren met behulp van een sequentiediagram.

## Randvoorwaarden

De opdracht bevat minstens drie sequentie diagrammen voor elk een andere use case:
- Voeg een RemoteController toe aan een Television
- Voeg een CIModule toe aan een Television
- Voeg een WallBracket toe aan een Television

### Belangrijk

De sequentie diagrammen laten alle lagen van je applicatie zien en de communicatie die daartussen plaatsvindt.

## Stappenplan

_Let op_: het is uitdagender om jouw eigen stappenplan te maken. Mocht je niet zo goed weten waar je moet beginnen, kun je onderstaand stappenplan volgen:

1. Maak een Actor lifeline.
2. Maak een TelevisionController lifeline.
3. Trek een comunicatie pijl tussen Actor en TelevisionController waaraan je de parameters van de `assignRemoteControllerToTelevision` methode aan meegeeft.
4. Maak een TelevisionService lifeline.
5. Trek een communicatie pijl tussen TelevisionController en TelevisionService waaraan je de parameters van de `assignRemoteControllerToTelevision` methode aan meegeeft.
6. Maak een TelevisionRepository lifeline.
7. Trek een communicatie pijl van TelevisionService naar TelevisionRepository waaraan je de `televisionId` meegeeft. Voor de duidelijkheid maak je hier `findById(televisionId)` van, omdat we dadelijk meer communicatie pijlen gaan zetten tussen TelevisionService en TelevisionRepository.
8. Maak een Database lifeline.
9. Trek een communicatie pijl van TelevisionRepository naar Database waaraan je het id meegeeft. Je kunt ook het complete sql commando meegeven, omdat dat natuurlijk de functie van de repository laag is.
10. Trek een communicatie pijl van Database terug naar TelevisionRepository waaraan je `Television` meegeeft.
11. Trek een communicatie pijl van TelevisionRepository terug naar TelevisionSerivce waaraan je return waarde van de findById methode meegeeft.
12. Maak een RemoteControllerRepository lifeline.
13. Trek een communicatie pijl tussen TelevisionService en RemoteControllerRepository waaraan je de `remoteControllerId` aan mee geeft. Wikkel dit wederom in de bijbehorende functienaam, dus `findById(remoteControlleId)`
14. Trek een communicatie pijl van RemoteControllerRepository naar Database waaraan je de id of het sql commando meegeeft.
15. Trek een communicatie pijl van Database terug naar RemoteControllerRepository waaraan je `RemoteController` meegeeft.
16. Trek een communicatie pijl van RemoteControllerRepositroy terug naar TelevisionService waaraan je returnwaarde van de findById methode meegeeft.
17. Trek een communicatie pijl van TelevisionService naar TelevisionService waaraan je `setRemoteController(remotecontroller)` meegeeft.
18. Trek een communicatie pijl van TelevisionService naar TelevisionRepository waraan je `save(television)` meegeeft.
19. Trek een communicatie pijl van TelevisionRepository naar Database waaraan je het id en de remotecontroller meegeeft of het sql commando.
20. Trek een communicatie pijl van Database terug naar TelevisionRepository waaraan je de television meegeeft.
21. Trek een communicatie pijl van TelevisionRepository terug naar TelevisionService waaraan je de returnwaarde van de save() methode meegeeft.
22. Trek een communicatie pijl van TelevisionService terug naar TelevisionController waaraan je de returnwaarde van de methode meegeeft.
23. Trek een communicatie pijl van TelevisionController terug naar Actor waaraan je de juiste HttpStatus meegeeft.
24. Dit stappenplan kun je nu gebruiken (met wat aanpassingen) om de sequentiediagrammen voor het toevoegen van een CIModule en het toevoegen van een WallBracket te tekenen.

## Bonusopdracht
Zoek nog een andere usecase die je kunt vertalen naar een sequentiediagram.
