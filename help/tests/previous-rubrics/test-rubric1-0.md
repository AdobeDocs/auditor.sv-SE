---
description: information om Adobe Experience Platform Auditor-tester
seo-description: information about the Adobe Experience Platform Auditor tests
seo-title: Test rubric 0.0.8
title: Provningsrutin 0.0.8
uuid: c62b7169-a650-4650-876f-c254eb57cb25
exl-id: 0313e271-5664-4a34-9e3c-8cb1c61d8b93
source-git-commit: 286a857b2ff08345499edca2e0eb6b35ecf02332
workflow-type: tm+mt
source-wordcount: '1998'
ht-degree: 4%

---

# Provningsrutin 0.0.8{#test-rubric}

## Provningsrutin 0.0.8

<!-- Note to writer: Please review the tables on this page for formatting and accuracy. Compare to original file.-->

![](assets/space.png)

## Larm {#alerts}

Den här referensen innehåller mer information om de aviseringar som visas i Adobe Experience Platform Auditor för tester.

Varningar visar problem som du bör vara medveten om, men som inte påverkar ditt poängtal.

<table id="table_031432C9BB804A6F90E7FF572739E169"> 
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Test </th> 
    <th colname="col2" class="entry"> Kriterier </th> 
    <th colname="col3" class="entry"> Rekommendation </th> 
   </tr>
  </thead>
  <tbody> 
   <tr> 
    <td colname="col1"> <p><b>Advertising Cloud - Korrigera konverteringstagg har implementerats</b> </p> <p>Bredd: 0 </p> </td> 
    <td colname="col2"> <p>Kontrollera om rätt konverteringstagg används. </p> <p> <p>Varning: Om du använder de föråldrade konverteringstaggarna för TubeMogul kan data gå förlorade. </p> </p> </td> 
    <td colname="col3"> <p>Uppgradera dina konverteringspixlar till de nya konverteringstaggarna för Advertising Cloud-bilder. </p> <p>Detta kan du enkelt göra med Advertising Cloud-tillägget för Adobe Experience Platform Launch. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b>Advertising Cloud - Tagg för endast bild</b> </p> <p>Bredd: 0 </p> </td> 
    <td colname="col2"> <p>Advertising Cloud bildpixelformat bör matcha något av följande rekommenderade format: </p> <p> 
      <ul id="ul_D85BE9C8A8654DE890E1A814E3573D86"> 
       <li id="li_E2AEDD76AC7044E8AD6AE8375858D198"> <p><span class="codeph"> /rtd.tubemogul.com/upi/?sid=&lt;hash_value&gt;</span> </p> </li> 
       <li id="li_1EEFA03516BF445294B5EC5DED891758"> <p><span class="codeph"> /rtd-tm.everesttech.net/upi/?sid=&lt;hash_value&gt;</span> </p> </li> 
       <li id="li_F72206B142214217BDD34356D2F3D8AD"> <p><span class="codeph"> http(s)://pixel.everesttech.net/px2/&lt;numeric_id&gt;?</span> </p> </li> 
      </ul> </p> </td> 
    <td colname="col3"> <p>Uppgradera dina Advertising Cloud-pixlar till de nya Advertising Cloud-taggar som säkerställer att du utnyttjar alla funktioner i Advertising Cloud. </p> <p>Det är enklast att göra med Advertising Cloud-tillägget för Platform launch. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b>Advertising Cloud - Synkronisering av pixlar DSP segment aktiverat</b> </p> <p>Bredd: 0 </p> </td> 
    <td colname="col2"> <p>Kontrollera om TubeMogul-segmentpixeln innehåller en DSP synkroniseringsinställning och rekommendera att inställningen läggs till i pixeln. </p> <p>Inställningen DSP synkronisering bestäms av användningen av en frågesträngsparameter, så </p> <p>Om taggen skickas till<span class="codeph"> ("https://rtd.tubemogul.com/upi/?sid=&lt;hash_value&gt;"</span> </p> <p> ELLER <span class="codeph"> "/rtd-tm.everesttech.net/upi/?sid=&lt;hash_value&gt;"</span> </p> <p> ELLER <span class="codeph"> "/pixel.everesttech.net/px2/&lt;numeric_id&gt;?"</span> </p> <p>OCH taggen innehåller URL-parametern <span class="codeph"> "sid=")</span> </p> <p>Kontrollera sedan om URL-parametern <span class="codeph"> "cs=0"</span> eller<span class="codeph"> "cs=1"</span> finns, och om det inte rekommenderas att <span class="codeph"> "cs=1"</span> läggas till i dessa pixlar så att målgruppens matchningsfrekvens kan förbättras. </p> </td> 
    <td colname="col3"> <p> Lägg till URL-parametern <span class="codeph"> "cs=1"</span> till dina Advertising Cloud-pixlar så att DSP kan synkroniseras, vilket ökar målgruppernas matchningsfrekvens. </p> <p>Det är enklast att göra detta med Advertising Cloud-tillägget för Platform launch. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b>DTM - sidans nedre återanropsplacering</b> </p> <p>Bredd: 0 </p> <p><a href="https://docs.adobe.com/content/help/en/dtm/using/client-side/t-add-header-fooder-code.html" format="html" scope="external"> Ytterligare information</a> </p> 
     <!--
       TEa9df69942f404055a64262889c8b21d3 
     --> </td> 
    <td colname="col2"> <p> Dynamic Tag Management kräver<span class="codeph"> _satellit.pageBottom()</span> funktion. </p> <p>Det är bäst att taggen är <i>sista</i> -taggen i <span class="codeph"> &lt;body&gt;</span>. Om den finns i <span class="codeph"> &lt;body&gt;</span> -taggen har en chans att fungera, men eftersom det inte är en bra metod kan den fungera felaktigt eller med oväntade eller oönskade resultat. </p> </td> 
    <td colname="col3"> <p>Lägg till det infogade skriptet omedelbart före stängningen <span class="codeph"> &lt;/body&gt;</span> -tagg för att säkerställa korrekt DTM-funktionalitet. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b> Experience Cloud ID-tjänst - använd endast en AdobeOrg</b> </p> <p>Bredd: 0 </p> <p><a href="https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html" format="html" scope="external"> Ytterligare information</a> </p> </td> 
    <td colname="col2"> <p>I en normal MCID-implementering bör en enda AdobeOrg användas. </p> </td> 
    <td colname="col3"> <p>Verifiera att det finns flera AdobeOrg ID:n för den här implementeringen. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b> Mål - Innehåll i mboxDefault</b> </p> <p>Bredd: 0 </p> <p><a href="https://docs.adobe.com/content/help/en/target/using/implement-target/client-side/functions-overview/mboxcreate-atjs.html" format="html" scope="external"> Ytterligare information</a> </p> </td> 
    <td colname="col2"> <p> Innehållet ska finnas i mboxDefault när at.js används. </p> </td> 
    <td colname="col3"> <p>Kontrollera att innehållet är tillgängligt. </p> </td> 
   </tr> 
  </tbody> 
</table>

![](assets/space.png)

## Konfiguration {#configuration}

Den här referensen ger mer information om testerna som plattformsgranskaren utför för konfiguration.

Platform Auditor utvärderar taggarna mot andra regler och rekommenderade metodtips.

<table id="table_A8A1FC360482447185C8460A18426638"> 
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Test </th> 
    <th colname="col2" class="entry"> Kriterier </th> 
    <th colname="col3" class="entry"> Rekommendation </th> 
   </tr>
  </thead>
  <tbody> 
   <tr> 
    <td colname="col1"> <p><b>Advertising Cloud - Konverteringsnamn innehåller endast alfanumeriska tecken</b> </p> <p>Bredd: 3 </p> </td> 
    <td colname="col2"> <p>The <span class="codeph"> ev_conversion_property_name</span> parametern får bara innehålla numeriska och decimala värden EXCEPT för "<span class="codeph"> ev_transid</span>"-parametern ( <span class="codeph"> ev_transid</span> värdet kan innehålla text eller numeriska värden) </p> <p>Sök efter <span class="codeph"> everesttech.net</span> pixlar som innehåller en URL-parameter som börjar med <span class="codeph"> ev_</span>. </p> <p>Exempel: </p> <p><span class="codeph"> http://pixel.everesttech.net/1180/t?ev_page_load=1&amp;ev_revenue=$12&amp;ev_transid=1hf74i47</span> </p> </td> 
    <td colname="col3"> <p> Kontrollera att egenskapsparametrarna för transaktionen bara innehåller numeriska och decimala värden. </p> <p> <p>Varning: Andra värdetyper kan orsaka dataförlust. </p> </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b>Advertising Cloud - Konverteringsnamn använder URL-säkra tecken</b> </p> <p>Bredd: 3 </p> </td> 
    <td colname="col2"> <p> Namn på konverteringsegenskaper får inte innehålla ett et-tecken eller frågetecken. </p> <p> Exempel: </p> <p><span class="codeph"> http://pixel.everesttech.net/1180/t?ev_revenue&amp;order=12&amp;ev_transid=</span> </p> </td> 
    <td colname="col3"> <p>Se till att egenskapsparametrarna för transaktioner inte innehåller ett icke-kodat et-tecken eller frågetecken. Dessa bryter URL-formatet. </p> <p> <p>Varning: Egenskapsparametrar som innehåller ett icke-kodat et-tecken eller frågetecken (till exempel: <span class="codeph"> ev_formComplete?=1</span> eller <span class="codeph"> ev_formComplete&amp;Submit=1</span>), kan leda till dataförlust. </p> </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b>Advertising Cloud - Transaktions-ID har implementerats korrekt</b> </p> <p>Bredd: 1 </p> </td> 
    <td colname="col2"> <p> Egenskapsnamnet <span class="codeph"> ev_transid=</span> får inte vara tom. </p> <p>Exempel: </p> <p><span class="codeph"> http://pixel.everesttech.net/1180/t?ev_page_load=1&amp;ev_revenue= 12&amp; ev_transid=</span> </p> </td> 
    <td colname="col3"> <p>Egenskapsnamnet <span class="codeph"> ev_transid=</span> får inte lämnas utan ett värde (<span class="codeph"> ev_transid=</span>). Om detta lämnas utan ett värde kan transaktionsdata gå förlorade. Tilldela ett värde till <span class="codeph"> ev_transid=</span> eller ta bort parametern från pixeln. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b>Analyser - instansierat i DOM</b> </p> <p>Bredd: 5 </p> <p><a href="https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/testing-and-validation-process/impl-validation.html" format="html" scope="external"> Ytterligare information</a> </p> </td> 
    <td colname="col2"> <p> Adobe Analytics-koden är inte installerad eller kan inte köras. Returnerar 0 när ingen analyskod finns på webbsidan. </p> </td> 
    <td colname="col3"> <p>Kontrollera att Analytics-taggen implementeras på sidan och inte blockeras av efterföljande skriptaktiviteter. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b>Analyser - instansierad en gång</b> </p> <p>Bredd: 5 </p> <p><a href="https://docs.adobe.com/content/help/en/analytics/implementation/home.html" format="https" scope="external"> Ytterligare information</a> </p> </td> 
    <td colname="col2"> <p> Adobe Analytics-koden upptäcktes mer än en gång på sidan. . Returnerar 0 när ingen analyskod finns på webbsidan. </p> </td> 
    <td colname="col3"> <p>Kontrollera att det bara finns en Analytics-tagg på sidan. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b>Analytics - Senaste versionen</b> </p> <p>Bredd: 3 </p> <p><a href="https://docs.adobe.com/content/help/sv-SE/analytics/implementation/appmeasurement-updates.html" format="https" scope="external"> Ytterligare information</a> </p> </td> 
    <td colname="col2"> <p> Dina sidor kör inte den senaste versionen av kodbiblioteket för Analytics. Kodbibliotek som används av Experience Cloud-teknik uppdateras och ändras ständigt för att dra nytta av prestandaförbättringar och tillhandahålla de senaste funktionerna. Returnerar 0 när ingen analyskod finns på webbsidan. </p> </td>       
    <td colname="col3"> <p>Installera den senaste versionen av Analytics-biblioteket. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b>DTM - Self-Hosted</b> </p> <p>Bredd: 4 </p> <p><a href="https://docs.adobe.com/content/help/en/dtm/using/client-side/client-side-information.html" format="html" scope="external"> Ytterligare information</a> </p> </td> 
    <td colname="col2"> <p> DTM-biblioteket ligger på Adobe Akamai-instansen på <span class="filepath"> assets.adobedtm.com</span>. </p> <p> Självvärdande är det rekommenderade sättet att läsa in DTM eftersom det ger bättre kontroll över webbplatsens prestanda genom cachekontroll, minskar beroenden av skript från tredje part och ger större kontroll över publiceringsprocessen. DTM-biblioteken kan hanteras via din egen webbhosting eller CDN. </p> </td> 
    <td colname="col3"> <p>Självvärdande är det rekommenderade sättet att läsa in DTM på en sida. Även om DTM-värdtjänster via Akamai CDN fungerar i de flesta fall, förbättras sidprestanda av självvärdtjänster. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b>DTM - tredjepartstaggar läses in asynkront efter DOM-klart</b> </p> <p>Bredd: 3 </p> <p><a href="https://docs.adobe.com/content/help/en/dtm/using/resources/load-order.html" format="html" scope="external"> Ytterligare information</a> </p> </td> 
    <td colname="col2"> <p>För att skapa en balans mellan en bra användarupplevelse och insamling av korrekta data bör tredjepartstaggar aktiveras vid DOM ready. Detta säkerställer att dessa spårningsskript körs utan att webbplatsfunktionaliteten påverkas. </p> </td> 
    <td colname="col3"> <p>Lös det här problemet genom att justera alla regler som kör pixlar från tredje part som ska utlösas på DOM Ready. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b>Experience Cloud ID-tjänst - senaste version</b> </p> <p>Bredd: 2 </p> <p><a href="https://docs.adobe.com/content/help/en/dtm/using/tools/macid.html" format="html" scope="external"> Ytterligare information</a> </p> </td> 
    <td colname="col2"> <p> Dina sidor använder inte den senaste versionen av kodbiblioteket för Visitor ID-tjänsten, <span class="codeph"> visitorAPI.js</span>. Kodbibliotek som används av Experience Cloud-teknik uppdateras och ändras ständigt för att dra nytta av prestandaförbättringar och tillhandahålla de senaste funktionerna. </p> </td> 
    <td colname="col3"> <p>Installera den senaste versionen av tjänstbiblioteket för Visitor-ID. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b>Mål - senaste version</b> </p> <p>Bredd: 2 </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/dtm/target/" format="html" scope="external"> Ytterligare information</a> </p> </td> 
    <td colname="col2"> <p> Dina sidor kör inte den senaste versionen av kodbiblioteket Target. Kodbibliotek som används av Experience Cloud-teknik uppdateras och ändras ständigt för att dra nytta av prestandaförbättringar och tillhandahålla de senaste funktionerna. </p> </td> 
    <td colname="col3"> <p>Installera den senaste versionen av målbiblioteket. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b>Mål - mboxDefault föregår mboxCreate </b> </p> <p>Bredd: 5 </p> <p><a href="https://docs.adobe.com/content/help/en/target/using/implement-target/client-side/functions-overview/mboxcreate-atjs.html" format="html" scope="external"> Ytterligare information</a> </p> </td> 
    <td colname="col2"> <p>Att använda <span class="codeph"> mboxCreate</span> ser ut ungefär så här: </p> <p> <span class="codeph"> &lt;div class="mboxDefault"&gt;&lt;!-Kundinnehåll—&gt;&lt;/div&gt;&lt;script&gt;mboxCreate('myMboxName')&lt;/script&gt;</span> </p> </td> 
    <td colname="col3"> <p>Var noga med att inkludera en <span class="codeph"> &lt;div class="mboxDefault"&gt;&lt;/div&gt;</span> tagg före anrop <span class="codeph"> mboxCreate()</span>. at.js kommer inte att lägga till en åt dig. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b>Mål - Giltig DOCTYPE</b> </p> <p>Bredd: 5 </p> <p><a href="https://docs.adobe.com/content/help/en/target/using/implement-target/client-side/functions-overview/mboxcreate-atjs.html" format="html" scope="external"> Ytterligare information</a> </p> </td> 
    <td colname="col2"> <p> En ogiltig DOCTYPE upptäcktes. Inga lådor kommer att utlösas i det här scenariot. </p> <p>För at.js måste DOCTYPE vara i standardläge, annars fungerar inte Target. </p> </td> 
    <td colname="col3"> <p>Uppdatera DOCTYPE på sidan. </p> </td> 
   </tr> 
  </tbody> 
</table>

![](assets/space.png)

## Konsekvens för taggar {#tag-consistency}

Den här referensen ger mer information om testerna som Platform Auditor utför för att få en enhetlig tagg.

Plattformsgranskaren utvärderar om taggarna är konsekventa över olika URL-adresser.

<table id="table_4F9ED873BAF741D19BFB0F297B3A1FDB"> 
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Test </th> 
    <th colname="col2" class="entry"> Kriterier </th> 
    <th colname="col3" class="entry"> Rekommendation </th> 
   </tr>
  </thead>
  <tbody> 
   <tr> 
    <td colname="col1"> <p><b>Analyser - Konsekvent kodversion </b> </p> <p>Bredd: 5 </p> <p><a href="https://docs.adobe.com/content/help/en/analytics/implementation/home.html" format="html" scope="external"> Ytterligare information</a> </p> </td> 
    <td colname="col2"> <p> Mer än en version av Analytics-koden hittades. </p> </td> 
    <td colname="col3"> <p>Ersätt alla instanser av Analytics med den aktuella versionen. </p> </td> 
   </tr> 
  </tbody> 
</table>

![](assets/space.png)

## Tagg presence {#tag-presence}

Den här referensen ger mer information om testerna som Platform Auditor utför för tagghistorik.

Plattformsgranskaren utvärderar om taggen finns, om den finns på rätt plats i sidkoden och så vidare.

<table id="table_98A2E3F7B3154EEFA76D0CAE2FE97CAB"> 
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Test </th> 
    <th colname="col2" class="entry"> Kriterier </th> 
    <th colname="col3" class="entry"> Rekommendation </th> 
   </tr>
  </thead>
  <tbody> 
   <tr> 
    <td colname="col1"> <p><b>Advertising Cloud - kodnärvaro</b> </p> <p>Bredd: 5 </p> </td> 
    <td colname="col2"> <p> Advertising Cloud-taggen är inte tillgänglig i DOM. </p> </td> 
    <td colname="col3"> <p>Implementera taggen Advertising Cloud med tillägget Advertising Cloud för Platform launch. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b>Advertising Cloud - segmentpixel implementerad</b> </p> <p>Bredd: 5 </p> </td> 
    <td colname="col2"> <p> Uppgradera dina Advertising Cloud-segmentpixlar till de nya Advertising Cloud-taggar som bara innehåller bilder. Om du använder de föråldrade AMO-segmenttaggarna kan data gå förlorade. </p> </td> 
    <td colname="col3"> <p>Implementera Advertising Cloud-segmentpixeln med tillägget Advertising Cloud för Platform launch. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b>Analyser - läses in i DOM</b> </p> <p>Bredd: 5 </p> <p><a href="https://docs.adobe.com/content/help/en/analytics/implementation/home.html" format="https" scope="external"> Ytterligare information</a> </p> </td> 
    <td colname="col2"> <p> Det gick inte att identifiera Adobe Analytics-taggen. </p> </td> 
    <td colname="col3"> <p>Installera den senaste versionen av Analytics. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b> DTM - Biblioteket har lästs in</b> </p> <p>Bredd: 5 </p> <p>Ytterligare information: </p> <p> 
      <ul id="ul_7E706EBC2E4649A69732E6982E116E22"> 
       <li id="li_9AF0257E39C347A9AE6D8D8FFBD66B38"><a href="https://docs.adobe.com/content/help/en/dtm/using/admin/c-troubleshooting.html" format="html" scope="external"> DTM-felsökning</a> </li> 
       <li id="li_7B422BCCD2654B0A9059799FB5276BE8"><a href="https://docs.adobe.com/content/help/en/dtm/using/client-side/t-add-header-fooder-code.html" format="html" scope="external"> Lägg till sidhuvuds- och sidfotskod</a> </li> 
      </ul> </p> </td> 
    <td colname="col2"> <p> Det gick inte att hitta ett globalt _satellitobjekt i DOM. Dynamic Tag Management är inte installerat eller kan inte köras. </p> </td> 
    <td colname="col3"> <p>Kontrollera att DTM-biblioteket är implementerat på sidan och inte blockeras av efterföljande skriptaktiviteter. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b> DTM - En inbäddningskod</b> </p> <p>Bredd: 5 </p> <p><a href="https://docs.adobe.com/content/help/en/dtm/using/client-side/code.html" format="html" scope="external"> Ytterligare information</a> </p> </td> 
    <td colname="col2"> <p> Produktionsplatser bör bara läsa in ett DTM-bibliotek. </p> </td> 
    <td colname="col3"> <p>Kontrollera att det bara är produktionsbiblioteket som läses in på sidan. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b>DTM - pageBottom-återanrop finns i &lt;body&gt;</b> </p> <p>Bredd: 5 </p> <p><a href="https://docs.adobe.com/content/help/en/dtm/using/client-side/t-add-header-fooder-code.html" format="html" scope="external"> Ytterligare information</a> </p> </td> 
    <td colname="col2"> <p> The <span class="codeph"> _satellit.pageBottom()</span> callback-funktionen hittades inte i <span class="codeph"> &lt;body&gt;</span> på sidan, vilket krävs av Dynamic Tag Management. </p> <p>Testet misslyckas om <span class="codeph"> pageBottom </span>anropet inte finns på sidan eller om det finns på sidan <span class="codeph"> &lt;head&gt;</span> -tagg (eller någon annan oväntad plats). Det går bara om <span class="codeph"> pageBottom</span> finns någonstans i <span class="codeph"> &lt;body&gt;</span> -tagg. Om den inte finns på sidan alls fungerar den inte och de andra två <span class="codeph"> pageBottom</span> testerna kommer också att misslyckas. </p> </td> 
    <td colname="col3"> <p>Lägg till det infogade skriptet omedelbart före stängningen <span class="codeph"> &lt;/body&gt;</span> -tagg för att säkerställa korrekt DTM-funktionalitet. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b>DTM - pageBottom-tagg utlöses</b> </p> <p>Bredd: 5 </p> <p><a href="https://docs.adobe.com/content/help/en/dtm/using/client-side/t-add-header-fooder-code.html" format="html" scope="external"> Ytterligare information</a> </p> </td> 
    <td colname="col2"> <p> The DTM <span class="codeph"> pageBottom</span> -taggen kunde inte identifieras. </p> <p>Detta kan inträffa om samtalet sker inom en <span class="codeph"> if</span> programsats som resulterar i något liknande <span class="codeph"> if (false) {_satellit.pageBottom()}</span>. Även om taggen kan finnas och placeras på rätt sätt kanske den ändå inte fungerar. </p> </td> 
    <td colname="col3"> <p>Installera DTM <span class="codeph"> pageBottom</span> på alla sidor. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b>Experience Cloud ID-tjänst - cookie-närvaro</b> </p> <p>Bredd: 5 </p> <p><a href="https://docs.adobe.com/content/help/en/dtm/using/tools/macid.html" format="html" scope="external"> Ytterligare information</a> </p> </td> 
    <td colname="col2"> <p> The <span class="codeph"> AMCV_</span> Det gick inte att hitta cookie. Du måste instansiera ett besökarobjekt från <span class="codeph"> VisitorAPI.js</span> kod. </p> </td> 
    <td colname="col3"> <p> Om det här är en DTM-implementering kontrollerar du att AdobeOrg-id:t har angetts korrekt i MCID-verktyget. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b>Experience Cloud ID-tjänst - MID-värde finns</b> </p> <p>Bredd: 5 </p> <p><a href="https://docs.adobe.com/content/help/sv-SE/id-service/using/intro/cookies.html" format="html" scope="external"> Ytterligare information</a> </p> </td> 
    <td colname="col2"> <p> Mittvärdet hittades inte i <span class="codeph"> AMCV_</span> cookie. </p> </td> 
    <td colname="col3"> <p>Testa igen för att kontrollera om det finns någon MCID API-fördröjning. Kontakta Adobe kundtjänst om problemet kvarstår. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b> Experience Cloud ID-tjänst - ska installeras</b> </p> <p>Bredd: 5 </p> <p><a href="https://docs.adobe.com/content/help/en/id-service/using/intro/overview.html" format="html" scope="external"> Ytterligare information</a> </p> </td> 
    <td colname="col2"> <p> Det gick inte att hitta Experience Cloud ID-tjänstkoden. ECID rekommenderas för att du ska få ut så mycket som möjligt av dina Experience Cloud-lösningar och är viktigt för ID-hantering i olika EU-lösningar. </p> </td> 
    <td colname="col3"> <p>Installera den senaste versionen av MCID. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><b> Mål - Biblioteket har lästs in i &lt;head&gt;</b> </p> <p>Bredd: 4 </p> <p><a href="https://docs.adobe.com/content/help/en/target/using/implement-target/implementing-target.html" format="html" scope="external"> Ytterligare information</a> </p> 
     <!--
       TE61c380082a4b4706b28a84aa047599a7 
     --> </td> 
    <td colname="col2"> <p> Målbiblioteket ska läsas in i <span class="codeph"> &lt;head&gt;</span> -tagg. </p> </td> 
    <td colname="col3"> <p> Kontrollera att målbiblioteket har lästs in i <span class="codeph"> &lt;head&gt;</span> -tagg. </p> </td> 
   </tr> 
  </tbody> 
</table>
