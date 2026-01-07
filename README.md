# 🔩 Prototipo di Motore Pneumatico ad Alta Efficienza con Distribuzione Elettronica "Cam-less"

**Autore:** Gianfranco Colasanti | **Stato:** Prototipo Sperimentale (Proof of Concept) | **Ultimo Aggiornamento:** Gennaio 2026

---

## 🖼️ Il Prototipo Reale

![Foto del Prototipo Completato](Foto_prototipo.jpeg)

*Figura 1: Il prototipo sperimentale del motore "Cam-less". Sono visibili il cilindro, il volano con i magneti, i sensori Hall e l'elettronica di controllo.*

---

## 📖 1. Sommario Esecutivo & Premessa

Questo progetto nasce da una sfida ingegneristica precisa: **superare l'inefficienza intrinseca dei motori pneumatici tradizionali**. La soluzione proposta è radicale: l'eliminazione completa del sistema di distribuzione meccanico (albero a camme o cassetti), sostituito da un **sistema di gestione elettronica "Cam-less"** comandato da Arduino.

Questo documento si propone di guidare il lettore attraverso:
1.  I **fondamenti** di un motore pneumatico e i suoi limiti tradizionali.
2.  La **soluzione innovativa** implementata in questo prototipo.
3.  I **dettagli costruttivi** e i risultati sperimentali.
4.  La **roadmap futura** verso un sistema ibrido.

---

## ⚙️ 2. Introduzione: Cos'è un Motore Pneumatico e Quali sono i suoi Limiti?

### 2.1 Il Principio di Funzionamento
Un motore pneumatico converte l'energia potenziale dell'**aria compressa** in lavoro meccanico (rotazione di un albero). Il suo funzionamento è concettualmente simile a quello di un motore a scoppio:
1.  **Immissione:** L'aria ad alta pressione viene introdotta nella camera di espansione (cilindro).
2.  **Espansione:** L'aria si espande, spingendo il pistone.
3.  **Scarico:** L'aria esausta (a pressione più bassa) viene evacuata dal cilindro.
4.  **Trasformazione:** Il moto rettilineo del pistone viene convertito in moto rotatorio da un meccanismo biella-manovella.

### 2.2 Il Problema della Distribuzione Meccanica
Nei motori pneumatici tradizionali, la sequenza di immissione e scarico è governata da un **sistema di distribuzione meccanica**, come un albero a camme o una valvola a cassetto.

Questi sistemi presentano due grandi svantaggi:
*   **Fasatura Fissa:** I tempi di apertura e chiusura delle valvole sono predeterminati dalla geometria delle camme e non sono ottimizzabili in tempo reale.
*   **Corto Circuito Pneumatico:** Per garantire l'apertura e la chiusura nei momenti giusti anche ad alto regime, le valvole restano aperte per un periodo sovrapposto. Questo causa la **fuoriuscita di aria compressa direttamente verso lo scarico**, senza compiere lavoro utile, **riducendo drasticamente l'efficienza**.

**L'obiettivo di questo progetto è eliminare questi due problemi alla radice.**

---

## 🚀 3. L'Innovazione: Architettura "Cam-less" Elettronica

La soluzione è abbandonare la logica meccanica e adottare un **sistema di controllo dinamico e software-defined**.

### 3.1 Il Concetto Chiave
L'albero a camme viene sostituito da:
1.  **Sensori** che rilevano in tempo reale la posizione del pistone.
2.  Un **cervello elettronico** (Arduino) che decide, in base a questa lettura e a logiche programmabili, il momento esatto per agire.
3.  **Attuatori** (elettrovalvole) che aprono e chiudono i passaggi dell'aria su comando digitale.

### 3.2 Schema a Blocchi del Sistema

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

### 🗺️ Disegno Meccanico di Assieme

![Disegno Meccanico del Motore](motvap.jpg)

*Figura 2: Disegno tecnico dell'assieme meccanico. Sono identificabili il cilindro (esterno Ø30mm), l'assemblaggio pistone-biella, l'albero motore e il volano.*

### 4.2 Sistema di Timing ed Elettronica di Controllo
Il cuore del sistema "Cam-less".

*   **Sensori di Posizione:** Due **sensori a effetto Hall (modello 3144)** fissi rilevano il passaggio di **2 magneti al neodimio** incastonati nel volano. Entrambi i magneti hanno la stessa polarità per semplificare la lettura.
*   **Regolazione della Fasatura:** L'anticipo/successo dell'apertura delle valvole non è fissato dal software. Può essere **regolato fisicamente** spostando i magneti lungo la circonferenza del volano, permettendo di trovare sperimentalmente il "punto dolce" per la massima coppia. Il software gestisce poi l'apertura con un ritardo/preavviso rispetto a questo segnale di riferimento.
*   **Logica di Sicurezza "Dead Time":** Il firmware su Arduino garantisce un **ritardo programmato (es. 500 µs)** tra il comando di chiusura di una valvola e l'apertura della successiva. Questo elimina il corto circuito pneumatico, massimizzando la pressione utile sul pistone.
*   **Pilotaggio delle Valvole:** Arduino, tramite un semplice circuito driver a MOSFET, pilota direttamente **elettrovalvole bistabili** o monostabili adatte alle alte velocità di risposta richieste.

---

## 📊 5. Risultati Sperimentali, Stato Attuale e Analisi

### 5.1 Performance e Validazione del Concetto
Il prototipo ha dimostrato in modo inequivocabile la **piena fattibilità del sistema di distribuzione elettronica "Cam-less"**.

*   **Validazione del Principio:** Il motore è in grado di funzionare in modo stabile e autonomo, trasformando l'energia dell'aria compressa in rotazione meccanica, **senza alcun componente di distribuzione meccanica tradizionale**.
*   **Regime Raggiunto:** Durante i test intensivi, il prototipo ha raggiunto e mantenuto un regime di **1200 RPM**. Questo risultato è stato misurato con un **tachimetro ottico costruito artigianalmente** ed è stato ottenuto alimentando il motore **esclusivamente con aria compressa**, dimostrando l'efficacia del controllo elettronico nella gestione del timing.
*   **Efficienza Fluidodinamica:** L'implementazione della logica di **"Dead Time"** nel software ha permesso di **eliminare quasi completamente il fenomeno del "corto circuito pneumatico"**, massimizzando la pressione utile sul pistone. Questo si traduce in un consumo d'aria ottimizzato e in una risposta molto fluida del motore.

### 5.2 Stato Attuale del Prototipo e Ottimizzazioni in Corso
Il progetto è in continua evoluzione. La configurazione testata è già stata superata da migliorie meccaniche, i cui effetti sono in fase di valutazione.

*   **Configurazione Attuale (Ottimizzata):** Il motore è montato con **due valvole identiche** (stesso modello e portata) per immissione e scarico. Questa scelta è temporanea, in **attesa della consegna di una nuova elettrovalvola ottimizzata specificamente per lo scarico**.
*   **Performance Correnti:** Nella configurazione a doppia valvola uguale, il motore **gira in modo estremamente fluido e stabile a una pressione di alimentazione di circa 0.5 bar**, sviluppando una **coppia meccanica soddisfacente** per le dimensioni del prototipo. Questo conferma la robustezza del design meccanico e del controllo di base.
*   **Limitazione Identificata e Sviluppo Futuro:** L'uso di due valvole uguali rappresenta un **compromesso**. La valvola attuale per lo scarico, pur funzionando, non è progettata per le esigenze di un fluido in espansione a bassa pressione e può limitare l'efficienza di evacuazione. Si prevede che l'installazione della **nuova elettrovalvola di scarico, con un'area di passaggio maggiorata e un'isteresi ottimizzata, migliorerà ulteriormente le prestazioni**, soprattutto a regimi più elevati.

### 5.3 Lezione Appresa e Limite Identificato
I test hanno evidenziato il **limite fisico fondamentale** dell'aria compressa come vettore energetico: la sua **bassa densità energetica**.
*   **Problema:** Per un uso pratico esteso (es. la propulsione di una bicicletta), la quantità d'aria necessaria richiederebbe serbatoi troppo pesanti e voluminosi.
*   **Conclusione:** Il motore pneumatico puro, sebbene meccanicamente efficiente, è limitato dall'autonomia. Questa consapevolezza è il motore che guida lo sviluppo verso il sistema ibrido.

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
*Questo README è stato aggiornato per chiarezza e completezza su suggerimento della community. Ultima revisione: Gennaio 2026.*
