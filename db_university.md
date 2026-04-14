# Database: Università

### tabella: dipartimenti
- id (INT PK AUTO_INCREMENT)
- nome (VARCHAR(150))
- descrizione (TEXT)


### tabella: corsi_di_laurea
- id (INT PK AUTO_INCREMENT)
- dipartimento_id (INT FK)
- nome (VARCHAR(150))
- durata_anni (TINYINT)
- tipo (VARCHAR(50))
- descrizione (TEXT)


### tabella: corsi
- id (INT PK AUTO_INCREMENT)
- corso_di_laurea_id (INT FK)
- nome (VARCHAR(150))
- cfu (TINYINT)
- anno_di_corso (TINYINT)
- semestre (TINYINT)
- descrizione (TEXT)


### tabella: insegnanti
- id (INT PK AUTO_INCREMENT)
- nome (VARCHAR(100))
- cognome (VARCHAR(100))
- email (VARCHAR(150))
- telefono (VARCHAR(20))
- ruolo (VARCHAR(100))


### tabella: corso_insegnante
- id (INT PK AUTO_INCREMENT)
- corso_id (INT FK)
- insegnante_id (INT FK)


### tabella: appelli_esame
- id (INT PK AUTO_INCREMENT)
- corso_id (INT FK)
- data_esame (DATETIME)
- aula (VARCHAR(100))
- tipo_prova (VARCHAR(50))

### tabella: studenti
- id (INT PK AUTO_INCREMENT)
- corso_di_laurea_id (INT FK)
- nome (VARCHAR(100))
- cognome (VARCHAR(100))
- matricola (VARCHAR(20))
- email (VARCHAR(150))
- data_nascita (DATE)
- data_iscrizione (DATE)


### tabella: iscrizioni_esami
- id (INT PK AUTO_INCREMENT)
- studente_id (INT FK)
- appello_id (INT FK)
- data_iscrizione (DATETIME)
- voto (TINYINT)
- lode (BOOLEAN)
- esito (VARCHAR(30))