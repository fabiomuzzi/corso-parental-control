# Modulo 2. La rete di casa: i filtri DNS

<p class="scheda-modulo">Tempo: circa 30 minuti. Ultima verifica: novembre 2026 (iOS 26, Android 16). Difficoltà: media, ma ti accompagno passo per passo.</p>

!!! abstract "In breve"
    - Il DNS è la "rubrica" di internet: quando scrivi il nome di un sito, il DNS trova l'indirizzo a cui collegarsi. Un DNS con **filtro famiglia** semplicemente non trova l'indirizzo dei siti per adulti e di quelli pericolosi.
    - Si può impostare **sul modem di casa** (protegge tutto ciò che usa il Wi-Fi) oppure **sul singolo telefono** (lo protegge anche fuori casa).
    - È gratuito, si fa una volta sola e non rallenta la connessione.
    - Non rompe niente: se qualcosa non ti convince, si torna indietro in un minuto.

!!! tip "Prima di cominciare: non puoi fare danni"
    Lo so, "DNS" e "pannello del modem" sembrano parole da tecnici. Ma qui non cambiamo nulla di irreversibile: scriviamo due numeri al posto di altri due. Prima di cambiarli ti faccio fotografare quelli vecchi, così puoi sempre rimetterli. La prima volta che l'ho fatto io ci ho messo più tempo a trovare la password del modem che a fare tutto il resto.

## Cosa ti serve
- Un computer o un telefono collegato al **Wi-Fi di casa**.
- La **password del modem** (non quella del Wi-Fi): di solito è su un'etichetta sotto o dietro il modem.
- Il telefono di tuo figlio, se vuoi fare anche il passo 3.
- Dieci minuti in cui nessuno in casa stia guardando un film in streaming: per un attimo la connessione potrebbe interrompersi.

## Passo 1. Scegli il filtro
Ti propongo tre servizi, tutti con un'opzione gratuita. Se non sai quale scegliere, **parti da Cloudflare for Families**: è il più semplice e non richiede nessuna registrazione.

| Servizio | Cosa blocca | Si può personalizzare? | Costo | Te lo consiglio se... |
|---|---|---|---|---|
| **Cloudflare for Families** | Siti per adulti e pericolosi | No | Gratis | ...vuoi impostarlo e non pensarci più |
| **CleanBrowsing Family** | Siti per adulti e pericolosi, VPN; attiva la ricerca sicura su Google, Bing e YouTube | No (sì a pagamento) | Gratis | ...hai figli piccoli |
| **NextDNS** | Quello che scegli tu: categorie, singoli siti, singole app, orari | Sì, da un pannello web | Gratis fino a 300.000 richieste al mese | ...vuoi decidere nel dettaglio e vedere le statistiche |

Gli indirizzi da copiare:

- **Cloudflare for Families**
    - DNS primario: `1.1.1.3`
    - DNS secondario: `1.0.0.3`
    - nome per i telefoni: `family.cloudflare-dns.com`
- **CleanBrowsing Family**
    - DNS primario: `185.228.168.168`
    - DNS secondario: `185.228.169.168`
    - nome per i telefoni: `family-filter-dns.cleanbrowsing.org`
- **NextDNS**: indirizzi e nome sono personali, li trovi nel tuo profilo su nextdns.io dopo esserti registrato.


## Passo 2. Imposta il filtro sul modem
È la soluzione migliore: copre anche smart TV, console, tablet e i telefoni degli amici che vengono a casa.

1. **Apri il pannello del modem.** Dal computer o dal telefono collegato al Wi-Fi apri il browser e scrivi nella barra degli indirizzi `192.168.1.1` (se non funziona, prova `192.168.0.1`, oppure leggi l'indirizzo sull'etichetta del modem).
2. **Entra con la password del modem.** È quella sull'etichetta, non quella del Wi-Fi.

    <div class="foto-segnaposto" markdown>**FOTO DA INSERIRE:** la pagina di accesso del tuo modem. *File suggerito: `img/modulo-2/01-accesso-modem.jpg`*</div>

3. **Cerca le impostazioni del DNS.** Ogni modem le chiama in modo diverso: guarda nelle voci **Rete locale**, **LAN**, **DHCP**, **Impostazioni avanzate** o **Internet**. Cerca due caselle chiamate "DNS primario" e "DNS secondario".

    <div class="foto-segnaposto" markdown>**FOTO DA INSERIRE:** la schermata del modem con le caselle del DNS, prima della modifica. *File suggerito: `img/modulo-2/02-dns-modem-prima.jpg`*</div>

4. **Fotografa i valori attuali** con il telefono. Se un giorno vorrai tornare indietro, ti basterà riscriverli.
5. **Scrivi i nuovi indirizzi** del servizio che hai scelto (per Cloudflare: `1.1.1.3` e `1.0.0.3`) e premi **Salva** o **Applica**.

    <div class="foto-segnaposto" markdown>**FOTO DA INSERIRE:** la stessa schermata con i nuovi indirizzi. *File suggerito: `img/modulo-2/03-dns-modem-dopo.jpg`*</div>

6. **Fai ricollegare i dispositivi.** Il modo più semplice è spegnere e riaccendere il Wi-Fi su ogni telefono e computer. In alternativa riavvia il modem.

!!! info "E se il mio modem non ha queste caselle?"
    Succede spesso con i modem forniti dagli operatori, e non è colpa tua. Hai tre strade, tutte valide:

    - chiedi all'operatore il **parental control gratuito per la linea di casa**, che è obbligato a offrirti (te lo spiego nel [modulo 5](sim-operatore.md));
    - imposta il filtro **direttamente sui dispositivi dei figli** (passo 3 qui sotto);
    - se te la senti, collega al modem un router tuo, su cui il DNS si può cambiare.

## Passo 3. Imposta il filtro sul telefono di tuo figlio
Questo passo protegge il telefono anche quando usa i dati mobili o il Wi-Fi di altri.

### Su Android (dalla versione 9 in poi)
1. Apri **Impostazioni**.
2. Tocca **Rete e Internet** (sui Samsung: **Connessioni**, poi **Altre impostazioni di rete**).
3. Tocca **DNS privato**.
4. Scegli **Nome host del provider DNS privato**.
5. Scrivi il nome del servizio scelto, per esempio `family.cloudflare-dns.com`, e tocca **Salva**.

    <div class="foto-segnaposto" markdown>**FOTO DA INSERIRE:** la schermata "DNS privato" su Android con il nome inserito. *File suggerito: `img/modulo-2/04-android-dns-privato.jpg`*</div>

Nel modulo 4, con Family Link, faremo in modo che questa impostazione non si possa cambiare.

### Su iPhone e iPad
Su iPhone il DNS si può cambiare in due modi.

**Solo per il Wi-Fi di casa (più semplice):**
1. Apri **Impostazioni** e tocca **Wi-Fi**.
2. Tocca la **(i)** accanto al nome della tua rete.
3. Scorri fino a **Configura DNS** e scegli **Manuale**.
4. Elimina i server presenti (tocca il cerchio rosso) e aggiungi i due indirizzi del servizio scelto.
5. Tocca **Salva**.

    <div class="foto-segnaposto" markdown>**FOTO DA INSERIRE:** la schermata "Configura DNS" su iPhone. *File suggerito: `img/modulo-2/05-iphone-configura-dns.jpg`*</div>

**Per tutte le reti, dati mobili compresi:** serve un "profilo di configurazione", un piccolo file che il servizio prepara per te. NextDNS e CleanBrowsing lo offrono dal loro sito.
1. Dal telefono di tuo figlio apri in Safari la pagina del servizio che genera il profilo.
2. Scarica il profilo e conferma.
3. Apri **Impostazioni**: in alto compare **Profilo scaricato**. Toccalo e poi tocca **Installa**.

    <div class="foto-segnaposto" markdown>**FOTO DA INSERIRE:** la schermata "Installa profilo" su iPhone. *File suggerito: `img/modulo-2/06-iphone-profilo.jpg`*</div>

Nel modulo 3, con Tempo di utilizzo, faremo in modo che il profilo non si possa togliere.

### Sul computer
- **Windows 11:** Impostazioni > Rete e Internet > Wi-Fi (o Ethernet) > Proprietà della rete > Assegnazione server DNS > Modifica > Manuale.
- **Mac:** Impostazioni di Sistema > Wi-Fi > Dettagli accanto alla rete > DNS > aggiungi i due indirizzi con il pulsante +.

## Passo 4. Controlla che funzioni
1. Spegni e riaccendi il Wi-Fi sul dispositivo che vuoi controllare.
2. Prova ad aprire un sito che dovrebbe essere bloccato: deve comparire un **errore di connessione** (o una pagina di blocco), non il sito.
3. Con CleanBrowsing, fai una ricerca su Google: deve risultare attiva la **SafeSearch**.
4. Con NextDNS, apri `test.nextdns.io`: deve comparire **status: ok**.

    <div class="foto-segnaposto" markdown>**FOTO DA INSERIRE:** come appare un sito bloccato sul tuo telefono. *File suggerito: `img/modulo-2/07-sito-bloccato.jpg`*</div>

!!! success "Fatto!"
    Se il test è andato bene, la rete di casa ha il suo primo strato di protezione. Ci hai messo mezz'ora, e da oggi lavora da solo.

## Cosa il filtro DNS non fa
Te lo dico con onestà, perché è meglio saperlo adesso che scoprirlo dopo:

- **Fuori casa** non funziona, se l'hai messo solo sul modem. Per questo c'è il passo 3, e c'è il [modulo 5](sim-operatore.md) sulla SIM.
- **Le VPN** e le app che promettono di "sbloccare" i siti lo possono aggirare. CleanBrowsing e NextDNS ne bloccano molte, non tutte. L'installazione di app la controlliamo nei moduli 3 e 4.
- **Il Relay privato di iCloud** su iPhone, se attivo, fa usare a Safari un altro DNS. Si disattiva da Impostazioni > il tuo nome > iCloud > Relay privato.
- **Non vede le chat.** Il filtro ferma i siti, non le persone. Ed è per questo che la guida comincia dal [modulo 0](prima-delle-impostazioni.md).

Non è un motivo per lasciar perdere: è il motivo per cui il DNS è il primo strato, non l'unico.

## Verifica: hai finito il modulo?
Spunta quello che hai fatto:

- [ ] Ho scelto un servizio di filtro DNS.
- [ ] Ho fotografato i valori DNS originali del modem (o ho scoperto che il modem non permette di cambiarli).
- [ ] Ho impostato il filtro sul modem, oppure sui dispositivi dei figli.
- [ ] Ho fatto la prova: un sito che doveva essere bloccato non si apre.
- [ ] Sull'iPhone di mio figlio ho controllato il Relay privato di iCloud.

Tre domande per controllare di aver capito:

??? question "1. Ho messo il filtro sul modem. Mio figlio esce e usa i dati mobili: è protetto?"
    No. Il filtro sul modem protegge solo chi usa il **Wi-Fi di casa**. Fuori casa servono il filtro sul telefono (passo 3) e il parental control della SIM ([modulo 5](sim-operatore.md)).

??? question "2. Ho cambiato il DNS e internet non va più. Cosa faccio?"
    Niente panico: rientra nel pannello del modem e riscrivi i valori che avevi fotografato (o cancella i nuovi e lascia le caselle vuote, che di solito vuol dire "automatico"). Poi riavvia il modem. Tutto torna come prima.

??? question "3. Il filtro DNS legge le chat di mio figlio?"
    No, e non è fatto per questo. Blocca l'accesso ai **siti**, non vede i messaggi. Per le persone che scrivono a tuo figlio conta il patto del [modulo 0](prima-delle-impostazioni.md).

## Fonti e guide ufficiali
- Cloudflare, 1.1.1.1 for Families: developers.cloudflare.com/1.1.1.1/setup/#1111-for-families
- CleanBrowsing, filtri e indirizzi: cleanbrowsing.org/filters
- NextDNS, piani: nextdns.io/pricing
- Google, Assistenza Android: modificare le impostazioni del DNS privato
- Apple, Supporto: informazioni su Relay privato di iCloud
