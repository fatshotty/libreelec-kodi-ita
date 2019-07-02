# LibreElec 9.0 kodi iso

Questa è una iso di libreElec con kodi 18 Leia configurato e pronto all'uso. Ci sono già gli addon e i servizi configurati e avviati per l'utilizzo.
La iso sarà presto on line [a questo link](https://mega.nz/#!J08UxAwK!y7Qfe1qjsCd2vvZO9-ZJDjZISp_ka0a7cPkEVtii6MI)


# Addons

- [KodiLive TV e Koditeka](http://kodilive.eu)
- [Emby e EmbyCon](https://emby.media/)
- [TvHeadEnd](https://tvheadend.org/)
- [KoD](https://kodiondemand.github.io/)
- [Elementum](https://howtomediacenter.com/en/install-elementum-kodi/)
- [Opensubtitles](https://www.opensubtitles.org/it/it)

## Struttura cartelle

- `/storage/video/Movies`
cartella dei film
- `/storage/video/Shows`
cartella delle serie tv
- `/storage/music`
cartella dei file musicali

## Skin
La skin configurata è [Aura](https://kodi.tv/addon/skins/aura).
Una volta avviato LibreElec occorre impostare la rete. **Solo dopo aver impostato la connessione di rete** andare nelle impostazioni della skin e scegliere *Aura*.
Le sezioni già abilitate sono:

- Live TV (in base al PVR scelto)
- Film (libreria basata su Emby Server)
   - Cerca on Demand (link diretto alla ricerca su KoD)
   - Cerca torrent (link diretto per la ricerca 'film' su Elementum)
   - Koditeka (link diretto alla sezione 'Film' di koditeka)
   - Link on demand (link alla sezione 'I miei link - Film' di KoD)
 - Serie Tv (libreria basata su Emby Server)
    - Cerca on Demand (link diretto alla ricerca su KoD)
   - Cerca torrent (link diretto per la ricerca 'serie tv' su Elementum)
   - Koditeka (link diretto alla sezione 'Serie Tv' di koditeka)
   - Link on demand (link alla sezione 'I miei link - Serie tv' di KoD)
 - Preferiti
 - Addons
 - Power e Meteo

## SSH abilitato
Il servizio ssh è già abilitato: `root`/`libreelec`

## Emby Server
Emby è studiato per fornire in tutta la rete locale (ma anche da remoto) l'intera libreria multimediale che gestisce. Pertanto è in grado di gestire Film, Musica e SerieTV, preoccupandosi di tenere le cartelle sincronizzate e aggiornate con i metadati necessari.
La libreria multimediale di Kodi è interamente gestita da Emby.
Per organizzare e modificare la libreria accedere via browser (o via app) a http://ip_raspberry:8096 `root`/`libreelec`
ATTENZIONE: **non utilizzare i comandi di Kodi per aggiornare la libreria**, collegarsi ad Emby (tramite browser o app) per aggiornare/modificare/gestire le librerie


## PVR Simple Client
Di default viene usato `PVR Simple Client` di Kodi. Il PVR e' configurator con la lista di KLTV. L'EPG viene preso da [EPG Italia](http://epgitalia.it).
Se si è in possesso di una lista IPTV è possibile sostituire il PVR con TvHeadEnd, da abilitare tra gli addons già installati


## TvHeadEnd
In alternativa a PVR Simple Client è possibile utilizzare TvHeadEnd, solo se si è in possesso di una lista iptv personale con link diretti. TvHeadEnd non è in grado di utilizzare link che seguono i redirect.
TvHeadEnd è già configurato con la lista dei canali più comuni. Se si desidera effettuare alcune modifiche occorre collegarsi via browser a http://[ip_raspberry]:9981
Le credenziali di accesso sono `libreelec`/`libreelec`
ATTENZIONE: ogni link del canale è stato impostato tramite un ulteriore servizio: `tv-channels-manager`


## TvChannelsManager
È un servizio scritto in `node-js` che consente di gestire liste canali iptv _m3u_ e il relativo _epg_.
Collegarsi via browser a http://[ip_raspberry]:3000 per abilitare le configurazioni di base.
Nella schermata HOME è possibile inserire l'url (remoto o locale) della lista IPTV che si possiede. In questo modo è possibile abilitare TvHeadEnd affinchè la lista dei canali venga servita tramite TvHeadEnd ai vari client connessi (kodi addon/mobile app ...)
ATTENZIONE: quando si vuole aggiungere/modificare un canale in TvHeadEnd, fare riferimento all'url esposto da TvChannelsManager. Questo perchè, se in futuro si decide di cambiare lisa iptv, sarà possibile farlo senza necessariamente cambiare url in TvHeadEnd.
in poche parole TvChannelsManager fa da proxy per gli url dei canali.
Inoltre suddivide la lista m3u in gruppi accessibili tramite il `Playlist Manager` di KLTV.
Altri dettagli disponibili [qui](https://www.npmjs.com/package/tv-channels-manager-ita).
Per aggiornare il servizio collegarsi via SSH, andare nella cartella `/storage/tv-channels-manager` e lanciare il comando `npm update` o `npm install tv-channels-manager-ita` e riavviare il raspberry.

## Opensubtitles
Questo addon permette di abilitare i sottotitoli. Account già impostato: `elecsubtitles`/`libreelec`



## Aiuto
La iso sarà soggetta ad aggiornamenti e nuove configurazioni.
Per info e/o aiuto contattatemi pure su telegram @fatshotty oppure aprite le issue qui :)
