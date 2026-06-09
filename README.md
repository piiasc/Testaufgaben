# Testaufgaben
Beantwortung der Testaufgaben

## Landingpage

Da ich mich erst einmal mit Bootstrap 5 vertraut machen musste, dauerte die Erstellung der Landingpage etwas länger als gedacht. Insgesamt benötigte ich ca 3,5 Stunden.

## PHP

1. Was ist an dem Code problematisch?

- kein Validierung der Eingaben (Einhalten Format/Länge)
- keine Authentifizierung (ob es den User gibt)

2. Welche Verbesserungen würdest du empfehlen und warum?

- Name & Mail auf Länge und feste Zeichen prüfen, damit Validierung und Authentifizierung durchgeführt wird

3. Noch eine ergänzende Frage aus der Praxis: 
Ein Kunde wird mit Spam über das Kontaktformular zugespammt. Welche Möglichkeiten fallen dir ein wie man 
solchen Spam verhindern kann?

- Verstecktes Formularfeld, das von Nutzer nicht gesehen wird aber von Bots automatisch ausgefüllt wird
- (robots.txt, ich bin mir jedoch unsicher, ob das Spam-Bots abhält)

## Datenbanken

1. Gib alle Nutzer aus, die sich in den letzten 30 Tagen registriert haben.
    SELECT * FROM users WHERE DATEDIFF(day, created_at, NOW()) <= 30; (musste DATEDIFF ergooglen)
3. Finde alle Nutzer, deren E-Mail mehrfach vorkommt.
    Hier bin ich mir leider unsicher, würde aber GROUP BY oder HAVING COUNT benutzen
4. Wie würdest du verhindern, dass doppelte E-Mails gespeichert werden?
    CREATE TABLE users (
        id INT PRIMARY KEY,
        name VARCHAR(255),
        email VARCHAR(255) UNIQUE,
        created_at DATETIME
    );
5. Warum sollte man SQL-Queries nicht direkt mit Benutzereingaben bauen?
    Weil es eine Sicherheitslücke für SQL-Injections sein könnte und Angreifer einfach die Eingaben ändern können
