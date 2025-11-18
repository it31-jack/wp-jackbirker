# KI_PROMPTS.md

- **Docker-Compose Version**  
  Frage: „Welche Versionen von MariaDB und WordPress sind geeignet?“  
  Antwort: MariaDB 10.11, WordPress 6.3 mit PHP 8.2 empfohlen.

- **Sicherstellung der Startreihenfolge**  
  Frage: „Wie sorge ich, dass WordPress erst startet, wenn die Datenbank bereit ist?“  
  Antwort: Nutze `depends_on` mit `condition: service_healthy` und einen Healthcheck.

- **Persistenz & Synchronisation**  
  Frage: „Wie synchronisiere ich wp-content zwischen Host und Container?“  
  Antwort: Bind-Mount: `./wordpress/wp-content:/var/www/html/wp-content`

- **Passwortsicherheit**  
  Frage: „Wie vermeide, Passwörter im Repository zu speichern?“  
  Antwort: `.env` außerhalb des Repos lagern, mit `.gitignore` ausschließen.

- **Ports und Zugänglichkeit**  
  Frage: „Welche Ports sind sinnvoll?“  
  Antwort: WordPress auf 8080, phpMyAdmin auf 8081.

- **Warnung `version` in `docker-compose.yml`**  
  Frage: „Was bedeutet die Warnung?“  
  Antwort: `version` kann bei aktuellen Docker Compose Versionen weggelassen werden.

- **Docker Desktop Fehler auf Windows**  
  Frage: „Fehler bei Docker-Start, z.B. 'The system cannot find the file specified'“  
  Antwort: Docker Desktop neu starten, WSL2 neu starten, Docker-Dienst neu starten.

**KI Prompts Datei anhand des Chats erstellen**
Frage: Erstelle mir bitte eine Datei im Markdown Format, in der du unsere Fragen und Antworten des jetzigen Chats aufführst. Kürze gerne ab - es wird eine KI_PROMPTS.md Datei