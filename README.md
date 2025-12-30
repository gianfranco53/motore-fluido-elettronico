# ⚙️ Motore a Fluido Compresso – Prototipo "Colasanti"

**Progettista:** Gianfranco Colasanti  
**Stato del progetto:** Prototipo sperimentale (Proof of Concept)

---

## 📝 Descrizione e Obiettivi
Questo progetto rappresenta un prototipo sperimentale di **motore a pistoni alimentato a fluido compresso**, nato con l’obiettivo di dimostrare come una **gestione elettronica della distribuzione** possa superare alcuni limiti dei sistemi meccanici tradizionali (valvole, distributori, scambiatori meccanici).

Il progetto non nasce con finalità industriali, ma come **studio tecnico, sperimentazione personale e piattaforma didattica** per testare soluzioni alternative di controllo del ciclo motore.

---

## 🛠️ Architettura Meccanica

![Foto del Prototipo Reale](Foto_prototipo.jpeg)
*Il prototipo del motore assemblato.*

![Disegno Tecnico](motvap.jpg)
*Schema tecnico con le proporzioni dell'architettura meccanica (N.T.S.).*

**Componenti principali:**

- **Cilindro:** Tubo in acciaio (Ø esterno 64 mm), rettificato e lucidato internamente a specchio
- **Pistone:** Alluminio (Ø 28 mm, corsa 15 mm) per ridurre le masse alterne
- **Albero motore:** Costruito al tornio in tre elementi separati e assemblati con precisione
- **Biella:** Collegata tramite due micro-cuscinetti per ridurre al minimo le resistenze
- **Testata:** Alluminio con collettori da 3,5 mm e fori filettati passo 5 mm
- **Basamento:** Struttura fissata su supporto in legno per smorzare vibrazioni ad alta frequenza

---

## ⚡ Innovazione Elettronica

La distribuzione del fluido è gestita elettronicamente tramite **Arduino**, eliminando la necessità di distributori o scambiatori meccanici tradizionali.

**Caratteristiche principali:**

- **Sensori Hall:** Rilevamento preciso delle fasi PMS/PMI tramite magneti sull’albero (attrito nullo)
- **Distribuzione elettronica:** Controllo diretto delle elettrovalvole di spinta e scarico
- **Logica di “dead time”:** Introduzione di un breve ritardo tra le fasi per evitare corto-circuiti pneumatici
- **Efficienza:** Riduzione dello spreco di fluido e maggiore controllo della coppia

---

## 🚲 Prospettive Future

Il prototipo dimostra la fattibilità concettuale di un **propulsore ausiliario per bicicletta**, utilizzabile come:
- assistenza in salita
- freno motore elettronico in discesa
- possibile recupero energetico (concetto KERS sperimentale)

---

## ⚠️ Avvertenze e Responsabilità

Questo progetto è **puramente sperimentale**.

Chiunque utilizzi, replichi o modifichi questo progetto **lo fa a proprio rischio**.
L’autore **non fornisce alcuna garanzia** e **non è responsabile per danni a persone, cose o animali** derivanti dall’uso del progetto o delle informazioni qui contenute.

---

## 📜 Licenza e Utilizzo

© 2025 Gianfranco Colasanti – Tutti i diritti riservati.

Il progetto è condiviso **per scopi personali, didattici e di studio**.
È consentito:
- studiare il progetto
- sperimentare
- modificare per uso personale

⚠️ **Non è consentito alcun uso commerciale, industriale o produttivo** (anche parziale) **senza il consenso scritto dell’autore**.

Chiunque intenda:
- commercializzare
- industrializzare
- integrare il progetto in prodotti o servizi a pagamento

**deve contattare preventivamente l’autore.**

---

## 📫 Contatti

Se sei interessato a collaborare, approfondire gli aspetti tecnici o discutere possibili sviluppi:

- **Email:** [gianfr.colasanti@gmail.com](mailto:gianfr.colasanti@gmail.com)
- **GitHub:** tramite le *Issues* di questo repository
