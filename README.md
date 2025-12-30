# ⚙️ Motore a Fluido Compresso – Prototipo "Colasanti"

**Progettista:** Gianfranco Colasanti  
**Stato del progetto:** Prototipo sperimentale (Proof of Concept)

---

## 📝 Descrizione e Obiettivi
Questo progetto rappresenta un prototipo sperimentale di **motore a pistoni alimentato a fluido compresso**, nato con l’obiettivo di dimostrare come una **gestione elettronica della distribuzione** possa superare alcuni limiti dei sistemi meccanici tradizionali.

Il progetto non nasce con finalità industriali, ma come **studio tecnico, sperimentazione personale e piattaforma didattica**.

---

## 🛠️ Architettura Meccanica

![Foto del Prototipo Reale](Foto_prototipo.jpeg)
*Il prototipo del motore assemblato.*

![Disegno Tecnico](motvap.jpg)
*Schema tecnico con le proporzioni dell'architettura meccanica.*

**Componenti principali:**

- **Cilindro:** Tubo in acciaio (Ø esterno 64 mm), rettificato e lucidato internamente a specchio
- **Pistone:** Alluminio (Ø 28 mm, corsa 15 mm) per ridurre le masse alterne
- **Albero motore:** Costruito al tornio in tre elementi separati e assemblati con precisione
- **Biella:** Collegata tramite due micro-cuscinetti per ridurre al minimo le resistenze
- **Testata:** Alluminio con collettori da 3,5 mm e fori filettati passo 5 mm
- **Basamento:** Struttura fissata su supporto in legno per smorzare vibrazioni

---

## ⚡ Innovazione Elettronica

La distribuzione del fluido è gestita elettronicamente tramite **Arduino**, eliminando la necessità di distributori meccanici.

- **Sensori Hall:** Rilevamento preciso delle fasi PMS/PMI tramite magneti sull’albero.
- **Distribuzione elettronica:** Controllo diretto delle elettrovalvole di spinta e scarico.
- **Logica di “dead time”:** Ritardo tra le fasi per evitare corto-circuiti pneumatici.

---

## 🚲 Prospettive Future

Il prototipo dimostra la fattibilità di un **propulsore ausiliario per bicicletta**:
- Assistenza in salita.
- Freno motore elettronico in discesa.
- Recupero energetico (KERS sperimentale).

---

## ⚠️ Avvertenze e Responsabilità

Questo progetto è **puramente sperimentale**. Chiunque lo replichi lo fa a proprio rischio. L’autore non è responsabile per danni a persone o cose.

---

## 📜 Licenza e Utilizzo

© 2025 Gianfranco Colasanti – Tutti i diritti riservati.
Uso consentito per scopi personali e didattici. **Vietato l'uso commerciale senza consenso scritto.**

---

## 📫 Contatti

- **Email:** [gianfr.colasanti@gmail.com](mailto:gianfr.colasanti@gmail.com)
- **GitHub:** tramite le *Issues* di questo repository
