# ⚙️ Motore a Fluido Compresso - Prototipo "Colasanti"

**Progettista:** Gianfranco Colasanti | **Stato:** Prototipo Sperimentale (Proof of Concept)
**Performance raggiunte:** 1200 RPM | **Sistema di controllo:** Arduino Uno

---

### 🚀 1. Descrizione del Progetto: Motore Fluido Elettronico (M.F.E.)

Il progetto M.F.E. nasce dalla necessità di superare i limiti di efficienza dei motori pneumatici a distribuzione meccanica. L'innovazione principale consiste nell'eliminazione totale dell'albero a camme, sostituito da un **sistema di gestione elettronica a fasatura variabile**. 

Arduino decide, in base alla lettura dei sensori, l'istante esatto di immissione e scarico del fluido. Questo permette di eliminare gli attriti meccanici e di ottimizzare il consumo d'aria, risolvendo il problema del "corto circuito pneumatico" (fuoriuscita del fluido prima del lavoro utile).

---

### 🛠️ 2. Architettura Meccanica e Design

Il motore è costruito con materiali ferrosi e alluminio, rifinito al tornio per garantire la massima precisione dei componenti rotanti.

| Componente | Specifiche Tecniche |
| :--- | :--- |
| ![Foto Prototipo](Foto_prototipo.jpeg) | **Cilindro:** Tubo in acciaio da 64 mm, interno **lappato a specchio** per la massima tenuta pneumatica. |
| ![Disegno Tecnico](motvap.jpg) | **Pistone:** Alluminio (Ø 28 mm, corsa 15 mm) per ridurre le masse alterne e le inerzie. |
| **Albero Motore** | Costruito in **3 pezzi separati**, assemblati a pressione e bilanciati al tornio. |
| **Biella** | Montata su **2 micro-cuscinetti**, eliminando le resistenze delle bronzine tradizionali. |
| **Testata** | In alluminio con collettori da 3.5 mm e fori filettati passo 5 mm. |
| **Volano** | Realizzato con l'unione a pressione di **4 rondelle in acciaio da 50 mm**. |

---

### ⚡ 3. Sistema di Timing ed Elettronica

La distribuzione "Cam-less" è resa possibile da una lettura magnetica della fase:

* **Sensori di Hall (3144):** Posizionati davanti al volano, rilevano il passaggio di **4 magneti al neodimio** (tutti con la stessa polarità).
* **Regolazione Fase:** L'anticipo non è fisso; può essere regolato fisicamente spostando i magneti sul volano per trovare lo "sweet spot" di massima coppia.
* **Logica "Dead Time":** Il software garantisce un ritardo di sicurezza (500 microsecondi) tra la chiusura di una valvola e l'apertura della successiva per massimizzare la pressione utile nel cilindro.

---

### 💻 4. Codice di Controllo (Logic Core)

Il sistema utilizza una logica a interrupt o lettura di fronte per gestire le elettrovalvole. Di seguito un estratto della logica di gestione:

```cpp
// Estratto logica di controllo valvole
if (pms && !prevPMS) {
    digitalWrite(pinEVSpinta, HIGH);   // Apertura valvola spinta
    digitalWrite(pinEVScarico, LOW);   // Sicurezza: scarico chiuso
    spintaAttiva = true;
    tSpinta = millis();
}
// Chiusura automatica dopo durata programmata via potenziometro
if (spintaAttiva && (millis() - tSpinta >= durataSpinta)) {
    digitalWrite(pinEVSpinta, LOW);
    spintaAttiva = false;
}
