DIPARTIMENTI
|       COLONNA         |        TIPO         |        ATTRIBUTI                   |        INDICI         | 
____________________________________________________________________________________________________________

| ID                    | Int                 | Auto increment, not null, unique   | Primay Key            |
| Nome                  | Varchar(50)         | Not null                           |                       |
| Sigla                 | Varchar (10)        | Not null, unique                   | Index                 |
| Mail                  | Varchar (50)        | Not null                           |                       |



CORSI DI LAUREA
|       COLONNA         |        TIPO         |        ATTRIBUTI                   |        INDICI         | 
____________________________________________________________________________________________________________

| ID                    | Int                 | Auto increment, not null, unique   | Primay Key            |
| Nome                  | Varchar(50)         | Not null                           |                       |
| Sigla                 | Varchar (10)        | Not null, unique                   | Index                 |



CORSI SINGOLI
|       COLONNA         |        TIPO         |        ATTRIBUTI                   |        INDICI         | 
____________________________________________________________________________________________________________

| ID                    | Int                 | Auto increment, not null, unique   | Primay Key            |
| Nome                  | Varchar(50)         | Not null                           |                       |
| Sigla                 | Varchar (10)        | Not null, unique                   | Index                 |



CORSI PER LAUREA
|       COLONNA         |        TIPO         |        ATTRIBUTI                   |        INDICI         | 
____________________________________________________________________________________________________________

| ID_CORSO_DI_LAUREA    | Int                 | Not null                           |                       |
| ID_CORSO_SINGOLO      | Int          | Not null                           |                       |



STUDENTI
|       COLONNA         |        TIPO         |        ATTRIBUTI                   |        INDICI         | 
____________________________________________________________________________________________________________

| ID                    | Int                 | Auto increment, not null, unique   | Primay Key            |
| Nome                  | Varchar(50)         | Not null                           |                       |
| Cognome               | Varchar (50)        | Not null                           |                       |
| Mail                  | Varchar (50)        | Not null                           |                       |
| Telefono              | Medium int          | Not null                           |                       |
| Indirizzo             | Varchar (200)       | Not null                           |                       |
| Data di nascita       | Date                | Not null                           |                       |
| Luogo di nascita      | Varchar (200)       | Not null                           |                       |
| Matricola             | Varchar (10)        | Not null, Unique                   | Index                 |




INSEGNANTI
|       COLONNA         |        TIPO         |        ATTRIBUTI                   |        INDICI         | 
____________________________________________________________________________________________________________

| ID                    | Int                 | Auto increment, not null, unique   | Primay Key            |
| Nome                  | Varchar(50)         | Not null                           |                       |
| Cognome               | Varchar (50)        | Not null                           |                       |
| Mail                  | Varchar (50)        | Not null                           |                       |
| Telefono              | Medium int          | Not null                           |                       |
| Indirizzo             | Varchar (200)       | Not null                           |                       |
| Data di nascita       | Date                | Not null                           |                       |
| Luogo di nascita      | Varchar (200)       | Not null                           |                       |




INSEGNANTI_CORSI
|       COLONNA         |        TIPO         |        ATTRIBUTI                   |        INDICI         | 
____________________________________________________________________________________________________________

| ID_INSEGNANTE         | Int                 | Not null                           |                       |
| ID_CORSO_SINGOLO      | Int                 | Not null                           |                       |




APPELLI
|       COLONNA         |        TIPO         |        ATTRIBUTI                   |        INDICI         | 
____________________________________________________________________________________________________________

| ID                    | Int                 | Auto increment, not null, unique   | Primay Key            |
| Data                  | Date                | Not null                           |                       |
| Ora                   | Time                | Not null                           |                       |
| Luogo                 | Varchar (200)       | Not null                           |                       |




APPELLI_STUDENTI
|       COLONNA         |        TIPO         |        ATTRIBUTI                   |        INDICI         | 
____________________________________________________________________________________________________________

| ID_APPELLO            | Int                 | Not null                           |                       |
| ID_STUDENTE           | Int                 | Not null                           |                       |
| VOTO                  | Small int           | Not null                           |                       |
