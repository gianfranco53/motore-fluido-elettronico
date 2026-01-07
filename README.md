
**Vantaggi di questa architettura:**
*   **Fasatura Variabile Ottimale:** Il timing di immissione e scarico può essere regolato via software per massimizzare la coppia a qualsiasi regime.
*   **Eliminazione del Corto Circuito:** Grazie alla precisione digitale, è possibile implementare un **"dead time"** garantendo la chiusura di una valvola prima dell'apertura dell'altra.
*   **Riduzione degli Attriti:** Vengono eliminati tutti i componenti della distribuzione meccanica (albero a camme, punterie, molle).
*   **Flessibilità Assoluta:** La logica di controllo è un software, modificabile ed evolvibile a piacere.

---

## 🛠️ 4. Dettaglio Tecnico del Prototipo "Colasanti"

### 4.1 Architettura Meccanica di Precisione
Il motore è progettato per minimizzare le perdite per attrito e le masse inerziali.

| Componente | Specifiche Tecniche e Note Costruttive |
| :--- | :--- |
| **Cilindro** | Tubo in acciaio (Ø esterno 30 mm, lunghezza 64 mm), interno **lappato a specchio** per garantire la massima tenuta del pistone e minimizzare l'attrito radente. |
| **Pistone** | Realizzato in alluminio (Ø28 mm, corsa 15 mm) per **ridurre le masse alterne**, limitando le forze d'inerzia e consentendo regimi più elevati. |
| **Albero Motore** | Costruzione innovativa in **3 pezzi separati**, assemblati a pressione e **bilanciati staticamente al tornio** per garantire una rotazione perfettamente fluida. |
| **Biella** | Montata su **2 micro-cuscinetti a sfere** anziché bronzine, eliminando quasi completamente l'attrito di rotolamento nel perno di manovella. |
| **Testata** | Fresata in alluminio, con collettori ottimizzati (Ø3.5 mm) e attacchi per le elettrovalvole. |
| **Volano** | Realizzato in un **unico blocco di ferro** (Ø48 mm, spessore 11 mm) per garantire la massima **inerzia rotazionale** e la stabilità del moto. |

## 🗺️ Disegno Meccanico di Assieme

Il disegno tecnico sottostante illustra la relazione spaziale e il montaggio dei componenti principali descritti nella tabella.

![Disegno Meccanico del Motore](motvap.jpg)

*Figura 2: Disegno tecnico dell'assieme meccanico. Sono identificabili il cilindro (esterno Ø30mm), l'assemblaggio pistone-biella, l'albero motore e il volano.*

### 4.2 Sistema di Timing ed Elettronica di Controllo
Il cuore del sistema "Cam-less".

*   **Sensori di Posizione:** Due **sensori a effetto Hall (modello 3144)** fissi rilevano il passaggio di **2 magneti al neodimio** incastonati nel volano. Entrambi i magneti hanno la stessa polarità per semplificare la lettura.
*   **Regolazione della Fasatura:** L'anticipo/successo dell'apertura delle valvole non è fissato dal software. Può essere **regolato fisicamente** spostando i magneti lungo la circonferenza del volano, permettendo di trovare sperimentalmente il "punto dolce" per la massima coppia. Il software gestisce poi l'apertura con un ritardo/preavviso rispetto a questo segnale di riferimento.
*   **Logica di Sicurezza "Dead Time":** Il firmware su Arduino garantisce un **ritardo programmato (es. 500 µs)** tra il comando di chiusura di una valvola e l'apertura della successiva. Questo elimina il corto circuito pneumatico, massimizzando la pressione utile sul pistone.
*   **Pilotaggio delle Valvole:** Arduino, tramite un semplice circuito driver a MOSFET, pilota direttamente **elettrovalvole bistabili** o monostabili adatte alle alte velocità di risposta richieste.

---

## 📊 5. Risultati Sperimentali e Analisi

### 5.1 Performance del Prototipo Pneumatico
*   **Regime Massimo Raggiunto:** **1200 RPM** alimentato esclusivamente ad aria compressa.
*   **Validazione del Concetto:** Il raggiungimento di questo regime, con rotazione stabile, **dimostra in modo inequivocabile la piena fattibilità del sistema di distribuzione elettronica "Cam-less"** per un motore a fluido.
*   **Efficienza Fluidodinamica:** L'assenza del caratteristico sibilo dell'aria persa (corto circuito) e la risposta immediata ai comandi confermano il **salto di qualità nell'uso del fluido motore**.

### 5.2 Lezione Appresa e Limite Identificato
I test hanno evidenziato il **limite fisico fondamentale** dell'aria compressa come vettore energetico: la sua **bassa densità energetica**.
*   **Problema:** Per un uso pratico esteso (es. la propulsione di una bicicletta), la quantità d'aria necessaria richiederebbe serbatoi troppo pesanti e voluminosi.
*   **Conclusione:** Il motore pneumatico puro, sebbene meccanicamente efficiente, è limitato dall'autonomia.

---

## 🔮 6. Sviluppo Futuro: Verso un Sistema Ibrido Aria/Calore

Per superare il limite dell'autonomia, il progetto si evolve mantenendo la rivoluzionaria architettura "Cam-less", ma cambiando fluido motore.

### 6.1 Concetto Ibrido
L'idea è utilizzare l'aria non più come unico fluido motore, ma come **vettore per un salto termico**.
1.  **Fase 1 (Immissione):** Una piccola quantità di **combustibile liquido (es. etanolo)** viene iniettata e miscelata con l'aria in ingresso.
2.  **Fase 2 (Accensione):** La miscela viene accesa (con candeletta o scintilla) all'interno del cilindro.
3.  **Fase 3 (Espansione Ibrida):** La combustione **riscalda violentemente l'aria**, causando un **ulteriore, drammatico aumento di pressione e volume**. È questa **espansione termica aggiuntiva** che fornisce la maggior parte del lavoro, moltiplicando potenza e autonomia.

### 6.2 Vantaggi della Piattaforma "Cam-less" per l'Ibrido
La transizione è favorita dall'architettura esistente:
*   **Controllo di Precisione:** Arduino gestisce già il timing. Basterà aggiungere i comandi per l'iniettore di combustibile e il sistema d'accensione, **sincronizzandoli perfettamente con la fasatura dell'aria**.
*   **Flessibilità:** La fasatura ottimale per la combustione è diversa da quella per l'aria pura. Con il sistema "Cam-less", questa **ottimizzazione è una semplice modifica software**.
*   **Meccanica Pronta:** La parte meccanica (cilindro, pistone, biella, albero) è già progettata per forze significative ed è pronta ad accogliere le maggiori sollecitazioni della combustione.

---

## 🧪 7. Stato Attuale, Test e Avvertenze

*   **Stato Attuale:** Il prototipo **puramente pneumatico** è completo, testato e funzionante. Lo **sviluppo del sistema ibrido** è nella fase di progettazione dei sottosistemi di iniezione e accensione.
*   **Test in Corso:** Prima di integrare la combustione nel motore, tutti i nuovi componenti (iniettore, accensione, logica di controllo) vengono testati in sicurezza su un **banco prova di combustione separato** ("misfire tube").
*   **⚠️ Avvertenze Sulla Sicurezza ⚠️**
    *   Questo progetto è **SPERIMENTALE** e si tratta di un prototipo di laboratorio.
    *   La manipolazione di **aria ad alta pressione**, **combustibili infiammabili** e **sistemi di combustione** comporta **rischi gravi** (esplosioni, incendi, proiezione di frammenti).
    *   **NON tentare di replicare o modificare questo progetto senza competenze specifiche in meccanica di precisione, elettronica di controllo e, soprattutto, senza le dovute precauzioni di sicurezza.**
    *   L'autore **declina ogni responsabilità** per danni a cose, persone o proprietà derivanti dall'uso improprio delle informazioni qui contenute.

---

## 📫 8. Contatti, Collaborazione e Licenza

*   **Autore:** Gianfranco Colasanti
*   **Contatto:** `gianfr.colasanti@gmail.com`
*   **Discussioni Tecniche:** Apri una **Issue** su questa repository GitHub per domande, suggerimenti o discussioni approfondite sul progetto.
*   **Licenza e Proprietà Intellettuale:** Questo progetto, nella sua documentazione e nel suo design, è un'opera dell'ingegno di Gianfranco Colasanti. La condivisione ha **scopo didattico e di ricerca**. Per qualsiasi uso che vada oltre la consultazione personale, **contattare l'autore**.

---

### ⚠️ Avvertenze e Responsabilità
Questo progetto è puramente sperimentale. La manipolazione di recipienti a pressione e gas infiammabili richiede competenze specifiche e massima cautela. L'autore declina ogni responsabilità per danni derivanti dall'applicazione delle informazioni qui illustrate.
