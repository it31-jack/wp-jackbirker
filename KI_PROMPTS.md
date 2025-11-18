# KI_PROMPTS.md

- **Docker Compose Grundlagen**  
  Frage: „Welche Version von MariaDB und WordPress eignen sich gut für eine lokale Entwicklungsumgebung?“  
  Antwort: MariaDB 10.11, WordPress 6.3 mit PHP 8.2 empfohlen.

- **Healthcheck und Abhängigkeiten**  
  Frage: „Wie stelle ich sicher, dass WordPress erst startet, wenn die Datenbank gesund ist?“  
  Antwort: Healthcheck mit `mysqladmin ping` für MariaDB und `depends_on` mit `condition: service_healthy` in docker-compose.yml.

- **Persistenz & Sync**  
  Frage: „Wie kann ich sicherstellen, dass wp-content zwischen Host und Container synchronisiert wird?“  
  Antwort: Bind-Mount benutzen: `./wordpress/wp-content:/var/www/html/wp-content`

- **Sicherheit bei Passwörtern**  
  Frage: „Wie kann ich Passwörter aus dem Git-Repository ausnehmen?“  
  Antwort: `.env`-Datei außerhalb des Repos halten und mit `.gitignore` ausschließen.

- **Ports & Zugänglichkeit**  
  Frage: „Welche Ports sind sinnvoll für WordPress und phpMyAdmin im lokalen Setup?“  
  Antwort: WordPress auf `8080`, phpMyAdmin auf `8081`

- **Version Warnung in docker-compose.yml**  
  Frage: „Was bedeutet die Warnung, dass `version` in docker-compose.yml obsolete ist?“  
  Antwort: Die `version`-Zeile kann entfernt werden, da sie bei aktuellen Versionen ignoriert wird.

- **Fehlerbehebung Docker Desktop auf Windows**  
  Frage: „Fehler 'The system cannot find the file specified' beim Docker-Start - Lösung?“  
  Antwort: Docker Desktop neu starten, WSL2 shutdown, Docker-Dienst neu starten

---

*Die meisten technischen Entscheidungen hast du selbst getroffen, die KI hat bei Details und Best-Practices geholfen.*
