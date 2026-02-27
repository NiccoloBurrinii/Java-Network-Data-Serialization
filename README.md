# Java Network Data Serialization

Progetto didattico focalizzato sulla trasmissione di oggetti strutturati attraverso Socket TCP, implementando la serializzazione e deserializzazione di dati nei formati **JSON** e **XML**.

## Descrizione
Il software dimostra come convertire oggetti Java complessi (POJO) in formati di interscambio universali per la comunicazione di rete. L'esercizio è strutturato in due varianti tecniche: la prima utilizza lo standard **JSON** per la sua leggerezza e velocità, la seconda lo standard **XML** per la sua struttura gerarchica. Entrambi i moduli permettono al Client di ricevere un oggetto "Persona" dal Server e ricostruirlo localmente mantenendo l'integrità dei dati.



## Funzionamento del Sistema:
* **Object Mapping (Jackson)**: Integrazione delle librerie `ObjectMapper` e `XmlMapper` per la trasformazione automatica degli oggetti in stringhe formattate e viceversa.
* **Network Communication**: Apertura di un canale TCP sulla porta 6789 per il trasferimento dei dati serializzati tra i due host.
* **Data Modeling**: Definizione di una classe `Persona` (Plain Old Java Object) con proprietà specifiche (nome, cognome, età) utilizzata come blueprint per i dati.
* **Deserializzazione Dinamica**: Il Client analizza la stringa ricevuta in tempo reale, mappandola nuovamente in un'istanza della classe Java per l'utilizzo logico.
* **Ciclo di Vita Server**: Implementazione di un loop infinito che consente al server di restare in ascolto e servire nuovi client in modo sequenziale.

## Tecnologie e Concetti
* **Java Sockets**: Gestione della connessione punto-punto per il trasporto affidabile dei pacchetti.
* **Jackson Databind**: Utilizzo del framework standard per la manipolazione di oggetti JSON in Java.
* **Jackson Dataformat XML**: Estensione specifica per la gestione della serializzazione in formato XML.
* **Interoperabilità**: Capacità di esporre dati in formati standard leggibili da qualsiasi applicazione esterna.

## Struttura dell'Esercizio
| Modulo | Libreria | Formato Output Esempio |
| :--- | :--- | :--- |
| **Serializzazione JSON** | `com.fasterxml.jackson.databind` | `{"nome":"Niccolò","cognome":"Burrini","eta":18}` |
| **Serializzazione XML** | `com.fasterxml.jackson.dataformat.xml` | `<Persona><nome>Niccolò</nome><cognome>Burrini</cognome><eta
