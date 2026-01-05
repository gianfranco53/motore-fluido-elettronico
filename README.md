# ⚙️ Motore a Fluido Compresso - Prototipo "Colasanti"

**Progettista:** Gianfranco Colasanti | **Stato:** Prototipo Sperimentale (Proof of Concept)

---

### 🛠️ Architettura Meccanica e Design

| Visione del Progetto | Specifiche Tecniche |
| :--- | :--- |
| ![Foto Prototipo](Foto_prototipo.jpeg) <br><br> ![Disegno Tecnico](motvap.jpg) | **Cilindro:** Acciaio (64 mm) rettificato e lucidato a specchio.<br><br>**Pistone:** Alluminio (Ø 28 mm, corsa 15 mm).<br><br>**Albero Motore:** Tornito in 3 pezzi e assemblato di precisione.<br><br>**Biella:** Su 2 micro-cuscinetti (no bronzine).<br><br>**Testata:** Alluminio, collettori 3.5 mm, filettatura passo 5.<br><br>**Basamento:** Struttura su legno antivibrazione. |

---

### ⚡ Innovazione Elettronica
Il motore utilizza un sistema indipendente gestito da Arduino per eliminare lo spreco d'aria dei sistemi meccanici:
* **Sensori di Hall:** Lettura precisa della fase tramite magneti sull'albero (attrito zero).
* **Logica "Dead Time":** Il codice garantisce un ritardo di 500 microsecondi tra le fasi per evitare il corto circuito pneumatico.
* **Efficienza:** Ottimizzazione della coppia e riduzione drastica dei consumi di fluido.

---

Prospettive Future: Verso l'Ibrido
Il prototipo attuale nasce come propulsore ausiliario pneumatico per cicli. Sebbene la costruzione abbia confermato la validità del sistema — con un prototipo perfettamente funzionante e dotato di un'ottima coppia motrice — i test sul campo hanno evidenziato che l'autonomia basata sulla sola aria compressa non è ancora soddisfacente per un utilizzo pratico esteso.

Evoluzione del Progetto: L'attuale configurazione funge da base per lo sviluppo di un sistema ibrido Aria/GPL. L'obiettivo è superare i limiti di densità energetica dell'aria compressa pura sfruttando l'espansione termica. L'iniezione e la combustione del GPL permetteranno di riscaldare l'aria in ingresso, aumentandone drasticamente pressione e volume, trasformando il sistema in un propulsore a combustione assistita ad alta efficienza.

⚠️ AVVERTENZE E RESPONSABILITÀ
Questo progetto è puramente sperimentale. Chiunque scelga di replicare, utilizzare o modificare le soluzioni tecniche qui descritte lo fa a proprio ed esclusivo rischio. L'autore non fornisce alcuna garanzia, esplicita o implicita, e declina ogni responsabilità per danni a persone, animali o cose derivanti dall'applicazione delle informazioni o dall'uso dei prototipi qui illustrati. La manipolazione di recipienti a pressione e gas infiammabili richiede competenze specifiche e massima cautela.

---

### 📜 PROPRIETÀ INTELLETTUALE E LICENZA
Il presente progetto è un'opera dell'ingegno di Gianfranco Colasanti. La documentazione, i disegni tecnici e la logica software sviluppata su piattaforma Arduino sono condivisi esclusivamente per scopi didattici e di ricerca.
---

### 📫 Contatti
* **Email:** [gianfr.colasanti@gmail.com](mailto:gianfr.colasanti@gmail.com)
* **GitHub:** Tramite le "Issues" di questo repository.
