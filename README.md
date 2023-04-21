# FastMonai semesterprosjekt

## REPRODUSERE: 
Path variabal må oppdateres ved ned/inn -lastning av data. Path variabler må og oppdateres for innlastning av modeller. Datasettene kan lastes ned i “Download_Sets.ipynb” (>50GB for alle settene). To viktigste settene for prosjektet er “Task04_Hippocampus” og “Task02_Hearth”.

## Generell info
Mappestrukturen er delt BaseLines, data og experimental. I BaseLines trenes en modell for hvert datasett I egne notebooks og modellene lagres der. I data ligger alle datasettene. I experimental ligger notebooken med forsøk på transfer learning fra Hipppocampus til Heart.

Notebooksene er generelt veldig like, med noen mindre forskjeller. Se derfor “Task04_Hippocampus.ipynb” og “HippocampusToHeart.ipynb” for forklaring av kode.
Maskinlæring/maskinsyn har potensial til å forbedre diagnostiske evner, redusere menneskelige feil og øke effektiviteten i helsevesenet. Ved å trene algoritmer på store mengder medisinsk bildeinformasjon, kan maskinlæring hjelpe leger med å identifisere og klassifisere sykdommer i pasienters bilder på en mer effektiv og potensielt bedre måte enn kun eksperter.

## Bakgrunn for prosjektet
En av hovedutfordringene innen medisinsk avbildning er mangelen på tilstrekkelig gode data og menneskelige ressurser for å merke denne informasjonen korrekt. Merking av medisinsk bildeinformasjon er ofte tidkrevende og krever ekspertkunnskap. Her kan “transfer learning” være av nytte.

“Tranfser learning” benytter seg av forhåndstrente modeller for å redusere behovet for store mengder merkede data. Dette kan spare tid og ressurser ved at modeller kan "overføre" kunnskap de har lært fra en oppgave til en annen. Ved å bruke en forhåndstrent modell som grunnlag, kan man finjustere modellen med et mindre sett med merkede data for den spesifikke medisinske avbildningsoppgaven man ønsker å løse.

Slik bidrar “transfer learning” også bidra til å redusere behovet for store datamengder ved å dra nytte av forhåndstrent kunnskap, noe som kan være spesielt viktig når man arbeider med sjeldne sykdommer eller etniske grupper der data kan være vanskelig å samle inn.
fastMonai er et low-code open-source bibliotek bygget på fastai, MONAI og TorchIO. fastMonai simplifiserer.
Dataene brukt i dette prosjekt kommer fra “The Medical Segmentation Decathlon” og består av syv forskjellige sett og forskjellige avbildningsteknologier. Målet for konkurransen var å trene en modell på de syv datasettene som har høyest mulig ytelse på tre usette områder og datasett, altså “transfer learning”.  Ytterligere bevis på at en model med generelt god ytelse på flere områder vil fort tilpasse seg nye data var at vinnermodellen ble brukt videre i nye konkurranser. For eksempel ble åtte nnU-Net-derivater rangert blant de 15 beste algoritmene i 2019 Kidney and Kidney Tumor Segmentation Challenge (KiTS—https://kits19.grand-challenge.org/)8, som var MICCAI-utfordringen med flest deltakere i 2019. Ni av de ti beste algoritmene i COVID-19 Lung CT Lesion Segmentation Challenge 2020 (COVID-19-20 https://covid-segmentation.grand-challenge.org/) bygget sine løsninger på nnU-Net.

## Utfordringer
Mitt prosjekt hadde flere utfordringer. Her er de største:
-	Jeg ønsket å trene modellene mine lokalt fordi jeg tidligere har gått tom for ressurser på nettbaserte tjenester som kaggle. Tid brukt til feilsøking av kompatibilitet med forskjellige versjoner av pytorch, fastai, fastMonai og CUDA har tatt adskillig mye mer tid enn forventet. Videre slet jeg også med dedikert minne på GPU. Filene er av såpass stor størrelse at jeg ofte måtte nedskalere bilder og kjøre batch size på 1 eller 2.

-	Datasettene varierte i antall dimensjoner (3D og 4D), størrelse på bildene og antall labels. Jeg hadde ikke satt av nok tid til denne type problemstillinger, det gjenspeiler seg nok også i resultatet. Spesielt størrelse på bildene var en utfordring. 

-	Datasettene var vanskelige å forstå rent koseptuelt. Et 4D bilde med “x-voxel spacing” er utfordrende å forstå i 2D med lite medisinks bakgrunn. Hvertfall sammenlignet et RGB bilde i 2D med tre kanaler.

## Resultat
Resultatet av prosjektet var på sitt beste middelmådig. For mye av tiden gikk til å få kode til å fungere, istedentfor å gjøre meningsfulle endringer på data for å legge bedre til rette for at modeller skal kunne fungere på ulike datasett. Det var også planlagt mer enn et forsøk på transfer learning, men utfordringene i kombinasjon med dårlig tidsplanlegging gjorde det ikke mulig. Lærdommen fra prosjektet har derimot vært ok+. Arbeidet med å få ting til å fungere er det og lærdom i.


