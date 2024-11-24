# CREAZIONE E GESTIONE DI REPORT E DASHBOARD INTERATTIVI IN POWER BI

## 1. Creazione tabelle Dimensioni e Fatti in Excel
Le Dimensioni sono statiche, i Fatti sono dinamici.

## 2. Creazione del Database, delle Tabelle e Importazione Dati in SQL Server Management Studio (SSMS)

### 2.1. Creazione del Database:
1. Aprire SQL Server Management Studio (SSMS) e connettersi al proprio server.
2. Cliccare con il tasto destro su "Databases" nel pannello di navigazione a sinistra.
3. Selezionare "New Database..." dal menu contestuale.
4. Nella finestra di dialogo che appare, inserire il nome del database (ad esempio, `DatasetQuality`) e cliccare su "OK".

### 2.2. Creazione delle Tabelle:
1. Espandere il database appena creato nel pannello di navigazione a sinistra.
2. Cliccare con il tasto destro su "Tables" e selezionare "New Table...".
3. Definire le colonne della tabella:
   - Inserire il nome della colonna, tipo di dati:
     - INT per le chiavi primarie;
     - FLOAT per i numeri (ad esempio, amount);
     - DATE per le date;
     - NVARCHAR (250) o NVARCHAR (MAX) per i testi (ad esempio, le descrizioni delle tipologie di prodotti).
   - Spuntare i caratteri nulli (se previsti nella colonna Excel).
   - Impostare una colonna come chiave primaria cliccando con il tasto destro sul nome della colonna e selezionando "Set Primary Key".
   - Cliccare due volte con il mouse su “Identity Specification” per impostare su YES.
4. Dopo aver configurato le colonne, salvare la tabella con un nome (ad esempio, `DimDates`).
5. Ripetere i passaggi per creare altre tabelle come `FactValutazioni` (tabella dei fatti) o `DimStrutture` (tabella delle dimensioni).

### 2.3. Importazione dei Dati:
1. Cliccare con il tasto destro sul database e selezionare "Tasks" > "Import Data...".
2. Nella finestra "SQL Server Import and Export Wizard":
   - Data source: FLAT FILE SOURCE
   - Browse: CSV FILES
   - Selezionare il file contenente la tabella da importare (fare un file csv per ogni tabella)
   - Sistemare in ADVANCED (ad esempio, se una colonna è testo: DataType: text stream)
   - Destination: MICROSOFT OLE DB PROVIDER FOR SQL SERVER
   - Eseguire l'importazione cliccando su "Finish".

## 3. Utilizzo di Power BI per Importare e Analizzare i Dati

### 3.1. Importazione dei Dati da SQL Server:
1. Aprire Power BI Desktop.
2. Andare su "Home" > "Ottieni dati" > "SQL Server".
3. Nella finestra di dialogo "Database SQL Server":
   - Inserire il nome del server e, se necessario, il nome del database.
   - Cliccare su "OK".
4. Selezionare le tabelle che si desidera importare (ad esempio, `DimStrutture` e `FactValutazioni`).
5. Cliccare su "Carica" per importare i dati nel proprio modello di Power BI.

### 3.2. Verifica delle Relazioni:
1. Andare alla vista "Modello" cliccando sull'icona del modello nel pannello a sinistra.
2. Verificare le relazioni tra le tabelle:
   - Se non sono già state create automaticamente, creare manualmente le relazioni (ad esempio, trascinando il campo `DateID` dalla tabella `DimDates` e rilasciandolo sul campo `DateID` nella tabella `FactValutazioni`).
   - Configurare la relazione come uno-a-molti (One-to-Many) se non è già configurata correttamente.

### 3.3. Creazione delle Misure:
1. Andare alla vista "Dati" cliccando sull'icona dei dati nel pannello a sinistra.
2. Selezionare la tabella in cui si vogliono creare le misure (ad esempio, in `DimStrutture`).
3. Cliccare su "Nuova Misura" nella scheda "Modellazione" della barra degli strumenti.
4. Inserire le formule per le misure

### 3.4. Creazione e Formattazione dei Grafici:
1. Andare alla vista "Report" cliccando sull'icona del report nel pannello a sinistra.
2. Selezionare il tipo di grafico (ad esempio, grafico a barre, grafico a torta).
3. Trascinare i campi e le misure appropriate nei riquadri "Asse", "Valori" e "Leggenda" del grafico.
4. Per formattare il grafico:
   - Selezionare il grafico e usare il pannello "Visualizzazioni" per modificare colori, etichette e stile.
5. Aggiungere i filtri:
   - Trascinare i campi nella sezione "Filtri" per applicare filtri globali o locali ai grafici.