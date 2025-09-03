Det finns tre typer av maskinlärning.
1. Supervised learning - Tränas på en markerad dataset.
2. Unsupervised learning - Tränas på en omarkerad dataset.
3. Reinforcement learning  - Tränas på belöning och straff.

Bäst tillvägagångsätt gällade ML-typ är troligen reinforcement learning ifall jag skulle lösa problemet med endast AI, givet att antalet överlapp kan vara "straff". Men givet att jag kompletterar en existerande algoritm så gäller det att jag lär mig hur algoritmen fungerar. 

I och med att algoritmen kompletteras är jag osäker på om man ska gå på unsupervised eller supervised learning då jag har lite erfarenhet inom AI-fältet och jag är osäker på hur datan kommer se ut.

Jag tänker också att baserat på faktumet att ordningen på hur varje lastbil placeras görs manuellt och fungerar "bra nog" kan peka på att det finns vissa kombinationer av vanligare lastbilstyper som passar bättre ihop på rullbandet. Ifall man kan lära sig vanliga ordningar så kan man komplettera algoritmen och sänka antalet operationer som krävs för att hitta en acceptabel lösning.

Ett problem med detta kommer troligen vara att ifall modellen blir overfitted så kan resultaten alltid vara lösningar som är "bra nog", men det kommer aldrig nå en ideel lösning. Det blir en fråga vad som prioriteras, perfekta lösningen i långsam tid, eller en okej lösning i rimlig tid.

All maskinlärning i sig baseras på det optimistiska antagandet att Volvo Trucks delar med sig av sin data. 

En annan vinkel på exjobbet är hur man ska, på ett intuitivt sätt, visa tidsflödet av en grupp lastbilar mellan stationerna. En idé jag suttit och funderat på är att ha en lång ui som visualiserar bandet, med klossar som visualiserar lastbilarna. 

För att indikera överlapp och eventuella problem runtom kan man ha en +/- 2 buffer som visar T-2, T-1, T, T+1, T+2. Där T är nuvarande klockcykel. <--- Tid räknas i klockcyklar i nuläget.

På grund av att den är så lång kan man stega mellan kanske station 1-10, 2-11, 3-12, ...
På så sätt tappar man inte bort alla lastbilar lika enkelt.

Problemet man stöter på då är att ifall överlapp eller andra problem finns i (T+5, 45-54) och vi sitter i (T*, 13-22). Hur visar man på ett intuitivt sätt att det finns probblem i förstnämde sektorn. Hur tar man sig dit? \*Vi sitter alltid i T.

Min lösning kan vara att man indikerar på användargränssnittet att "Det finns x problem, se en lista på allihopa." eller visa på något sätt att det finns problem om man stegar frammåt. En lista kanske är mer intuitiv då man får se allt på en och samma gång och man kan gå till varje instans av problemen och inspektera dem.


