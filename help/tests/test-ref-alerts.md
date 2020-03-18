---
description: Denna referens innehåller mer information om de larm som granskaren visar för test.
seo-description: Denna referens innehåller mer information om de larm som granskaren visar för test.
seo-title: Varningar
title: Varningar
uuid: 8f05b3c1-2427-4691-a88f-1de98f120a02
translation-type: tm+mt
source-git-commit: 762ff31ca4d5ed69d1b813589e419c51a40d5920

---


# Varningar{#alerts}

Denna referens innehåller mer information om de larm som granskaren visar för test.

Varningar visar problem som du bör vara medveten om, men som inte påverkar ditt poängtal. Det här är rekommendationer om god praxis som i vissa fall kanske inte gäller din implementering.

<table id="table_031432C9BB804A6F90E7FF572739E169"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Testa </th> 
   <th colname="col2" class="entry"> Kriterier </th> 
   <th colname="col3" class="entry"> Rekommendation </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Advertising Cloud - Korrigera konverteringstagg implementerad</b> </p> <p>Bredd: 0 </p> </td> 
   <td colname="col2"> <p>Kontrollera om rätt konverteringstagg används. </p> <p> <p>Varning:  Om du använder de föråldrade konverteringstaggarna för TubeMogul kan data gå förlorade. </p> </p> </td> 
   <td colname="col3"> <p>Uppgradera dina konverteringspixlar till de nya konverteringstaggarna för endast Advertising Cloud-bilder. </p> <p>Det är enklast att göra med Advertising Cloud Launch Extension. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Advertising Cloud - Korrigera JS-tagg som används</b> </p> <p>Bredd: 0 </p> </td> 
   <td colname="col2"> <p>Advertising Cloud bör använda de senaste JavaScript-taggarna. </p> </td> 
   <td colname="col3"> <p>Uppgradera ditt Advertising Cloud JavaScript till den senaste versionen. Om du använder de inaktuella JavaScript-versionerna kan du förlora funktioner. </p> <p>Detta kan göras enklare med hjälp av Advertising Cloud Launch Extension. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Advertising Cloud - Tagg för endast bilder</b> </p> <p>Bredd: 0 </p> </td> 
   <td colname="col2"> <p>Advertising Cloud-bildens pixelformat bör matcha något av följande rekommenderade format: </p> <p> 
     <ul id="ul_D85BE9C8A8654DE890E1A814E3573D86"> 
      <li id="li_E2AEDD76AC7044E8AD6AE8375858D198"> <p><span class="codeph"> /rtd.tubemogul.com/upi/?sid=&lt;HASH_VALUE&gt;</span> </p> </li> 
      <li id="li_1EEFA03516BF445294B5EC5DED891758"> <p><span class="codeph"> /rtd-tm.everesttech.net/upi/?sid=&lt;HASH_VALUE&gt;</span> </p> </li> 
      <li id="li_F72206B142214217BDD34356D2F3D8AD"> <p><span class="codeph"> /pixel.everesttech.net/px2/&lt;NUMERIC_ID&gt;?</span> </p> </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Uppgradera dina Advertising Cloud-pixlar till de nya Advertising Cloud-taggarna som säkerställer att du drar nytta av den fullständiga funktionen i Advertising Cloud. </p> <p>Det är enklast att göra med Advertising Cloud Launch Extension. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Advertising Cloud - Synkronisering av segmentpixlar för DSP aktiverad</b> </p> <p>Bredd: 0 </p> </td> 
   <td colname="col2"> <p>Kontrollera om TubeMogul-segmentpixeln innehåller en DSP-synkroniseringsinställning och rekommendera att inställningen läggs till i pixeln. </p> <p>Inställningen för DSP-synkronisering bestäms av användningen av en frågesträngsparameter, så </p> <p>OM taggen skickas till<span class="codeph"> ("https://rtd.tubemogul.com/upi/?sid=&lt;HASH_VALUE&gt;")</span> </p> <p> ELLER <span class="codeph"> "/rtd-tm.everesttech.net/upi/?sid=&lt;HASH_VALUE&gt;"</span> </p> <p> ELLER <span class="codeph"> "http(s)://pixel.everesttech.net/px2/&lt;NUMERIC_ID&gt;?"</span> </p> <p>OCH taggen innehåller URL-parametern <span class="codeph"> "sid=")</span> </p> <p>Kontrollera sedan om URL-parametern <span class="codeph"> "cs=0"</span> eller<span class="codeph"> "cs=1"</span> finns och om den inte rekommenderar att <span class="codeph"> "cs=1"</span> läggs till i pixlarna så att målgruppens matchningsfrekvens kan förbättras. </p> </td> 
   <td colname="col3"> <p> Lägg till URL-parametern <span class="codeph"> "cs=1"</span> i dina Advertising Cloud-pixlar så att DSP-synkronisering kan ske, vilket ökar målgruppernas matchningsfrekvens. </p> <p>Det är enklast att göra detta med Advertising Cloud Launch Extension. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      CAce6db25bc8c443409f0fcc5ac9d622c3 
    </draft-comment> <p><b>DTM - sidans nedre återanropsplacering</b> </p> <p>Bredd: 0 </p> <p><a href="https://experiencecloud.adobe.com/resources/help/en_US/dtm/t_add_header_fooder_code.html" format="html" scope="external"> Ytterligare information</a> </p> 
    <draft-comment>
      TEa9df69942f404055a64262889c8b21d3 
    </draft-comment> </td> 
   <td colname="col2"> <p>Dynamisk tagghantering kräver funktionen <span class="codeph"> _satellit.pageBottom()</span> . Lägg till det infogade skriptet omedelbart före den avslutande <span class="codeph"> &lt;/body&gt;</span> -taggen för att säkerställa korrekt DTM-funktionalitet. </p> <p> <p>Obs! Det är bäst att använda taggen som den <i>sista</i> taggen i <span class="codeph"> &lt;body&gt;</span>. Om den hittas i <span class="codeph"> &lt;body&gt;</span> -taggen har den en chans att fungera, men eftersom det inte är en bra metod kan den fungera felaktigt eller med oväntade eller oönskade resultat. </p> </p> </td> 
   <td colname="col3"> <p>Lägg till det infogade skriptet omedelbart före den avslutande <span class="codeph"> &lt;/body&gt;</span> -taggen för att säkerställa korrekt DTM-funktionalitet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>DTM - Self-Hosted</b> </p> <p>Bredd: 0 </p> <p><a href="https://experiencecloud.adobe.com/resources/help/en_US/dtm/deployment.html" format="html" scope="external"> Ytterligare information</a> </p> </td> 
   <td colname="col2"> <p> DTM-biblioteket ligger på Adobes Akamai-instans på <span class="filepath"> assets.adobedtm.com</span>. </p> <p> Självvärdande är det rekommenderade sättet att läsa in DTM eftersom det ger bättre kontroll över webbplatsens prestanda genom cachekontroll, minskar beroenden av skript från tredje part och ger större kontroll över publiceringsprocessen. DTM-biblioteken kan hanteras via din egen webbhosting eller CDN. </p> </td> 
   <td colname="col3"> <p>Självvärdande är det rekommenderade sättet att läsa in DTM på en sida. Även om DTM-värdtjänster via Akamai CDN fungerar i de flesta fall, förbättras sidprestanda av självvärdtjänster. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b> Experience Cloud ID Service - använd bara en AdobeOrg</b> </p> <p>Bredd: 0 </p> <p><a href="https://experiencecloud.adobe.com/resources/help/en_US/mcvid/mcvid_id_request.html" format="html" scope="external"> Ytterligare information</a> </p> </td> 
   <td colname="col2"> <p>I en normal MCID-implementering bör en enda AdobeOrg användas. </p> </td> 
   <td colname="col3"> <p>Verifiera att det finns flera AdobeOrg ID:n för den här implementeringen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.5 
    </draft-comment> <p><b>Launch - pageBottom callback placement</b> </p> <p>Bredd: 0 </p> <p><a href="https://docs.adobelaunch.com/getting-started" format="https" scope="external"> Ytterligare information</a> </p> 
    <draft-comment>
      TE48c499b022f545c5bccc6f8bde169685 
    </draft-comment> </td> 
   <td colname="col2"> <p>Launch ska ha en <span class="codeph"> pageBottom- </span>callback-funktion som är sist definierad i sidans brödtext om den distribueras synkront. </p> <p> <p>Obs! Det är bäst att använda taggen som den <i>sista</i> taggen i <span class="codeph"> &lt;body&gt;</span>. Om den hittas i <span class="codeph"> &lt;body&gt;</span> -taggen har den en chans att fungera, men eftersom det inte är en bra metod kan den fungera felaktigt eller med oväntade eller oönskade resultat. </p> </p> </td> 
   <td colname="col3"> <p>Launch kräver funktionen <span class="codeph"> _satellit.pageBottom()</span> för synkrona distributioner. Lägg till det infogade skriptet omedelbart före den avslutande <span class="codeph"> &lt;/body&gt;</span> -taggen för att säkerställa rätt startfunktion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Launch - Self-Hosted</b> </p> <p>Bredd: 0 </p> <p><a href="https://docs.adobelaunch.com/getting-started" format="https" scope="external"> Komma igång med Launch</a> </p> <p><a href="https://docs.adobelaunch.com/client-side-information/asynchronous-deployment" format="https" scope="external"> Starta asynkron distribution</a> </p> </td> 
   <td colname="col2"> <p>Startbiblioteket ligger på Adobes Akamai-instans på <span class="filepath"> assets.adobedtm.com</span>. </p> <p>Självvärdande är det rekommenderade sättet att läsa in Launch eftersom det ger bättre kontroll över webbplatsens prestanda genom cachekontroll, minskar beroenden av skript från tredje part och ger större kontroll över publiceringsprocessen. Launch-biblioteken kan hanteras via din egen webbhosting eller CDN. </p> </td> 
   <td colname="col3"> <p>Även om Launch-värdtjänster via Akamai CDN fungerar i de flesta fall rekommenderar vi att självvärdtjänster implementeras som ett första steg i att förbättra sidans prestanda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Launch - ska distribueras asynkront</b> </p> <p>Bredd: 0 </p> <p><a href="https://docs.adobelaunch.com/getting-started" format="https" scope="external"> Ytterligare information</a> </p> </td> 
   <td colname="col2"> <p>Launch ska distribueras asynkront för optimala prestanda. </p> </td> 
   <td colname="col3"> <p>Inkludera parametern async i det infogade skriptet för att säkerställa korrekt asynkron start-funktion </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b> Mål - Innehåll i mboxDefault</b> </p> <p>Bredd: 0 </p> <p><a href="https://experiencecloud.adobe.com/resources/help/en_US/target/ov2/r_target-atjs-mboxcreate.html" format="html" scope="external"> Ytterligare information</a> </p> </td> 
   <td colname="col2"> <p> Innehållet ska finnas i mboxDefault när at.js används. </p> </td> 
   <td colname="col3"> <p>Kontrollera att innehållet är tillgängligt. </p> </td> 
  </tr> 
 </tbody> 
</table>
