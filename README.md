# ⚙️ Motore a Fluido Compresso - Prototipo "Colasanti"

**Progettista:** Gianfranco Colasanti | **Stato:** Prototipo Sperimentale (Proof of Concept)

---
Abstract del Progetto: Motore Fluido Elettronico (M.F.E.)
Descrizione Generale Il progetto M.F.E. rappresenta una radicale evoluzione del motore a pistoni tradizionale. A differenza dei sistemi pneumatici o a combustione classica, questo prototipo elimina completamente l'albero a camme e i leveraggi meccanici della distribuzione, sostituendoli con un sistema di gestione elettronica intelligente basato su Arduino
### 🛠️ Architettura Meccanica di Precisione Il motore è costruito con tecniche di officina avanzate per massimizzare la resistenza e ridurre gli attriti:


Cilindro e Pistone: Cilindro in acciaio da 64 mm con interno lucidato a specchio per una tenuta pneumatica perfetta. Il pistone è in alluminio (Ø 28 mm) per ridurre le masse alterne.



Albero Motore e Biella: Albero costruito in 3 pezzi separati, assemblati a pressione e rettificati al tornio per una geometria perfetta. La biella ruota su 2 micro-cuscinetti, eliminando le resistenze delle bronzine.




Geometria: Lo spinotto sull'albero e la corsa sono perfettamente accoppiati a 14-15 mm.
---

### ⚡Innovazione Elettronica e Timing Il controllo del fluido è gestito digitalmente per eliminare gli sprechi tipici dei sistemi meccanici:



Sensori di Hall (3144): Rilevano la posizione dell'albero tramite magneti al neodimio sul volano (attrito zero).




Logica "Dead Time": Il software implementa un ritardo controllato tra le fasi di spinta e scarico per evitare il "corto circuito pneumatico", garantendo che l'aria non venga sprecata.


Distribuzione Cam-less: L'apertura delle valvole è affidata a elettrovalvole (o valvole a fungo nel nuovo design) pilotate da MOSFET via Arduino
---

Prospettive Future: Verso l'Ibrido
Il prototipo attuale nasce come propulsore ausiliario pneumatico per cicli. Sebbene la costruzione abbia confermato la validità del sistema — con un prototipo perfettamente funzionante e dotato di un'ottima coppia motrice — i test sul campo hanno evidenziato che l'autonomia basata sulla sola aria compressa non è ancora soddisfacente per un utilizzo pratico esteso.

Evoluzione del Progetto: L'attuale configurazione funge da base per lo sviluppo di un sistema ibrido Aria/GPL. L'obiettivo è superare i limiti di densità energetica dell'aria compressa pura sfruttando l'espansione termica. L'iniezione e la combustione del GPL permetteranno di riscaldare l'aria in ingresso, aumentandone drasticamente pressione e volume, trasformando il sistema in un propulsore a combustione assistita ad alta efficienza.

⚠️ AVVERTENZE E RESPONSABILITÀ
Questo progetto è puramente sperimentale. Chiunque scelga di replicare, utilizzare o modificare le soluzioni tecniche qui descritte lo fa a proprio ed esclusivo rischio. L'autore non fornisce alcuna garanzia, esplicita o implicita, e declina ogni responsabilità per danni a persone, animali o cose derivanti dall'applicazione delle informazioni o dall'uso dei prototipi qui illustrati. La manipolazione di recipienti a pressione e gas infiammabili richiede competenze specifiche e massima cautela.

---
Evoluzione e Prospettive Future Nato come prototipo sperimentale per la propulsione ausiliaria di biciclette, il progetto si sta evolvendo verso un sistema ibrido Aria/Gas

### 📜 PROPRIETÀ INTELLETTUALE E LICENZA
Il presente progetto è un'opera dell'ingegno di Gianfranco Colasanti. La documentazione, i disegni tecnici e la logica software sviluppata su piattaforma Arduino sono condivisi esclusivamente per scopi didattici e di ricerca.
---

### 📫 Contatti
* **Email:** [gianfr.colasanti@gmail.com](mailto:gianfr.colasanti@gmail.com)
* **GitHub:** Tramite le "Issues" di questo repository.
