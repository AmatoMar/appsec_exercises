## Avvio dei servizi con Docker Compose

Questa repository contiene un ambiente di laboratorio per testare vulnerabilità OWASP tramite Docker Compose.

### Avvio dei servizi
Per avviare tutti i servizi definiti nel file `docker-compose.yaml`, esegui il seguente comando dalla root del progetto:

```bash
docker compose up -d
```

Questo comando avvierà i seguenti laboratori e applicazioni target.

### SKF Labs

| Servizio | Descrizione                         | HTTP (diretto)                                 |
| -------- | ----------------------------------- | ---------------------------------------------- |
| **idor** | Laboratorio OWASP IDOR              | [http://127.0.0.1:7000](http://127.0.0.1:7000) |
| **sqli** | Laboratorio OWASP SQL Injection     | [http://127.0.0.1:7001](http://127.0.0.1:7001) |
| **xss**  | Laboratorio OWASP XSS               | [http://127.0.0.1:7002](http://127.0.0.1:7002) |
| **ssrf** | Laboratorio OWASP SSRF              | [http://127.0.0.1:7003](http://127.0.0.1:7003) |
| **cmdi** | Laboratorio OWASP Command Injection | [http://127.0.0.1:7004](http://127.0.0.1:7004) |

### Applicazioni Target

| Servizio       | Descrizione                     | HTTP (diretto)                                 |
| -------------- | ------------------------------- | ---------------------------------------------- |
| **dvwa**       | Damn Vulnerable Web Application | [http://127.0.0.1:7010](http://127.0.0.1:7010) |
| **juice-shop** | OWASP Juice Shop                | [http://127.0.0.1:7011](http://127.0.0.1:7011) |
| **webgoat**    | OWASP WebGoat                   | [http://127.0.0.1:7012](http://127.0.0.1:7012) |
| **webwolf**    | WebWolf (companion di WebGoat)  | [http://127.0.0.1:7013](http://127.0.0.1:7013) |

### Spegnimento dei servizi
Per fermare e rimuovere i container:

```bash
docker compose down
```

### Architettura

Tutti i servizi sono connessi alla rete Docker `appsec-network`.

### Note
- I servizi HTTP diretti (porte 7xxx) sono esposti solo su localhost per motivi di sicurezza.
- Il servizio `ssrf.internal` non è esposto direttamente all'host per motivi didattici (utilizzato come target interno per il laboratorio SSRF).

Per ulteriori dettagli consulta il file `docker-compose.yaml`.
