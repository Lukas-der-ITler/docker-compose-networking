\# Docker Compose Networking - Antworten



\## 1. Was ist das Standardnetzwerkverhalten in Docker Compose, wenn kein Netzwerk konfiguriert ist?



Docker Compose erstellt automatisch ein gemeinsames Bridge-Netzwerk mit dem Namen <Projektname>\_default. Alle Container werden diesem Netzwerk hinzugefügt und können sich über ihre Servicenamen gegenseitig erreichen.



\## 2. Wie erstellt man ein benutzerdefiniertes Netzwerk in einer docker-compose.yml Datei?



Ein benutzerdefiniertes Netzwerk wird mit dem Abschnitt `networks` definiert und anschließend den gewünschten Services zugewiesen.



Beispiel:



```yaml

services:

&#x20; app:

&#x20;   networks:

&#x20;     - backend



networks:

&#x20; backend:

&#x20;   driver: bridge

