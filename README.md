# wirvsvirus-backend-doc

## ID Erzeugung
Die ID wird errechnet aus Daten, welche nur dem medizinischen Personal und dem Patienten in dieser Kombination bekannt sind.
* Name des Patienten
* Geburtsdatum des Patienten
* Probennummer des beim Patienten durchgeführten Tests

Diese ID wird erzugt unter Verwendung einer https://de.wikipedia.org/wiki/Kryptographische_Hashfunktion ( aktuell SHA256, beliebig austauschbar).
Eine Eigenschaft einer Hashfunktion ist es, dass es nicht möglich ist aus dem berechneten Hash die Eingabedaten zu berechnen (das Backend kann diese Daten nicht de-anonymisieren).

Der vorgeschlagene Prozess sieht vor, dass beim Eingang der Testergebnisse diese ID, das Ergebnis und sofern vorhanden die Kontaktinformation übertragen werden. 
Die aktive Benachrichtigung wird zu diesem Zeitpunkt ausgelöst. Allein die ID und das Ergebnis werden im Backend gespeichert, damit sie später vom Patienten über das Portal abgerufen werden können. Die Kontaktinformationen werden nach der versuchten Benachrichtigung verworfen.
