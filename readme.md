# Spiegazione Dashboard per Controllo di Qualità Strutture

La dashboard è progettata per fornire una visione d'insieme delle prestazioni in termini di qualità delle strutture, basata sui punteggi di valutazione dei diversi servizi nelle zone. Ci sono 10 zone in tutto, e ad ogni zona appartengono dei servizi fino ad ammontare ad un totale di 46.

## Zone e Servizi

1. **Reception**
   - Qualità Complessiva Reception
   - Personale Reception
   - Pulizia Reception
2. **Sala**
   - Qualità Complessiva Sala
   - Allestimento Sala
   - Personale Sala
   - Pulizia Sala
   - Qualità Cibo Colazione
   - Buffet Colazione
3. **Cucina**
   - Qualità Cibo Cucina
   - Presentazione Cibo Cucina
   - Pulizia Cucina
4. **Bar**
   - Qualità Complessiva Bar
   - Personale Bar
   - Pulizia Bar
   - Qualità Cibo Carta Snack
   - Presentazione Carta Snack
5. **Piscina**
   - Qualità Complessiva Piscina
   - Personale Piscina
   - Pulizia Piscina
   - Bar Piscina
   - Personale Bar Piscina
   - Pulizia Bar Piscina
6. **Piazzetta**
   - Qualità Complessiva Piazzetta
   - Personale Piazzetta
   - Pulizia Piazzetta
   - Bar Piazzetta
   - Personale Bar Piazzetta
   - Pulizia Bar Piazzetta
7. **Spiaggia**
   - Qualità Complessiva Spiaggia
   - Personale Spiaggia
   - Pulizia Spiaggia
   - Bar Spiaggia
   - Personale Bar Spiaggia
   - Pulizia Bar Spiaggia
8. **Centro Benessere**
   - Qualità Complessiva Centro Benessere
   - Personale Centro Benessere
   - Pulizia Centro Benessere
   - Palestra
   - Personale Palestra
   - Pulizia Palestra
9. **Camere**
   - Manutenzione Camere
   - Pulizia Camere
10. **Aree Comuni**
    - Manutenzione Aree Comuni
    - Pulizia Aree Comuni
    - Presenza e Cura del Verde

## Elementi della Dashboard

### FILTRI
- **Filtro per Struttura (primo in alto)**: permette di fare l’analisi specificando una o più strutture 
- **Filtro per Zona (secondo in alto)**: permette di fare l’analisi specificando una o più zone di riferimento.
- **Filtro per Mese (terzo in alto)**: permette di fare l’analisi focalizzandosi su uno o più mesi di riferimento.

### GRAFICI
- **Migliore Struttura (in alto a sinistra)**: è un grafico a barre orizzontali che mostra il punteggio complessivo delle diverse strutture (ad esempio "Riva Marina Resort" con un punteggio di 7.6, "Porto Giardino" con 7.2, ecc.). Indica quale struttura ha un punteggio più alto rispetto alle altre.
  - **Asse X**: `Score_per_Struttura`
  - **Asse Y**: `Struttura`

- **Andamento per Zona e Note (in alto a destra)**: è un grafico a barre verticali che compara il punteggio medio di diverse zone, mostrando anche le note relative (se esistenti).
  - **Asse X**: `Zona`
  - **Asse Y**: `AvgScore`

- **Andamento Complessivo per Modulo (in basso a sinistra)**: è un grafico a colonne che mostra il punteggio medio avuto per ogni modulo compilato in una specifica data e in una specifica struttura (applicando i filtri).
  - **Asse X**: `CodiceRegistrazione`, `Struttura`, `FullDateAlternateID`
  - **Asse Y**: `AvgScore`

- **Andamento per Servizio (in basso a destra)**: è un grafico a torta che mostra i punteggi dei diversi servizi specifici in base ai filtri applicati.
  - **Valori**: Somma di `Score`
  - **Dettagli**: `Servizio`
