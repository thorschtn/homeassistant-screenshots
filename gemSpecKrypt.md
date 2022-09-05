


**Elektronische Gesundheitskarte und Telematikinfrastruktur**



**Übergreifende Spezifikation**

**Verwendung kryptographischer Algorithmen in der
Telematikinfrastruktur**

{include-macros:/macros.gematikMacros}

#renderGematikDokumentenTitel($document)

**Änderungen zur Vorversion**

Anpassungen des vorliegenden Dokumentes im Vergleich zur Vorversion können Sie der nachfolgenden Tabelle entnehmen.

**Dokumentenhistorie**

|**Version**|**Datum**|**Grund der Änderung, besondere Hinweise**|**Bearbeitung**|
| :- | :- | :- | :- |
|1.4.0|03.07.08|freigegeben (für Release 2.3.4)|gematik|
|1.9.0|26.06.12|Kommentierung|gematik|
|1.10.0|13.09.12|Einarbeitung der Gesellschafterkommentare|gematik|
|2.0.0|15.10.12|bQS Kommentare eingearbeitet|gematik|
|2.1.0|06.06.13|Erweiterung im Rahmen der PP-Erstellung Konnektor (kryptographische Vorgaben für die SAK); Anpassung an das fortgeschriebene PP Konnektor ORS1 (BSI-CC-PP-0046), Konsistenz zur veränderten gemSpec\_Kon herstellen|gematik|
|2.2.0|21.02.14|Losübergreifende Synchronisation|gematik|
|2.3.0|17.06.14|Entfernung des CBC-Modus bei der Dokumentenver- und -entschlüsselung gemäß P11-Änderungsliste|gematik|
|2.4.0|17.07.15|Einarbeitung Änderungen aus Errata 1.4.6|gematik|
|2.5.0|03.05.16|Anpassungen zum Online-Produktivbetrieb (Stufe 1)|gematik|
|2.6.0|24.08.16|Einarbeitung weiterer Kommentare|gematik|
|2.7.0|28.10.16|Anpassungen gemäß Änderungsliste|gematik|
|2.8.0|20.04.17|Start der Migration 120-Bit-Sicherheitsniveau kryptographische Verfahren in der TI (PKI der Kartengeneration 2.1), Anpassungen gemäß Änderungsliste|gematik|
|2.9.0|19.12.17|C\_6260 (IPsec), C\_6289 (qeS)|gematik|
|2.10.0|14.05.18|C\_6195 (IPsec), C\_6374 (ed. IPsec), C\_6375 (TLS für SM), C\_6399 (IPsec)|gematik|
|2.11.0|26.10.18|Veröffentlichung im Rahmen von Release 2.1.3|gematik|
|2.11.0|29.10.18|C\_6639 (RSA 2048 Bit Zertifikate) etc., redaktionelle Aktualisierung der Anforderungen A\_14653, A\_15699 im Rahmen von Release 2.1.3|gematik|
|2.12.0|18.12.18|ePA-Inhalte ergänzt|gematik|
|2.13.0|15.05.19|Anpassungen gemäß Änderungsliste P18.1|gematik|
|2.14.0|28.06.19|Anpassungen gemäß Änderungsliste P19.1|gematik|
|2.15.0|02.10.19|Anpassungen gemäß Änderungsliste P20.1/2|gematik|
|2.16.0|02.03.20|Anpassungen gemäß Änderungsliste P20.4/21.1|gematik|
|2.16.1|27.08.20|Anpassungen gemäß Änderungsliste P21.4|gematik|
|2.16.2|05.11.20|Anpassungen gemäß Änderungsliste P21.6|gematik|
|2.17.0|30.06.20|Anpassungen gemäß Änderungsliste P22.1 und Scope-Themen aus Systemdesign R4.0.0|gematik|
|2.18.0|12.11.20|Einarbeitung Scope-Themen zu R4.0.1|gematik|
|2.19.0|19.02.21|Anpassungen gemäß Änderungsliste P22.5 |gematik|
|2.19.1|30.06.21|Ergänzung fehlender Referenzen bzgl. Prüfung der VAU-Identität (informative Erläuterung in Kapitel 7.1 (C\_10599)), Rückbau C\_10062 (aus Konn\_Maintenance\_21.3)|gematik|
|2.20.0|02.09.21|Einarbeitung Konn\_Maintenance\_21.5 (Kapitel 6.13 neu),<br>ab Release "Konnektor PTV 5.0.2: Maintenance 21.5" (Sept. 2021) führt die gematik eine stufenweise Umbenennung folgender Begriffe durch:<br>aus "aAdG-NetG" wird "WANDA Basic",<br>aus "aAdG" und "aAdG-NetG-TI" wird "WANDA Smart"<br>(nähere Informationen finden Sie unter <https://fachportal.gematik.de/>) |gematik|
|2.21.0|31.01.22|Einarbeitung ePA\_Maintenance\_21.5 und Konn\_Maintenance\_21.6|gematik|
|2.22.0|01.03.22|Einarbeitung E-Rezept\_Maintenance\_21.3|gematik|
|2.23.0||Einarbeitung gemSpec\_Krypt\_Maintenance\_22.1                      ?????<br>Einarbeitung Änderungsliste E-Rezept\_Maintenance 22.2|gematik|
Die vorliegende übergreifende Spezifikation definiert Anforderungen an Produkte der TI bezüglich kryptographischer Verfahren. Diese Anforderungen sind als übergreifende Regelungen relevant für Interoperabilität und Verfahrenssicherheit.

Für die TI ist die Technische Richtlinie 03116 Teil 1 [BSI-TR-03116-1] normativ, d. h. nur dort aufgeführte kryptographische Verfahren dürfen von Produkten in der TI verwendet werden. Wenn mehrere unterschiedliche Produkttypen der TI zusammenarbeiten ist es bez. der Interoperabilität nicht sinnvoll wenn jeder beteiligte Produkttyp alle dort aufgeführten Verfahren umsetzen muss, da er vermuten muss die Gegenstelle beherrscht nur eine Teilmenge der dort aufgeführten Verfahren. Um einen gemeinsamen Nenner zu definieren, legt dieses Dokument für bestimmte Einsatzzwecke ein Mindestmaß an verpflichtend zu implementierenden Verfahren aus [BSI-TR-03116-1] fest, oftmals mit spezifischen Parametern. Ein Produkttyp ist frei, weitere Verfahren aus der [BSI-TR-03116-1] optional zu implementieren, kann sich jedoch nicht ohne Weiteres darauf verlassen, dass sein potentieller Kommunikationspartner diese auch beherrscht.

Dieses Dokument folgt den Konventionen der TR. Diese hat einen Betrachtungszeitraum von sechs bzw. sieben Jahren. Analog zu Kapitel 1 [BSI-TR-03116-1] bedeutet eine Aussage „Algorithmus X ist geeignet bis Ende 2023+“ generell nicht, dass Algorithmus X nach Ende 2023 nicht mehr geeignet ist, sondern lediglich, dass über die Eignung nach Ende 2023 in der TR keine explizite Aussage gemacht wird und dass aus heutiger Sicht die weitere Eignung nicht ausgeschlossen ist. Aussagen über den Betrachtungszeitraum hinaus sind „mit einem höheren Maß an Spekulation verbunden“.

Bei neuen Erkenntnissen über die verwendeten kryptographischen Algorithmen, die zu einer Änderung der TR-03116-1 führen, wird eine Anpassung dieses Dokumentes erfolgen. Für Verwendungszwecke, bei denen bereits eine Migration zu stärkeren Algorithmen in Planung ist oder die Verwendung von Algorithmen unterschiedlicher Stärke zulässig ist, wird ein Ausblick gegeben, bis wann welche Algorithmen ausgetauscht sein müssen. Bei den Migrationsstrategien für kryptographische Algorithmen ist darauf zu achten, dass hinterlegte Objekte umzuschlüsseln sind bzw. die älteren Algorithmen (unter der Bedingung, dass sie sicherheitstechnisch noch geeignet sind) für eine gewisse Übergangsphase weiter unterstützt werden müssen und danach zuverlässig in den Komponenten deaktiviert werden müssen.

Das Dokument richtet sich an Hersteller und Anbieter von Produkten der TI, die kryptographische Objekte verwalten.

Dieses Dokument enthält normative Festlegungen zur Telematikinfrastruktur des deutschen Gesundheitswesens. Der Gültigkeitszeitraum der vorliegenden Version und deren Anwendung in Zulassungsverfahren wird durch die gematik GmbH in gesonderten Dokumenten (z. B. Dokumentenlandkarte, Produkttypsteckbrief, Leistungsbeschreibung) festgelegt und bekannt gegeben.

***Schutzrechts-/Patentrechtshinweis***

*Die nachfolgende Spezifikation ist von der gematik allein unter technischen Gesichtspunkten erstellt worden. Im Einzelfall kann nicht ausgeschlossen werden, dass die Implementierung der Spezifikation in technische Schutzrechte Dritter eingreift. Es ist allein Sache des Anbieters oder Herstellers, durch geeignete Maßnahmen dafür Sorge zu tragen, dass von ihm aufgrund der Spezifikation angebotene Produkte und/oder Leistungen nicht gegen Schutzrechte Dritter verstoßen und sich ggf. die erforderlichen Erlaubnisse/Lizenzen von den betroffenen Schutzrechtsinhabern einzuholen. Die gematik GmbH übernimmt insofern keinerlei Gewährleistungen.*

Aufgabe des Dokumentes ist es nicht, eine Sicherheitsbewertung von kryptographischen Algorithmen vorzunehmen. Dieser Gesichtspunkt wird in [BSI-TR-03116-1] behandelt. Es werden lediglich die dort vorgegebenen Algorithmen weiter eingeschränkt, um die Herstellung der Interoperabilität zu unterstützen.

Es ist nicht Ziel dieses Dokumentes, den Prozess zum Austauschen von Algorithmen zu definieren, sondern lediglich den zeitlichen Rahmen für die Verwendbarkeit von Algorithmen festzulegen und somit auf den Bedarf für die Migration hinzuweisen.

Anforderungen als Ausdruck normativer Festlegungen werden durch eine eindeutige ID sowie die dem RFC 2119 [RFC-2119] entsprechenden, in Großbuchstaben geschriebenen deutschen Schlüsselworte MUSS, DARF NICHT, SOLL, SOLL NICHT, KANN gekennzeichnet.

Sie werden im Dokument wie folgt dargestellt:

**<AFO-ID> - <Titel der Afo>**
Text / Beschreibung
**[**<=**]**

Dabei umfasst die Anforderung sämtliche zwischen Afo-ID und der Textmarke [<=] angeführten Inhalte.

Nachfolgend werden grundlegende Festlegungen zur Verwendung von Algorithmen innerhalb der Telematikinfrastruktur getroffen. Diese Anforderungen sind unabhängig von den im nachfolgenden Kapitel definierten Einsatzszenarien und werden durch diese verwendet.

Der Begriff „kryptographische Identität“ (nachfolgend nur noch als Identität bezeichnet) bezeichnet einen Verbund aus Identitätsdaten und einem kryptographischen Objekt, das bspw. im Rahmen einer Authentisierung und Authentifizierung verwendet werden kann. Im Allgemeinen handelt es sich um Schlüsselpaare, bestehend aus öffentlichem und privatem Schlüssel, sowie einem Zertifikat, das die Kombination aus Attributen und öffentlichem Schlüssel durch eine übergeordnete Instanz (CA – Certification Authority) bestätigt.

Bei den Algorithmenvorgaben für Identitäten muss u. a. spezifiziert werden:

- für welche Algorithmen und für welchen Verwendungszweck die Schlüssel verwendet werden (Bestimmte Verwendungszwecke schließen einander aus, bspw. dürfen nicht Signaturschlüssel für die Sicherung von Authentizität und Integrität von Dokumenten als Signaturschlüssel für beliebige Challenges im Rahmen einer Authentisierung verwendet werden.),
- welche Algorithmen für die Signatur des Zertifikates verwendet werden,
- mit welchen Algorithmen die OCSP-Responses signiert werden und
- wie die Zertifikate des OCSP-Responders signiert sind.

Eine X.509-Identität ist eine Identität gemäß Abschnitt 2.1, bei der ein X.509-Zertifikat [RFC-5280] verwendet wird.

Bei der Aufteilung von X.509-Identitäten wurden die Identitäten zunächst nach Gruppen für verschiedene Einsatzzwecke des Schlüssels unterteilt und diese bei Bedarf um einen notwendigen Einsatzkontext erweitert. Aus dieser Aufteilung ergibt sich die nachfolgend tabellarisch dargestellte Übersicht der Arten von X.509-Identitäten. Der exemplarische Einsatzort der Identitäten ist hierbei rein informativ, die Ausprägung wird in den Spezifikationen festgelegt, die eine kryptographische Identität benötigen.

Tabelle #: Tab\_KRYPT\_001 Übersicht über Arten von X.509-Identitäten 

|**Referenz**|**Gruppe**|**Kontext**|**Exemplarische Identitäten zur Verwendung (nicht vollständig)**|
| :- | :- | :- | :- |
|2.1.1.1|Identitäten für die Erstellung von Signaturen|Identitäten für die Erstellung nicht-qualifizierter digitaler Signaturen|OSIG-Identität der SMC-B bzw. HSM-B|
|2.1.1.2||Identitäten für die Erstellung qualifizierter Signaturen|QES-Identität des HBA|
|2.1.1.5||Signaturidentitäten, die in den Diensten der TI-Plattform und den Fachdiensten zum Einsatz kommen.|Fachdienstsignatur<br>Signatur durch zentrale Komponente der TI-Plattform<br>Code-Signatur|
|2.1.1.3|Identitäten für die Client-Server-Authentifizierung|Identitäten für den Aufbau von TLS-Verbindungen|Fachdienst TLS – Server<br>Fachdienst TLS – Client<br>zentrale TI-Plattform TLS – Server<br>zentrale TI-Plattform TLS – Client<br>AUT-Identität der SMC-B<br>AUT-Identität des Kartenterminals<br>AUT-Identität des Anwendungskonnektors<br>AUT-Identität der SAK<br>AUT-Identität der eGK<br>AUTN-Identität der eGK<br>AUT-Identität des HBA|
|2.1.1.4||Identitäten für den Aufbau von IPsec-Verbindungen|ID.NK.VPN<br>ID.VPNK.VPN|
|2.1.1.6|Verschlüsselungs-zertifikate|Identitäten, für die medizinische Daten verschlüsselt werden|ENC-Identität  des Versicherten <br>ENCV-Identität der eGK des Versicherten<br>ENC-Identität des HBA<br>ENC-Identität der SMC-B|
Für den Aufbau der X.509-Zertifikate gelten die Vorgaben aus den jeweiligen Spezifikationen der X.509-Zertifikate.

Tabelle #: Tab\_KRYPT\_002 Algorithmen für X.509-Identitäten zur Erstellung nicht-qualifizierter Signaturen für die Schlüsselgeneration „RSA“ 

|**Anwendungsfall**|**Vorgaben**|
| :- | :- |
|Art und Kodierung des öffentlichen Schlüssels|RSA (OID 1.2.840.113549.1.1.1)<br>zu verwendende Schlüssellänge: 2048 Bit, zulässig bis Ende 2023 [BSI-TR-03116-1], vgl. auch A\_15590|
|Signatur eines Zertifikats<br>Signatur einer OCSP-Response<br>Signatur eines OCSP-Responder-Zertifikates<br>Signatur einer CRL<br>Signatur des Zertifikats das Basis der Signaturprüfung einer CRL ist|sha256withRSAEncryption<br>(OID 1.2.840.113549.1.1.11)<br>zu verwendende Schlüssellänge: 2048 Bit, zulässig bis Ende 2023 [BSI-TR-03116-1], vgl. auch A\_15590|

Erläuterung: Die technische Durchsetzung des Endes der Zulässigkeit von RSA mit weniger als 3000 Bit Schlüssellänge in X.509-Zertifikaten erfolgt durch die Herausnahme der entsprechenden RSA-basierten Sub-CA-Zertifikate aus der TSL zum Zeitpunkt des Ablaufens der Zulässigkeit (gemäß TIP1-A\_2062). Ein TSP muss bez. der Zertifikatsgültigkeitsdauer der von ihm ausgegebenen Zertifikate das nach Spezifikationslage definierte Verhalten zeigen (i. A. Zertifikatsgültigkeitsdauer der ausgegebenen Zertifikate von 5 Jahren). Ein TSP kann auch mit dem Kartenherausgeber beliebige Gültigkeitsdauern unter 5 Jahren für die Laufzeit der vom TSP ausgegebenen Zertifikate vereinbaren.

Tabelle #: Tab\_KRYPT\_002a Algorithmen für X.509-Identitäten zur Erstellung nicht-qualifizierter Signaturen für die Schlüsselgeneration „ECDSA“ 

|**Anwendungsfall**|**Vorgabe**|
| :- | :- |
|Art und Kodierung des öffentlichen Schlüssels|ecPublicKey<br>{OID 1.2.840.10045.2.1}<br>auf der Kurve brainpoolP256r1 [RFC-5639#3.4, brainpoolP256r1]<br>zulässig bis Ende 2023+<br><br>Die Kodierung des öffentlichen Punkt erfolgt nach [RFC5480, Abschnitt 2], vgl. Beispiel in Abschnitt 5.2)<br><br>Der privater Schlüssel muss zufällig und gleichverteilt aus {1, …, q-1} gewählt werden. (q ist die Ordnung des Basispunkts und ceil(log2 q)=256 ).|
|Signatur eines Zertifikats<br>Signatur einer OCSP-Response<br>Signatur eines OCSP-Responder-Zertifikates<br>Signatur einer CRL<br>Signatur des Zertifikats das Basis der Signaturprüfung einer CRL ist|ecdsa-with-SHA256 [RFC-3279] {OID 1.2.840.10045.4.3.2}<br>auf der Kurve brainpoolP256r1 [RFC-5639#3.4, brainpoolP256r1]<br>zulässig bis Ende 2023+<br><br>vgl. Beispiel in Abschnitt 5.2<br><br>Der privater Schlüssel muss zufällig und gleichverteilt aus {1, …, q-1} gewählt werden. (q ist die Ordnung des Basispunkts und ceil(log2 q)=256 ).|
Aktuell werden in der TI CRLs ausschließlich im Rahmen des IPsec-Verbindungsaufbaus (Verbindung der Konnektoren in die TI) verwendet.

Für die maximale Gültigkeitsdauer der Zertifikate gilt die Anforderung [GS-A\_3080].

Hinweis: "Tagesgenau" bedeutet, dass der Zeitpunkt sich nicht im Kalenderdatum, jedoch in der Uhrzeit unterscheiden darf. 

Tabelle #: Tab\_KRYPT\_003 Algorithmen für X.509-Identitäten zur Erstellung qualifizierter elektronischer Signaturen für die Schlüsselgeneration „RSA“ 

|**Anwendungsfälle**|**Vorgaben**|
| :- | :- |
|Signatur des VDA-Zertifikats|Nachdem die eIDAS-Verordnung das Signaturgesetz vollständig abgelöst hat, steht es einem VDA frei zu entscheiden welche Signatur (bspw. signiert von einer beliebigen VDA-internen CA) sein VDA-Zertifikat haben soll. Insbesondere kann die Signatur mit einem Nicht-RSA-Verfahren erstellt werden.<br>Eine auswertende Komponente muss mit beliebigen (also auch nicht-RSA basierten) Signaturen eines VDA-Zertifikats umgehen können (bspw. Signatur des VDA-Zertifikats nicht auswerten, Authentizität und Integrität des Zertifikats wird über die Vertrauensliste sichergestellt).|
|Art und Kodierung des öffentlichen EE-Schlüssels|RSA-Signaturvariante:<br>**Entweder**<br>OID 1.2.840.113549.1.1.1 (rsaEncryption)<br>(zulässig bis Ende 2022 [SOG-IS-2020]) <br>**oder**<br>OID 1.2.840.113549.1.1.10 (id-RSASSA-PSS) [RFC-5756].<br>(ohne zeitliche Beschränkung der Zulässigkeit [SOG-IS-2020])<br>Die Auswahl obliegt dem EE-Zertifikatsausgebenden VDA.<br><br>RSA-Schlüssellänge:<br>zu verwendende Schlüssellänge: 2048 Bit, zulässig bis vgl. Angabe in [SOG-IS-2020]|
|Signatur eines<br>Zertifikats,<br>Signatur einer OCSP-Response oder<br>Signatur eines OCSP-Responder-Zertifikates|**Entweder**<br>sha256withRSAEncryption (OID 1.2.840.113549.1.1.11)<br>(zulässig bis Ende 2022 [SOG-IS-2020])<br>**oder**<br>id-RSASSA-PSS (1.2.840.113549.1.1.10) [RFC-5756]<br>(ohne zeitliche Beschränkung der Zulässigkeit [SOG-IS-2020])<br><br>zu verwendende Schlüssellänge: 2048 Bit, zulässig bis vgl. Angabe in [SOG-IS-2020]<br><br>Die Hashfunktion für die Hashwertberechnung der TBSCertificate-Datenstruktur MUSS eine nach [SOG-IS-2020] zulässige Hashfunktion („Agreed Hash Function“) sein. Als Hashfunktion SOLL SHA-256 [FIPS-180-4] verwendet werden.<br>Als MGF MUSS MGF1 [PKCS#1] verwendet werden. Die innerhalb der MGF1 verwendete Hashfunktion MUSS die gleiche Hashfunktion sein, wie die Hashfunktion der Hashwertberechnung der TBSCertificate-Datenstruktur. (Dies entspricht der Empfehlung aus [RFC-5756] bzw. [RFC-4055, 3.1] und dient der Komplexitätsreduktion.)<br>Die Saltlänge MUSS mindestens 256 Bit betragen.(Die Maximallänge des Salts ergibt sich nach [PKCS#1] in Abhängigkeit von der Länge des Moduls.)|

Tabelle #: Tab\_KRYPT\_003a Algorithmen für X.509-Identitäten zur Erstellung qualifizierter Signaturen für die Schlüsselgeneration „ECDSA“ 

|**Anwendungsfall**|**Vorgabe**|
| :- | :- |
|Signatur des VDA-Zertifikats|Nachdem die eIDAS-Verordnung das Signaturgesetz vollständig abgelöst hat, steht es einem VDA frei zu entscheiden welche Signatur (bspw. signiert von einer beliebigen VDA-internen CA) sein VDA-Zertifikat haben soll. Insbesondere kann die Signatur mit einem Nicht-ECDSA-Verfahren erstellt werden.<br>Eine auswertende Komponente muss mit beliebigen (also auch nicht-ECDSA basierten) Signaturen eines VDA-Zertifikats umgehen können (bspw. Signatur des VDA-Zertifikats nicht auswerten, Authentizität und Integrität des Zertifikats wird über die Vertrauensliste sichergestellt).|
|Art und Kodierung des öffentlichen<br>EE-Schlüssels|ecPublicKey {OID 1.2.840.10045.2.1}<br>auf der Kurve brainpoolP256r1 [RFC-5639#3.4, brainpoolP256r1]<br>zulässig bis Ende 2023+<br><br>Die Kodierung des öffentlichen Punkt erfolgt nach [RFC5480, Abschnitt 2], vgl. Beispiel in Abschnitt 5.2). Der private Schlüssel muss zufällig und gleichverteilt aus {1, …, q-1} gewählt werden. (q ist die Ordnung des Basispunkts und ceil(log2 q)=256 ).|
|Signatur eines<br>Zertifikats,<br>Signatur einer OCSP-Response oder<br>Signatur eines OCSP-Responder-Zertifikates|ecdsa-with-SHA256 [RFC-3279] {OID 1.2.840.10045.4.3.2}<br>auf Kurve der brainpoolP256r1 [RFC-5639#3.4, brainpoolP256r1]<br>zulässig bis Ende 2023+<br><br>vgl. Beispiel in Abschnitt 5.2|
CV-Identitäten werden für die Authentifizierung zwischen Karten verwendet.

Tabelle #: Tab\_KRYPT\_006 Algorithmen für CV-Zertifikate 

|**Algorithmen Typ**|**Algorithmus**|**Schlüssellänge**|
| :- | :- | :- |
|über das Zertifikat bestätigtes Schlüsselpaar|**Authentisierung ohne Sessionkey-Aushandlung**<br>[RFC-5639#3.4, brainpoolP256r1]<br>ecdsa-with-SHA256<br>{OID 1.2.840.10045.4.3.2}<br><br>**Authentisierung mit Sessionkey-Aushandlung**<br>[RFC-5639#3.4, brainpoolP256r1]<br>authS\_gemSpec-COS-G2\_ecc-with-sha256<br>{OID 1.3.36.3.5.3.1}|256 Bit bis Ende 2023+|
|Signatur des Endnutzerzertifikats|[RFC-5639#3.4, brainpoolP256r1]<br>ecdsa-with-SHA256<br>{OID 1.2.840.10045.4.3.2}|256 Bit bis Ende 2023+|
Für die maximale Gültigkeitsdauer der Zertifikate gilt die Anforderung [GS-A\_3080].

Tabelle #: Tab\_KRYPT\_007 Algorithmen für CV-CA-Zertifikate 

|**Algorithmen Typ**|**Algorithmus**|**Schlüssellänge**|
| :- | :- | :- |
|über das Zertifikat bestätigtes Schlüsselpaar|[RFC-5639#3.4, brainpoolP256r1]<br>ecdsa-with-SHA256<br>{OID 1.2.840.10045.4.3.2}|256 Bit bis Ende 2023+|
|Signatur des CA-Zertifikates|[RFC-5639#3.4, brainpoolP256r1]<br>ecdsa-with-SHA256<br>{OID 1.2.840.10045.4.3.2}|256 Bit bis Ende 2023+|
Für die maximale Gültigkeitsdauer der Zertifikate gilt die Anforderung [GS-A\_3080].

(Hinweis: dies ist das ehemalige „Kapitel 5.2.4 Hilfestellung bei der Umsetzung der Anforderungen“. Der Text in diesem Abschnitt entstand in enger Abstimmung mit dem BSI auf Gesellschafterwunsch.)

Die Sicherheit eines deterministischen Zufallszahlengenerators (DRNGs) hängt maßgeblich von drei Faktoren ab:

- von der Entropie des Seeds,
- vom algorithmischen Anteil (generelles Design) und
- dem Schutz des inneren Zustands (und der zur Ausgabe vorgesehenen Zufallszahlen).

Der Nachweis, dass der algorithmische Anteil eines DRNGs den Anforderungen einer bestimmten Funktionalitätsklasse genügt, kann schwierig und aufwändig sein. Deshalb wurde das BSI gebeten, die DRNGs in [FIPS-186-2+CN1] und [ANSI-X9.31] in Bezug auf die kryptographische Güte ihres algorithmischen Anteils zu bewerten.

Das Ergebnis ist:

A) [FIPS-186-2+CN1]: Lässt man in dem DRNG aus Appendix 3.1 (S. 16f.) in Schritt 3c bzw. in dem DRNG aus Algorithmus 1 (Change Notice 1, S. 72f.) in Schritt 3.3 den Term "mod q" weg, so werden gleich verteilt 160-Bit Zufallszahlen bzw. 320-Bit Zufallszahlen erzeugt (vgl. Abschnitt „General Purpose Random Number Generation“ (Change Notice 1, S. 74)).    
Beide DRNGs sind dann 

1. algorithmisch geeignet für die Klasse K4 [AIS-20-1999] und
1. erfüllen die algorithmischen Anforderungen aus DRG.3 [AIS-20].

Ob eine konkrete Implementierung eines dieser DRNG bspw. Teil der Klasse DRG.3 ist, bleibt im Einzelfall zu prüfen, da dazu u. a. auch Fragen über die Initialisierung zu beantworten sind (vgl. (DRG.3.1) [KS-2011]).

Das BSI empfiehlt bei den Zufallsgeneratoren aus [FIPS-186-2+CN1] nach Möglichkeit SHA-256 [FIPS-180-4] anstatt SHA-1 zu verwenden. Folgt man der Empfehlung, so ist der Algorithmus dementsprechend zu adaptieren.

B) [ANSI-X9.31]: Der Zufallsgenerator aus Appendix A.2.4 ist

(1) algorithmisch geeignet für die Klasse K3 [AIS-20-1999] und

(2) erfüllt die algorithmischen Anforderungen aus DRG.2 [AIS-20].

*Hinweis: im Rahmen der Sicherheitszertifizierung von Komponenten, wie bspw. des Konnektors, wird dies überprüft.*

*Hinweis: Dies ist eine Anforderung an Kartenherausgeber, die so sicherstellen müssen, dass das in den Sicherheitsmodulen (also auch HSM-B) zur Verfügung stehende kryptographische Schlüsselmaterial geeignet ist Daten mit sehr hohem Schutzbedarf schützen zu können. (siehe auch Kapitel 4.4)*

Aufgrund des geringeren Mengengerüsts bei HBA und SMC-B ist dort die On-Card-Generierung der entsprechenden Schlüsselpaare möglich. Somit (vgl. auch [PP-0082, FPT\_EMS.1] ist technisch sichergestellt, dass keine Kopie der privaten Schlüssel außerhalb der Chipkarte existiert (Kontext: Ende-zu-Ende-Verschlüsselung von medizinischen Daten).

Für private Schlüssel bei HBA und SMC-B wird die kartenindividuelle Erzeugung und Personalisierung durch GS-A\_5338 technisch sichergestellt. Je nach verwendetem COS, insbesondere dessen spezifischen Personalisierungsverfahrens, kann es sein, dass ein Kartenherausgeber symmetrische Schlüssel aus technischen Gründen personalisieren muss, obwohl er später nicht plant mit diesen Schlüsseln bspw. im Rahmen eines CMS zu arbeiten. Es ist sicherheitskritisch, dass auch diese symmetrischen Schlüssel ebenfalls die Anforderungen GS-A\_5021 bzw. GS-A\_4368 erfüllen.

Als geeignete Schlüsselableitungsverfahren (KDF) für die Erzeugung von kartenindividuellen Schlüssel sind bspw. folgende Verfahren geeignet:

- alle Verfahren aus [NIST-SP-800-108] mittels CMAC [NIST-SP-800-38B],
- alle Verfahren aus [NIST-SP-800-56-A] bzw. [NIST-SP-800-56-B] mittels jeder nach [BSI-TR-03116-1] zulässigen Hashfunktion,
- alle Verfahren aus [NIST-SP-800-56C] mittels CMAC [NIST-SP-800-38B] oder eines HMAC, der auf einer nach [BSI-TR-03116-1] zulässigen Hashfunktion basiert,
- das Verfahren nach [ANSI-X9.63, Abschnitt 5.6.3] mittels jeder nach [BSI-TR-03116-1] zulässigen Hashfunktion.

TSPs, die im Internet TLS-Zertifikate ausgeben (bspw. für die Verwendung von HTTPS), müssen aufgrund der Baseline Requirement des CA/Browser Forums (<https://cabforum.org/baseline-requirements-documents/> ) vor der Zertifikatserzeugung kryptographische Prüfungen des zu bestätigenden öffentlichen Schlüssels durchführen. Analog gilt dies mit   auch für TI-TSPs. Die gematik stellt auf Anfrage eine Beispielimplementierung für die Tests des Mindestumfangs bereit.  

Hinweis: Diese Kodierungsform (uncompressed encoding) ist auch die Form, wie sie letztendlich in den X.509-Zertifikaten verwendet wird. Weiterhin kann ein TSP in dieser Form mit der Prüfung aus GS-A\_5518 sicherstellen, dass keine Fehlkodierung des zu bestätigenden ECC-Schlüssels aufgetreten ist.

Erläuterungen zu  befinden sich in Abschnitt .  

Erläuterungen zu   befinden sich in Abschnitt . 

In den nachfolgenden Abschnitten werden die kryptographischen Algorithmen für verschiedene Einsatzszenarien spezifiziert. In diesem Zusammenhang sind ausschließlich die kryptographischen Aspekte der Einsatzszenarien relevant.


![](Aspose.Words.2d194658-3910-4b4a-bf6b-abf9f3411a63.001.png)

Abbildung #: Verwendung von Algorithmen nach Zonen und OSI-Schicht 

Abbildung 1 stellt beispielhaft die für die Vertraulichkeit von medizinischen Daten relevanten Algorithmen auf den verschiedenen OSI-Schichten in einer Übersicht dar. Es besteht in dieser Abbildung kein Anspruch auf Vollständigkeit.

XML-Signaturen sind bezüglich der verwendeten Algorithmen selbst beschreibend, die für die Erstellung einer Signatur verwendeten Algorithmen sind in der Signatur aufgeführt.

Zur vollständigen Spezifikation der Algorithmen für XML-Signaturen müssen für alle Signaturbestandteile Algorithmen spezifiziert werden. Die nachfolgenden Abschnitte wählen aus der Menge der zulässigen Algorithmen die jeweiligen Algorithmen für die einzelnen Einsatzszenarien aus.

Die Referenzierung von Algorithmen in XML-Signaturen und XML-Verschlüsselungen erfolgt nicht wie in Zertifikaten oder Signaturen binärer Daten über OIDs sondern über URIs. Die URIs der Algorithmen dienen als eindeutige Identifier und nicht dazu, dass unter der jeweils angegebenen URI die Beschreibung zu finden ist.

Tabelle #: Tab\_KRYPT\_008 Beispiele für solche Algorithmen-URIs 

|**Algorithmen Identifier** |**Erläutert in** |
| :- | :- |
|<http://www.w3.org/2001/04/xmlenc#aes256-cbc> |[XMLEnc] |
|<http://www.w3.org/2001/04/xmlenc#rsa-1_5> |[XMLEnc] |
|<http://www.w3.org/2001/04/xmlenc#sha256> |[XMLDSig] |
|<http://www.w3.org/2000/09/xmldsig#enveloped-signature> |[XMLDSig] |
|<http://www.w3.org/2001/04/xmldsig-more#rsa-sha256> |[RFC-4051] bzw. [RFC-6931] |
|[http://www.w3.org/2001/10/xml-exc-c14n#](http://www.w3.org/2001/10/xml-exc-c14n) |[XMLCan\_V1.0] |
|<http://www.w3.org/2009/xmlenc11#aes256-gcm> |[XMLEnc-1.1] |
|<http://www.w3.org/2007/05/xmldsig-more#sha256-rsa-MGF1> |[RFC-6931] |
Tabelle #: Tab\_KRYPT\_009 Algorithmen für die Erzeugung von nicht-qualifizierten elektronischen XML-Signaturen 

|**Signaturbestandteil**|**Beschreibung**|**Algorithmus**|**Anmerkung**|
| :- | :- | :- | :- |
|Signaturstandard|Signaturstandard|ETSI TS 101 903 V1.4.2 (2010-12)<br>Electronic Signatures and Infrastructures (ESI); XML Advanced Electronic Signatures (XAdES)<br>[ETSI-XAdES]|Die Verwendung des Standards ist für die Signatur von XML-Dokumenten verpflichtend, die nicht über CMS [RFC-5652] signiert werden.|
|kryptographisches Signaturverfahren|Algorithmus für die Berechnung des Nachrichten Digest und die Verschlüsselung mit dem privaten Schlüssel|RSASSA-PSS mit SHA256<br>bis nach Ende 2024+ verwendbar (Ende des Betrachtungshorizonts)<br><br>(Hinweis: siehe Abschnitt 4.1)|Die Verwendung des Algorithmus ist verpflichtend.<br><br>Alle hier aufgeführten Signaturverfahren müssen von einer Signaturprüfenden Komponente überprüfbar sein.|
|DigestMethod|Methode zur Berechnung eines Digest der zu signierenden Bereiche|SHA-256<br>Die [XMLDSig] konforme Bezeichnung lautet:<br><http://www.w3.org/2001/04/xmlenc#sha256>|Die Verwendung des Algorithmus ist verpflichtend.|
|Kryptographisches Token|Kryptographisches Token für die Signatur, bestehend aus einem privaten Schlüssel und einem zugehörigen X.509-Zertifikat|Identitäten gemäß einem der folgenden Abschnitte<br>2.1.1.1|Die Auswahl des kryptographischen Tokens ist von dem jeweiligen Einsatzzweck abhängig.|
Tabelle #: Tab\_KRYPT\_010 Algorithmen für qualifizierte XML-Signaturen 

|**Signaturbestandteil** |**Beschreibung** |**Algorithmus** |**Anmerkung** |
| :- | :- | :- | :- |
|Signaturstandard |Signaturstandard |ETSI TS 101 903 V1.4.2 (2010-12)<br>Electronic Signatures and Infrastructures (ESI); XML Advanced Electronic Signatures (XAdES)<br>[ETSI-XAdES] |Die Verwendung des Standards ist für die Signatur von XML-Dokumenten verpflichtend, die nicht über CMS [RFC-5652] signiert werden. |
|kryptographisches Signaturverfahren |Algorithmus für die Berechnung des Nachrichten-Digest und die Verschlüsselung mit dem privaten Schlüssel |RSASSA-PSS mit SHA256<br>bis nach Ende 2023+ verwendbar (Ende des Betrachtungshorizonts)<br><br>(Hinweis: siehe Abschnitt 4.1) |Der Algorithmus muss für alle qualifizierten Signaturen verwendet werden.<br><br>Alle hier aufgeführten Signaturverfahren müssen von einer Signaturprüfenden Komponente überprüfbar sein. |
|DigestMethod |Methode zur Berechnung eines Digest der zu signierenden Bereiche |SHA-256<br>Die [XMLDSig] konforme Bezeichnung lautet:<br><http://www.w3.org/2001/04/xmlenc#sha256> |Der Algorithmus muss für alle qualifizierten Signaturen verwendet werden. |
|Kryptographisches Token |Kryptographisches Token für die Signatur, bestehend aus einem privaten Schlüssel und einem zugehörigen X.509-Zertifikat |Identitäten gemäß dem folgenden Abschnitt<br>2.1.1.2 |Es darf nur eine Identität, die den Ansprüchen qualifizierter Signaturen entspricht, verwendet werden. |
Nicht relevant für den Wirkbetrieb der TI.

Das Verfahren zur Durchführung der Card-to-Card-Authentisierung wird in [gemSpec\_COS] spezifiziert.

Das Verfahren zur Durchführung der Card-to-Server-Authentisierung wird in [gemSpec\_COS] spezifiziert.

C2S-Authentisierung bzw. der Trusted-Channel wird zwischen der Karte und dem zugeordneten Management-System verwendet.

Der Algorithmus AES ist nach [BSI-TR-03116-1] in der TI bis Ende 2024+ (meint bis Ende des Betrachtungsraums der TR) zulässig.

Tabelle #: Tab\_KRYPT\_012 Algorithmen für Card-to-Server-Authentifizierung 

|**Algorithmen Typ**|**Algorithmus**|**Schlüssellänge**|
| :- | :- | :- |
|Authentifizierung und Verschlüsselung der Authentisierungsdaten|AES im CBC-Modus<br>(OID 2.16.840.1.101.3.4.1)|128 Bit<br>zulässig bis Ende 2023+|
Im Gegensatz zu kryptographischen Verfahren für den Integritätsschutz oder die Vertraulichkeit von Daten, bei denen keine direkte Kommunikation zwischen dem Sender bzw. dem Erzeuger und dem Empfänger stattfindet, kann bei Netzwerkprotokollen eine Aushandlung des kryptographischen Algorithmus erfolgen. Das Ziel der nachfolgenden Festlegungen ist es daher, jeweils genau einen verpflichtend zu unterstützenden Algorithmus festzulegen, so dass eine Einigung zumindest auf diesen Algorithmus immer möglich ist. Zusätzlich können aber auch optionale Algorithmen festgelegt werden, auf die sich Sender und Empfänger ebenfalls im Zuge der Aushandlung einigen können. Es darf jedoch durch keine der Komponenten vorausgesetzt werden, dass der Gegenpart diese optionalen Algorithmen unterstützt.

*Hinweis-4382-1: In [NK-PP] wird mit FCS\_COP.1/NK.HMAC und FCS\_COP.1/NK.Hash die Unterstützung von SHA-1 und SHA-256 gefordert. Da für den Einsatz innerhalb einer HMAC-Funktion und innerhalb einer PRF die Einwegeigenschaft der Hashfunktion im Vordergrund steht und nicht die allgemeine Kollisionsresistenz, ist dort der Einsatz von SHA-1 noch zulässig (vgl. auch [BSI-TR-02102-3, Abschnitt 3.2.2, Tabelle 3, 4 und 8]). Es ist davon auszugehen, dass die Zulässigkeit von SHA-1 bei diesen beiden Einsatzzwecken zukünftig nicht mehr gegeben sein kann, und sowohl im NK als auch im VPN-Zugangsdienst, bspw. per Konfiguration, deaktiviert werden muss.*

Ziel ist es zum Zeitpunkt der IKE-SA-Reauthentication ausgeführte Anwendungsfälle nicht zu unterbrechen. Aktuell wird aufgrund von TIP1-A\_4492 im Rahmen der Reauthentication dem Konnektor eine neue (i.d.R. andere) VPN-TI-IP-Adresse zugewiesen, was dazu führt, dass bestehende TCP-Verbindungen in die TI effektiv zerstört und laufende Anwendungsfälle unterbrochen werden. Perspektivisch wird die folgende Anforderung als MUSS-Anforderung in TIP1-A\_4492 integriert.

Da noch nicht alle VPN-Zugangsdienste technisch in der Lage sind GS-A\_5547 umzusetzen werden als Symptomlinderung die Gültigkeitsdauern der ausgehandelten Schlüssel erhöht, auch in Anbetracht, dass weitere Sicherheitsmaßnahmen (bspw. TIP1-A\_5389) umgesetzt werden neben den klassischen Prüfungen, die im Rahmen einer Reauthentication durchgeführt werden.

Auszug Beispielkonfiguration /etc/ipsec.conf

`    `ikelifetime=161h
`    `lifetime=23h
`    `margintime = 20m
`    `rekeyfuzz = 40%
`    `keyexchange=ikev2

Bei TLS 1.1 oder älter ist im Rahmen des TLS-Verbindungsaufbaus die Verwendung von SHA-1 bei der Erstellung und Prüfung von Signaturen (TLS-Handshake) notwendig. Es gibt keine Möglichkeit der Aushandlung/Vereinbarung der Verwendung von kryptographisch höherwertigeren Hashfunktionen dafür. Dies wurde erst mit TLS 1.2 möglich. SHA-1 erbringt in Konstruktionen, die nur die kryptographische Einwegeigenschaft der Hashfunktion benötigen (bspw. bei der HMAC-Berechnung auf SHA-1-Basis) noch ein -- zwar nicht hochwertiges, aber immer noch -- vertretbares Sicherheitsniveau. Die allgemeine Kollisionsresistenz, so wie sie bei Signaturen notwendig ist, kann SHA-1 nicht mehr leisten. SHA-1 wurde in diesem Aspekt praktisch (i. S. v. nicht nur theoretisch) -- und öffentlichkeitswirksam demonstriert -- gebrochen. Aus diesem Grunde hat die IETF alle TLS Version unter 1.2 abgekündigt und bspw. alle Webbrowser-Hersteller haben die Unterstützung von TLS-Versionen unter 1.2 deaktiviert.

Analog zu IKE/IPsec und  (Spiegelstrich 5) wird deshalb folgend mit A\_21275 eine Verwendung von SHA-1 bei der Signaturerstellung und -prüfung im Kontext des TLS-Handshakes untersagt. 

Umsetzunghinweise zu A\_21275-\*:

Bei den Anwendungsfällen der TI-Anwendungen sind die Mehrzahl der TLS-Verbindungen einseitig authentisiert. D. h. beim TLS-Handshake signiert nur der TLS-Server dessen (EC)DH-Schlüssel. Bei der Initiierung der TLS-Verbindung sendet der TLS-Client in der "signature\_algorithms"-Extension beim ClientHello. In der Extension werden alle vom Client unterstützen Hashfunktionen kodiert. Dort muss also nach A\_21275-\* mindestens SHA-256 enthalten sein. Bei TLS 1.2 wird von fast allen TLS-Bibliotheken ebenfalls SHA-1 angegeben, dieses Verhalten lässt sich im Normalfall nicht ohne Code-Änderungen in den Bibliotheken verändern -- dieses Verhalten widerspricht zunächst A\_21275-\*. Das bloße Aufführen von SHA-1 als grundsätzlich unterstützte Hashfunktion soll nicht als fehlerhaftes Verhalten gelten. Wichtig für die Umsetzung von A\_21275-\* sind die tatsächlich erstellten Signaturen und die Prüfung dieser Signaturen.

Informationen zu Algorithmen in der "signature\_algorithms"-Extension findet man in [RFC-5246#7.4.1.4.1.] und [RFC-8446-4.2.3.], vgl. auch [RFC-9155].

Für Embedded-Systeme (Konnektor, eHealth-KT) ist in diesem Zusammenhang lesenswert: [Oorschot-Wiener-1996].

Einen lesenswerten Abriss bekannter Angriffe auf TLS findet man in [TLS-Attacks], vgl. auch [Breaking-TLS].

Bei  bestimmten  Produkttypen,  bspw.  TSPs,  beschränkt  sich  die  Prüfung  von  Zertifikaten beim TLS-Verbindungsaufbau in Bezug auf die TI ausschließlich auf die Prüfung des Zertifikats des Service Monitorings oder anderer betriebsunterstützender Dienste. Dafür ist der TUC\_PKI\_018 unangemessen leistungsstark und komplex. Deshalb wird folgend mit GS-A\_5581 eine passgenauere Zertifikatsprüfung als Alternative definiert.

Als Hilfestellung: für die Umsetzung von GS-A\_5581 Spiegelstrich (1) kann man bspw. folgende Maßnahmen wählen.

(a) Übergabe bei einem Vororttermin in der gematik,

(b) Regelmäßiger Download über https://download.tsl.ti-dienste.de/

(c)  Verwendung  einer  dedizierten  Software  zum  Download,  Signaturprüfung  und Auswertung  der  TI-TSL  (es  existiert  dafür  jeweils mindestens eine Open-Source-Lösung und eine kommerzielle Lösung) 

(d) oder andere Lösung, die die Integrität und Authentizität der Zertifikate sicherstellt.

Ziel ist es, dass für die Verbindung zur Störungsampel oder zum Service Monitoring auch einfach verfügbare und einfach verwendbare HTTPS-Clienten wie wget oder curl verwendet werden können.

Unter der Annahme, dass

(a) im Verzeichnis /etc/TI-Komponenten-CAs die in GS-A\_5581 Punkt (1) aufgeführten Zertifikate liegen und

(b) die an die Störungsampel zu sendende Information (i. d. R. unsignierte XML-Daten) in der Datei SOAP\_Daten liegen,
erfüllen folgende Aufrufe die Punkt (2)-(4) aus GS-A\_5581.
I.
wget --ca-directory=/etc/TI-Komponenten-CAs --post-file=SOAP\_Daten https://monitoring-update.stampel.telematik:8443/I\_Monitoring\_Message
II.
curl --capath /etc/TI-Komponenten-CAs –d SOAP\_Daten https://monitoring-
update.stampel.telematik:8443/I\_Monitoring\_Message

Sicherheitsziel bei der Verwendung von TLS in der TI ist die Forward Secrecy [BSI-TR-02102-1, S. ix], was sich u. a. in den vorgegebenen Cipher-Suites (vgl.  und  ) widerspiegelt. Um dieses Ziel zu erreichen, muss sichergestellt werden, dass in regelmäßigen Abständen frisches Schlüsselmaterial über einen authentisierten Diffie-Hellman-Schlüsselaustausch gebildet wird, welches das alte Material ersetzt, wobei das alte Material sowohl im Klienten als auch im Server sicher gelöscht wird. Insbesondere bei der Nutzung von TLS-Resumption (vgl. [RFC-5246, S. 36] oder [RFC-5077]) kann die Dauer einer TLS-Session deutlich länger sein als die Lebensdauer der TCP-Verbindung innerhalb welcher der initiale Schlüsselaustausch stattgefunden hat. Aus diesem Grunde werden analog zu den IPsec-Vorgaben (vgl. [gemSpec\_Krypt#GS-A\_4383]) Vorgaben für die maximale Gültigkeitsdauer dieses Schlüsselmaterials gemacht (vgl. auch [SDH-2016]). 

Aktuell gibt es in der TI keine Anwendungsfälle (Wechsel der kryptographischen Identität innerhalb einer TLS-Verbindung oder erzwungene Schlüssel-„Auffrischung“ der Sitzungsschlüssel), die eine Session-Renegotiation im Rahmen von TLS unmittelbar erforderlich machen. Lesenswert bez. des Themas Sicherheitsprobleme mit TLS-Session-Renegotiation ist [IR-2014, S.181ff] und allgemein [CM-2014].

Es hat sich gezeigt, dass es notwendig ist weitere Vorgaben zur TLS-Renegotiation für die Sicherstellung der Interoperabilität zwischen Komponenten und Diensten zu machen.

Für eine Java-Implementierung bedeutet dies, dass allowLegacyHelloMessages und allowUnsafeRenegotiation jeweils auf false gesetzt sind ("Modus Strict", <http://www.oracle.com/technetwork/java/javase/overview/tlsreadme2-176330.html> ). 

Da der Angriff [Ray-2009], der zur Erstellung des [RFC-5746] führte, praktisch durchführbar war, wurde die Mehrzahl der existierenden TLS-Bibliotheken relativ zügig angepasst (Timeline in [IR-2014, S. 190, Abbildung 7.2]). (Vgl. die erste Spalte „Secure Renegotiation“ bei <https://en.wikipedia.org/wiki/Comparison_of_TLS_implementations#Extensions> ) Um für den unwahrscheinlichen Fall, dass aktuell ein schon bestehender Fachdienst Probleme bei der Umsetzung der folgenden Anforderung hat, wurde diese als SOLL-Anforderung formuliert. Es ist geplant diese Anforderung zukünftig in eine MUSS-Anforderung zu ändern. 

Die folgende Anforderung hat den Zweck die Interoperabilität zwischen Konnektor und Intermediär sicherzustellen.

Für eine verbesserte Interoperabilität zu bestimmten TLS-Implementierungen (bspw. SChannel, vgl. auch ( <https://en.wikipedia.org/wiki/Comparison_of_TLS_implementations> bzw. <https://www.ssllabs.com/ssltest/clients.html>) sollen im Konnektor zusätzlich zu den Cipher-Suiten aus GS-A\_4384 weitere Cipher-Suiten unterstützt werden. Mit der mittelfristigen Anhebung des zu erreichenden Sicherheitsniveaus auf 120 Bit (vgl. [SOG-IS-2020] und [BSI-TR-03116-1]) werden die folgenden Cipher-Suiten mittelfristig verpflichtend. In diesem Kontext spielt die Performanz (3000 Bit Diffie-Hellman vs. 256 Bit Elliptic Curve Diffie-Hellman) bei Embedded-Geräten wie dem Konnektor eine wichtige Rolle. 

Von einem TLS-Server, dessen Kommunikationspartner Standard-Webbrowser sind (bspw. einem Webserver), wird wie folgt eine Webbrowser-Interoperabilität bez. der unterstützten TLS-Cipher-Suiten gefordert.

Hinweis: hinter den folgenden Identifier-n verbirgt sich kryptographisch gesehen jeweils die gleiche Kurve:

|**ansix9p256r1**|**[ANSI-X9.62#L.6.4.3]**|
| :- | :- |
|ansip256r1|<http://oid-info.com/get/1.2.840.10045.3.1.7>|
|prime256v1|[RFC-3279],<br>openssl ecparam -list\_curves|
|secp256r1|[RFC-5480], <http://www.secg.org/collateral/sec2_final.pdf>|
|P-256 |[FIPS186-4]|
Analog P-384 [FIPS186-4]:

|**ansix9p384r1**|**[ANSI-X9.62#L.6.5.2]**|
| :- | :- |
|ansip384r1|<http://oid-info.com/get/1.3.132.0.34>|
|prime384v1|[RFC-3279],<br>openssl ecparam -list\_curves|
|secp384r1|[RFC-5480], <http://www.secg.org/collateral/sec2_final.pdf>|
|P-384 |[FIPS186-4]|

Der VZD wird u. Um. direkt von einem Webbrowser angesprochen, daher wird für eine  größere Interoperabilität zu verschiedenen Webbrowsern von ihm die Unterstützung zusätzlicher TLS-Cipher-Suiten gefordert. 

Erläuterung: Eine andere Anwendung des Gesundheitswesens ohne Zugriff auf Dienste der TI in angeschlossenen Netzen des Gesundheitswesens (WANDA Basic) muss beim TLS-basierten Nachrichtentransport durch die TI nach [TR-02102-2] sichere Cipher-Suiten und Domainparameter verwenden. Für solch eine Anwendung ist eine die Interoperabilität mit TI-Diensten sicherstellende Einschränkung der Cipher-Suiten und Domainparameter nach GS-A\_4384 und A\_17124 nicht notwendig, d. h. beide Anforderungen gelten nicht für solche Anwendungen, sondern A\_18183 gilt.

Erläuterung: A\_18986 ”befreit” Produkttypen-interne TLS-Verbindungen von der Beschränkung auf die Vorgaben von GS-A\_4384 und ggf. A\_17124 und erweitert diese Vorgaben auf die Gesamtheit der in [TR-02102-2] empfohlenen TLS-Konfigurationen.

Hinweis: In Abschnitt " " gibt es weitere TLS-Vorgaben. 

Tabelle #: Tab\_KRYPT\_017 Algorithmen für DNSSEC 

|**Algorithmen Typ**|**Algorithmus**|**Schlüssellänge**|
| :- | :- | :- |
|TSIG – symmetrischer Schlüssel zur Absicherung der Transaktionskanäle zwischen zwei Name-Server-Instanzen bei Zonentransfers, Änderungsbenachrichtigungen, dynamischen Updates und rekursiven Queries.|HMAC-SHA-256|256 Bit|
|DNSSEC ZSK<br>Asymmetrische Schlüssel zur Wahrung der Authentizität und Integrität von Zonendatenobjekten.|RSA-SHA-256 [RFC-5702]|2048 Bit|
|DNSSEC KSK<br>Asymmetrische Schlüssel zur Wahrung der Authentizität und Integrität von Zonendatenobjekten.|RSA-SHA-256<br>[RFC-5702]|2048 Bit|
*Hinweis: Nach [RFC-5702] ist die Verwendung von SHA-256 [FIPS-180-4] möglich. Schlüssellängen von RSA zwischen 512 bis 4096 Bit sind seit den Anfängen von DNSSEC möglich. Bei TSIG ist nach [RFC-4635] auch SHA-256 verwendbar und bspw. von bind seit der Version 9.5 unterstützt.*

Die gematik wurde aufgefordert, beispielhaft ein mögliches Ableitungsverfahren für einen versichertenindividuellen symmetrischen Schlüssel auf Grundlage eines Ableitungsschlüssels (Masterkey) aufzuführen. Ein Kartenherausgeber ist frei in der Wahl seines Ableitungsverfahrens. Jedoch müssen beim Einsatz eines Ableitungsverfahrens, um die Qualität der Ableitung zu garantieren, insbesondere folgende Punkte beachtet werden:

- Der Ableitungsprozess muss unumkehrbar und nicht-vorhersehbar sein, um sicherzustellen, dass die Kompromittierung eines abgeleiteten Schlüssels nicht den Ableitungsschlüssel oder andere abgeleitete Schlüssel kompromittiert.
- Bei einer Schlüsselableitung (im Sinne von [ISO-11770]) basiert die kryptographische Stärke der abgeleiteten Schlüssel auf der Ableitungsfunktion und der kryptographischen Stärke des geheimen Ableitungsschlüssels (insbesondere hier dessen Entropie). Die Entropie der abgeleiteten Schlüssel ist kleiner gleich der Entropie des geheimen Ableitungsschlüssels. Um die Entropie der abgeleiteten Schlüssel sicherzustellen, muss die Entropie des geheimen Ableitungsschlüssels (deutlich) größer sein als die zu erreichende Entropie der abgeleiteten Schlüssel.
- Der Betreiber eines Schlüsseldienstes muss im Falle des Einsatzes einer Schlüsselableitung (nach [ISO-11770]) in seinem Sicherheitskonzept Maßnahmen für das Bekanntwerden von Schwächen des kryptographischen Verfahrens, welche die Grundlage der Schlüsselableitung ist, darlegen.

Ein Kartenherausgeber hat auch die Freiheit, gar kein Ableitungsverfahren zu verwenden, sondern alle symmetrischen SK.CMS aller seiner Karten sicher in seinem RZ vorzuhalten.

Ziel des Masterkey-Verfahrens zur Ableitung eines versichertenindividuellen Schlüssels ist es, aus einem geheimen Masterkey und einem öffentlichen versichertenindividuellen Merkmal einen geheimen symmetrischen Schlüssel abzuleiten, der zur Absicherung der Verbindung zwischen CMS und Smartcard verwendet wird. Öffentlich bedeutet an dieser Stelle nicht, dass die Merkmale selbst nicht schützenswert sind, es soll jedoch ausdrücken, dass die Vertraulichkeit des versichertenindividuellen Schlüssels nicht von der Geheimhaltung dieser Merkmale abhängt. Die Vertraulichkeit der Daten muss durch die Geheimhaltung des Masterkeys gewährleistet sein. Das bedeutet, die Geheimhaltung anderer Daten als des Masterkeys darf für die Vertraulichkeit der Daten nicht notwendig sein. Die Durchführung dieses Verfahrens muss bei gleichen Eingangsparametern immer das gleiche Ergebnis generieren.

Für die Durchführung des Algorithmus wird neben dem Masterkey auch noch mindestens ein versichertenindividuelles Merkmal verwendet. Die Auswahl des Merkmals ist fachlich motiviert und wird daher in diesem Dokument nicht spezifiziert. Das in Tabelle 20 beispielhafte Verfahren besteht aus einer Kombination von AES-Verschlüsselung [FIPS-197] und Hashwert-Bildung. Die Schlüssel- bzw. Hashwert-Länge ergibt sich gemäß Tabelle 21.

Tabelle #: Tab\_KRYPT\_018 Ablauf zur Berechnung eines versichertenindividuellen Schlüssels 

|**Reihenfolge**|**Beschreibung**|**Formale Darstellung**|
| :- | :- | :- |
|1|Bildung eines Hashwertes über dem versichertenindividuellen Merkmal unter Verwendung eines statischen Padding-Verfahrens für den Fall, dass das versichertenindividuelle Merkmal in seiner Länge nicht der Blocklänge des Hash-Algorithmus entspricht.<br>Im Ergebnis wird ein versichertenindividuelles Merkmal geeigneter Länge für den nächsten Schritt erzeugt.|HASH#1 =<br>SHA-256(versichertenindividuelles Merkmal)|
|2|AES-Verschlüsselung des Resultats mit dem Masterkey.<br>Durch die Verschlüsselung an dieser Stelle ist sichergestellt, dass der versichertenindividuelle Schlüssel nur durch den Besitzer des geheimen Masterkeys erzeugt werden kann.|ENC#1 = AES-256(HASH#1)|
|3|Bildung eines Hashwertes über dem Ergebnis des vorherigen Verarbeitungsschritts.<br>Dies stellt sicher, dass ein Schlüssel geeigneter Länge erzeugt wird.|Versichertenindividueller Schlüssel =<br>SHA-256(ENC#1)|
In der nachfolgenden Tabelle werden Kürzel entsprechend der Definition aus Abschnitt 3.2.3 verwendet.

Tabelle #: Tab\_KRYPT\_019 eingesetzte Algorithmen für die Ableitung eines versichertenindividuellen Schlüssels 

|**Algorithmen Typ**|**Algorithmus**|**Unterverfahren**|
| :- | :- | :- |
|Masterkey-Verfahren für die Generierung des versichertenindividuellen Schlüssel innerhalb eines CMS|AES basiertes Verfahren gemäß vorheriger Definition|AES-256<br>SHA-256<br>anwendbar bis Ende 2023+|
Für die hybride Verschlüsselung werden die Daten zunächst symmetrisch mittels eines zufällig gewählten geheimen symmetrischen Schlüssels verschlüsselt. Der geheime Schlüssel wird im Anschluss asymmetrisch für jeden Empfänger separat verschlüsselt.

*Hinweis: unter binären Daten sind im gesamten Dokument beliebige Daten insbesondere beliebigen Typs (Text, HTML, PDF, JPG etc.) zu verstehen. Es gilt das Prinzip: das Spezielle vor dem Allgemeinen: gibt es weitere spezielle Vorgaben für bestimmte Datenformate, sind diese für die entsprechenden Daten verpflichtend (überschreiben oder ergänzen die allgemeinen Vorgaben).*

*Hinweis: In [RFC-5084] findet man Informationen über die Verwendung von AES-GCM innerhalb von CMS [RFC-5652].*

*Hinweis: In [RFC-5084] findet man Informationen über die Verwendung von AES-GCM innerhalb von CMS [RFC-5652].*

Tabelle #: Tab\_KRYPT\_020 Algorithmen für die Erzeugung und Prüfung von binären Daten im Kontext von Dokumentensignaturen 

|**Signaturbestandteil**|**Beschreibung**|**Algorithmus**|**Anmerkung**|
| :- | :- | :- | :- |
|Signaturstandard|Signaturstandard|ETSI TS 101 733 V1.7.4 (2008-07)<br>Electronic Signatures and Infrastructures (ESI); CMS Advanced Electronic Signatures (CAdES)<br>[ETSI-CAdES]|Die Verwendung des Standards ist für die Signatur von Dokumenten verpflichtend die mittels CMS [RFC-5652] erzeugt werden.|
|kryptographisches Signaturverfahren|Algorithmus für die Berechnung des Nachrichten Digest und die Verschlüsselung mit dem privaten Schlüssel|**RSASSA-PSS mit SHA256**<br>bis nach Ende 2023+ verwendbar (Ende des Betrachtungshorizonts)|Die Verwendung einer dieser Algorithmen ist verpflichtend.<br><br>Alle hier aufgeführten Signaturverfahren müssen von einer Signaturprüfenden Komponente überprüfbar sein.|
|DigestMethod|Methode zur Berechnung eines Digest der zu signierenden Bereiche|SHA-256|Die Verwendung des Algorithmus ist verpflichtend.|
|Kryptographisches Token|Kryptographisches Token für die Signatur, bestehend aus einem privaten Schlüssel und einem zugehörigen X.509-Zertifikat|Identitäten gemäß einem der folgenden Abschnitte<br>2.1.1.1<br>2.1.1.2|Die Auswahl des kryptographischen Tokens ist von dem jeweiligen Einsatzzweck abhängig.|
Tabelle #: Tab\_KRYPT\_021 Algorithmen für die Erzeugung und Prüfung von PDF/A-Dokumentensignaturen 

|**Signaturbestandteil**|**Beschreibung**|**Algorithmus**|**Anmerkung**|
| :- | :- | :- | :- |
|**Signaturstandard**|Signaturstandard|ETSI TS 102 778-3 V1.2.1,<br>PDF Advanced Electronic Signature Profiles; Part 3: PAdES Enhanced – PAdES-BES and PAdES-EPES Profiles<br>Technical Specification, 2010 [PAdES-3]|Die Verwendung des Standards ist für die Signatur von PDF/A [PDF/A-2] Dokumenten verpflichtend, die mittels eingebetteter Signaturen signiert werden.|
|**kryptographisches Signaturverfahren**|Algorithmus für die Berechnung des Nachrichten Digest und die Verschlüsselung mit dem privaten Schlüssel|**RSASSA-PSS mit SHA256**<br>bis nach Ende 2023+ verwendbar (Ende des Betrachtungshorizonts)|Die Verwendung einer dieser Algorithmen ist verpflichtend.<br><br>Alle hier aufgeführten Signaturverfahren müssen von einer Signaturprüfenden Komponente überprüfbar sein.|
|**DigestMethod**|Methode zur Berechnung eines Digest der zu signierenden Bereiche|**SHA-256**|Die Verwendung des Algorithmus ist verpflichtend.|
|**Kryptographisches Token**|Kryptographisches Token für die Signatur, bestehend aus einem privaten Schlüssel und einem zugehörigen X.509-Zertifikat|Identitäten gemäß einem der folgenden Abschnitte<br>2.1.1.1<br>2.1.1.2|Die Auswahl des kryptographischen Tokens ist von dem jeweiligen Einsatzzweck abhängig.|
Vgl. auch Abschnitt 2.4 (Schlüsselerzeugung).

Erläuterung:

Alle CAs und der TSL-Dienst müssen im Rahmen ihrer Prozesse öffentliche Schlüssel oder Zertifikate (bspw. auf Webseiten) veröffentlichen. Dabei wird auch jeweils der SHA-256 Hashwert mit veröffentlicht.

Hersteller einer gSMC-KT müssen den Hashwert des auf der Karte befindlichen Zertifikats in MF/DF.KT/EF.C.SMKT.AUT.R2048 entweder auf dem ID-1-Kartenkörper drucken (das ID-000-Modul ist dann herausbrechbar) oder ausgedruckt mitliefern. Der Konnektor muss den Hashwert des Zertifikats bei initialen Pairing mit dem KT berechnen und dem Administrator präsentieren.

Innerhalb der CertHash-Extension als Teil einer OCSP-Response wird vom TSP ein SHA-256 Hashwert des Zertifikats, über das eine Sperrinformation gegeben wird, mitgeliefert.

Es hat sich gezeigt, dass zum folgenden Themenkomplex eine Erläuterung hilfreich ist.

Im Zusammenspiel OCSP-Anfrage und OCSP-Antwort werden an drei Stellen Hashfunktionen verwendet, die theoretisch alle paarweise verschieden sein können.

**Erste Stelle:** Zunächst erzeugt ein OCSP-Client eine OCSP-Anfrage (vgl. [RFC-6960, Abschnitt 4.1.1] oder [RFC-2560, Abschnitt 4.1.1]). Dafür muss dieser u. a. eine CertID-Datenstruktur erzeugen: 

`   `CertID          ::=     SEQUENCE {
`       `hashAlgorithm       AlgorithmIdentifier,
`       `issuerNameHash      OCTET STRING, -- Hash of issuer's DN
`       `issuerKeyHash       OCTET STRING, -- Hash of issuer's public key
`       `serialNumber        CertificateSerialNumber }

Bei der Wahl der Hashfunktion kann er sich nur darauf verlassen, dass der OCSP-Responder als Hashalgorithmus (vgl. „hashAlgorithm“-Datenfeld) SHA-1 [FIPS-180-4] unterstützt. Für den Anfragenden und den OCSP-Responder gilt dementsprechend GS-A\_5131. Er muss SHA-1 für die CertID-Struktur verwenden. Ein OCSP-Responder, der zusätzlich weitere Hashfunktionen unterstützt, muss nichts zurückbauen – er darf auch so in der TI arbeiten.

Warum ist der Einsatz von SHA-1 an dieser Stelle kryptographisch gesehen ausreichend? Da (1) ein OCSP-Responder der TI nicht für beliebige CAs arbeitet (Wahl von DN und öffentlichen Schlüssel ist damit beschränkt) und (2) i. d. R. die CertHash-Extension Teil der OCSP-Antwort ist und innerhalb der CertHash-Extension in der TI eine kryptographisch hochwertige Hashfunktion verwendet wird, ist die Verwendung von SHA-1 hier aus Sicherheitssicht betrachtet unbedenklich. (Vgl. analoges Vorgehen BNetzA-OCSP-Responder für den qualifizierten Vertrauensraum.) Es ist also sichergestellt, dass zwischen OCSP-Client und -Responder keine (evtl. von einem Angreifer böswillig herbeigeführten) Unklarheiten darüber entstehen können über welches Zertifikat gerade gesprochen wird. Es geht bei GS-A\_5131 vornehmlich um die Interoperabilität von OCSP-Client und OCSP-Responder.

Die optionale Signatur einer OCSP-Anfrage wird in der TI nicht verwendet, damit ist die dort verwendete Hashfunktion für die aktuelle Betrachtung irrelevant.

**Zweite Stelle:** Für die Beantwortung der OCSP-Anfrage erzeugt der OCSP-Responder u. a. eine CertHash-Datenstruktur: 

id-commonpki-at-certHash OBJECT IDENTIFIER ::= {1 3 36 8 313}
CertHash ::= SEQUENCE {
`     `hashAlgorithm   AlgorithmIdentifier,  -- The identifier
`     `-- of the algorithm that has been used the hash value below.
`     `certificateHash OCTET STRING }

Hierfür muss eine kryptographisch hochwertige (nach [BSI-TR-03116-1] zulässige) Hashfunktion verwendet werden. Normativ ist an dieser Stelle: „GS-A\_4393 Algorithmus bei der Erstellung von Hashwerten von Zertifikaten oder öffentlichen Schlüsseln“. Spätestens an dieser Stelle können OCSP-Client und OCSP-Server sich sicher sein, ob sie über das gleiche Zertifikat sprechen.

**Dritte Stelle:** Die OCSP-Response muss am Ende vom OCSP-Responder signiert werden. Dafür ist die Vorgabe aus Tab\_KRYPT\_002 „Signatur der OCSP-Response“ normativ, welche über die für die jeweiligen Zertifikate geltenden Anforderungen (bspw. GS-A\_4357) angezogen werden. 

Erläuterung: Beim initialen Pairing zwischen Konnektor und eHealth-Kartenterminal wird vom Konnektor ein 16 Byte langes Geheimnis erzeugt, das bei späteren Verbindungsaufbauten zwischen Konnektor und KT im Rahmen eines Challenge-Response-Verfahrens ([gemSpec\_KT#3.7.2]) verwendet wird. Dieses Geheimnis wird von der gSMC-KT des KT beim initialen Pairing signiert. Die Signatur wird vom KT zum Konnektor transportiert und dort vom Konnektor geprüft.

Erläuterung: Der Konnektor erlaubt (bei entsprechender Berechtigung) die direkte Nutzung der privaten Schlüssel MF/ DF.ESIGN/ PrK.HP.AUT.\* auf einem HBA oder MF/ DF.ESIGN/ PrK.HCI.AUT.\* auf einer SMC-B durch ein Primärsystem. Dies wird fast immer für eine klientenseitige TLS-Authentisierung gegenüber einem TLS-Server (außerhalb der TI) verwendet. Dafür werden über die Schnittstelle RSASSA-PKCS1-v1\_5-Signaturen von den entsprechenden Karten erzeugt und über den Konnektor an ein Primärsystem übergeben. Für unbenannte Anwendungen müssen auch RSASSA-PSS-Signaturen erzeugbar sein. Diese Signaturen sind nicht als Dokumentensignaturen verwendbar, der Verwendungszweck ist in den zu den privaten Schlüsseln gehörigen Zertifikaten kodiert (ExtendedKeyUsage: keyPurposeId = id-kp-clientAuth).

Hinweis: GS-A\_5208 ist nicht dem PTV4-Konnektor zugewiesen, sondern die erweiterte Anforderungen  . 

Die "vertrauenswürdige Ausführungsumgebung" (VAU) wird in [gemSpec\_Dokumentenverwaltung] eingeführt. Jedes ePA-Frontend des Versicherten (FdV) muss mit jeder beliebigen VAU (egal von welchem Anbieter ePA-Aktensystem) kommunizieren können. Deshalb ist es für die Interoperabilität notwendig, das Kommunikationsprotokoll zwischen beiden Kommunikationspartnern zu definieren und dessen Verwendung zu fordern.

Hinweis: ein ePA-Frontend des Versicherten ist nach A\_15872 (bzw. A\_15873) [gemSpec\_ePA\_FdV] verpflichtet, das Zertifikat des Kommunikationspartners (VAU) zu prüfen (Kontext: Prüfung Authentizität des empfangene ECDH-Schlüssels). Nach A\_15873 (vgl. auch A\_15784) [gemSpec\_ePA\_FdV] muss dabei die TSL der TI Prüfungsgrundlage sein [gemSpec\_ePA\_FdV].

Erläuterung: Das zu erreichende Ziel ist, dass, wenn ein Angreifer (mit hohem Angriffspotential, im Sinne von CC) selbst unter (1) der (hypothetischen) Annahme, die ePA an sich wäre überhaupt nicht verschlüsselt (es würde gar kein Aktenschlüssel existieren etc.) und (2), er alles im ePA-Aktensystem außer der VAU (inkl. HSM mit dem betreiberspezifischen Schlüssel) sicherheitstechnisch kompromittiert hätte, der Angreifer immer noch nicht auf die Klartextdaten zugreifen könnte. 

Hintergrund ist, dass es unter dem Hybrid-Modell der ePA-Architektur aus Zugriffskontrolle und Verschlüsselung bei Entzug einer Berechtigung einem nun nicht mehr berechtigten Nutzer kryptographisch theoretisch immer noch möglich ist, die Daten der Akten, auf die er vormals berechtigten Zugriff hatte, zu entschlüsseln (er bricht bspw. in das Rechenzentrum des Anbieters ePA-Aktensystem ein und stiehlt dort alle Festplatten). Durch den in einem HSM beschützten betreiberspezifischen Schlüssel ist dieser beschriebene Angriff nun unterbunden.

Erläuterung: Ziel von A\_15751 und A\_16176 ist es, den Umstellungsbedarf im Rahmen der ECC-Migration der TI und ihrer Anwendungen in der Phase 2 zu minimieren.

Hinweis: Der betreiberspezifische Schlüssel (BS) darf gemäß A\_15745 ausschließlich der VAU des ePA-Aktensystems zugänglich sein. Daher muss die Umschlüsselung in der VAU stattfinden. Dabei ist \***keine**\* Mitwirkung des Versicherten (oder eines von ihm berechtigten Nutzers) erforderlich. 

Es gibt ePA-Aktensysteme deren "Zugangsgateway des Versicherten" [gemSpec\_Zugangsgateway\_Vers] die Verwendung von TLS-Session-Resumption per Session-ID von einem ePA-FdV verlangen. Ebenfalls gibt es ePA-Aktensysteme deren Zugangsgateway des Versicherten die Verwendung von TLS-Session-Resumption per Session-Tickets von einem ePA-FdV verlangen. Nach einem TLS-Verbindungsende muss ein ePA-FdV eine TLS-Session-Resumption verwenden, ansonsten muss der Versicherte sich neu authentisieren (erneuter Login).

Ein ePA-FdV muss, um die beiden Anwendungsfälle (1) Aktensystemwechsel und (2) Versicherten-Vertreter über ein ePA-FdV eines anderen Aktensystemherstellers zu ermöglichen, beide Varianten der TLS-Session-Resumption unterstützen. Die meisten TLS-Bibliotheken unterstützen beide Varianten per Default.

Zur Schlüsselableitung bei der Schlüsselableitungsfunktionalität ePA wird die HKDF nach [RFC-5869] auf Basis von SHA-256 verwendet. Diese Funktion wird auch als Grundlage der Schlüsselableitungen bei TLS Version 1.3 verwendet.

Ein Client eines SGD (bspw. ein ePA-FdV) erhält über einen beidseitig authentisierten Ende-zu-Ende-verschlüsselten Kanal von jeweils zwei unabhängigen SGD AES-256-Bit-Schlüssel. Diese beiden Schlüssel nutzt der Client, um den Akten- und Kontextschlüssel des Versicherten im "Zwiebelschalenprinzip" zu ver- oder zu entschlüsseln.

Für die Ende-zu-Ende-verschlüsselte Datenübertragung zwischen Client und SGD-HSM wird ECIES (vgl. [SEC1-2009#5.1 Elliptic Curve Integrated Encryption Scheme], [TR-02102-1#3.3. ECIES-Verschlüsselungsverfahren] und Abschnitt  ) verwendet. Dabei besitzt der Empfänger einen elliptischen Kurvenpunkt (öffentlicher Schlüssel), dessen Authentizität der Sender prüfen kann. Dies wird erreicht, indem der Kurvenpunkt des Empfängers (entweder Client oder SGD-HSM) mittels der Langzeitidentität des Empfängers signiert ist. Der Sender erzeugt ein ephemeres ECDH-Schlüsselpaar. Mit diesem und dem Kurvenpunkt des Empfängers führt der Sender einen ECDH-Schlüsselaustausch durch. Aus dem berechneten ECDH-Geheimnis berechnet der Sender mittels einer HKDF auf Basis von SHA-256 einen AES-256-Bit-Schlüssel der im Galois/Counter-Mode (GCM) verwendet wird (Authenticated Encryption). Damit verschlüsselt der Sender den Klartext und erhält ein AES-GCM-Chiffrat. Der Sender sendet seinen erzeugten ephemeren Kurvenpunkt und das AES-GCM-Chiffrat an den Empfänger. Damit ist der Nachrichtentransport Ende-zu-Ende-verschlüsselt zwischen Sender und Empfänger, jedoch nur einseitig authentisiert. Die beidseitige Authentisierung wird über einen Authentisierungstoken, den das SGD-HSM für einen Client erzeugt, erreicht (vgl. [gemSpec\_SGD\_ePA#]). Für das ECIES-Verfahren gilt der kryptographische Sicherheitsbeweis aus [ABR-1999]. 

In  und in  wird nicht aufgeführt, welche Hashfunktion im Rahmen der Signaturstellung und -prüfung zu verwenden ist. Dies wird mit folgender Anforderung nachgeholt. 

Der Fachdienst E-Rezept besitzt zwei HTTPS-Schnittstellen, eine in der TI und eine im Internet.

Hinweis: GS-A\_4384 (TLS\_DHE\_RSA\_WITH\_AES\_128\_CBC\_SHA etc.) ist absichtlich nicht den Produkttypen der E-Rezept-Anwendung zugewiesen. Die Interoperabilität zu den Konnektoren ist mindestens über die ersten beiden Cipher-Suiten aus A\_21332 (1) sichergestellt, ebenfalls über A\_17094-\*.

Ähnlich wie bei der Anwendung ePA endet die TLS-Verbindung am E-Rezept-FD an der Webschnittstelle (Eingangspunkt). Ziel ist es die Code-Komplexität innerhalb der VAU so gering wie möglich zu halten (Trusted Computing Base), um eine ausreichende Sicherheitsanalyse des VAU-Programmcodes überhaupt erst möglich zu machen. Dafür werden die Probleme des TLS-Handlings, der Lastverteilung und des DoS-Schutzes auf Applikationsebene außerhalb der VAU an den Webschnittstellen des Fachdienstes E-Rezept bearbeitet. So kann sich der Programmcode in der VAU auf seine zentrale Aufgabe des Zugriffsschutzes der über die VAU einstellbaren und abholbaren E-Rezepte fokussieren.

Um die Verbindungsstrecke zwischen Webschnittstelle und E-Rezept-VAU in Bezug auf Vertraulichkeit zu schützen, wird eine Verschlüsselung auf Anwendungsebene eingeführt. Bei ePA ist dies das VAU-Protokoll. Beim E-Rezept kann aufgrund der andersartigen Anwendungslogik in der E-Rezept-VAU ein einfacheres Sicherungsverfahren verwendet werden. Dieses ist in Abschnitt  normativ definiert. 

Erläuterung zu A\_22698-\*:
Der Pseudonymisierungsschlüssel kann auch nur in Software vorliegen – muss also nicht zwangsweise in einem HSM vorliegen.
Für die Unterstützung von betrieblichen Prozessen soll dem E-Rezept-Projekt ein Überblick über die Anzahl der aktuell im Feld befindlichen Primärsystem-Versionen zur Verfügung gestellt werden. Der E-Rezept-FD übermittelt die Pseudonyme als Teil der Rohdatenlieferung an die gematik. 

Bei KOM-LE werden E-Mail-Anhänge , deren Größe die konnektorschnittstellenbedingte Maximalgröße (vgl. [gemSpec\_KON]) von etwas weniger als 25 MiB überschreiten, separat symmetrisch verschlüsselt und das Chiffrat auf dem "Fachdienst Download-Server (KAS)" abgelegt. Das Chiffrat erhält eine ID, die aus dem Hashwert des Chiffrats gebildet wird. Dabei ist die in  festgelegte Hashfunktion zu verwenden. Der verwendete symmetrische Schlüssel und die Hashwert-Referenz sind dann Teil des Klartextes der verschlüsselten E-Mail-Nachricht (KOM-LE). Die Chiffrate auf dem Download-Server (KAS) werden automatisch nach einer bestimmten im FD festgelegten Zeit gelöscht. 

Das u. a. durch die TR-03116-1 [BSI-TR-03116-1] angestrebte Sicherheitsniveau soll persönliche medizinische Daten effektiv schützen. Dazu lehnt sie sich an die sehr starken kryptographischen Vorgaben für die qualifizierte elektronische Signatur [SOG-IS-2020] an. Einige Formate (bspw. XMLDSig) oder Implementierungen (bspw. Standard-Java-Bibliotheken) können einige Vorgaben von Hause aus nicht erfüllen.

Dieses Kapitel weist auf Umsetzungsprobleme hin (ehemals Kapitel 3.3 aus dem Kryptographiekonzept des Basis-Rollouts).

Mit [XMLDSig] allein ist aktuell keine Nutzung von RSASSA-PSS [PKCS#1] möglich.

Aus diesem Grund hat die gematik entschieden für die Signatur nach [XMLDSig] zusätzliche Identifier für RSASSA-PSS aus [RFC-6931] innerhalb der TI zu verwenden, welche auf der Lösung aus [XMLDSig-RSA-PSS] basieren. Der RFC-6931 [RFC-6931] ist die Aktualisierung von [RFC-4051]. Die in Abschnitt „2.3.9 RSASSA-PSS With Parameters“ und „2.3.10 RSASSA-PSS Without Parameters“ aufgeführten Identifier für RSASS-PSS-Signaturen müssen innerhalb von XMLDSig für solche Signaturen verwendet werden.

Ein Beispiel aus [RFC-6931] Abschnitt „2.3.10 RSASSA-PSS Without Parameters“:

<SignatureMethod
`     `Algorithm=
`     `"http://www.w3.org/2007/05/xmldsig-more#sha256-rsa-MGF1"
`   `/>

Vgl. [gemSpec\_COS, (N003.000)]: Die Hashfunktion, auf der die Mask-generation-function basiert, ist SHA-256 [FIPS-180-4]. Die Länge des salt ist gleich der Ausgabelänge eben jener Hashfunktion (= 256 Bit).

Bei der Verschlüsselung mittels XMLEnc [XMLEnc] gibt es zwei Probleme in Bezug auf fehlende Identifier für kryptographische Verfahren, die in Abstimmung mit dem BSI für den Einsatz in der TI notwendig sind.

- Für die symmetrische Verschlüsselung mittels AES-GCM ([FIPS-197], [NIST-SP-800-38D]) gibt es keine Algorithmen-Identifier innerhalb von [XMLEnc]. Solche gibt es in [XMLEnc-1.1, Abschnitt 5.2.4].
- Für die Kodierung von RSA-OAEP-Chiffraten innerhalb von [XMLEnc] fehlt in [XMLEnc] ein Identifier für RSAES-OAEP mit der MGF1 basierend auf SHA-256 (vgl. auch Kapitel 5.10 „MGF Mask Generation Function“ in [gemSpec\_COS]). Einen solchen Identifier(„http://www.w3.org/2009/xmlenc11#mgf1sha256“) gibt es in XMLEnc Version 1.1 [XMLEnc-1.1, Abschnitt 5.5.2]. 

Aus diesem Grund hat die gematik entschieden für die XML-Verschlüsselung die Vorgaben aus [XMLEnc-1.1] zu verwenden.

Komplexität ist der natürliche Feind von Sicherheit. Die unter dem Sammelbegriff XML betitelten Formate und Protokolle sind sehr flexibel und leistungsfähig, aber auch sehr komplex. Noch dazu sind Sicherheitsmechanismen in diesem Bereich zum Teil nachträglich beigefügt worden und sind damit oft weniger leistungsfähig als im CMS-Bereich. XML-Daten effektiv zu schützen ist aktives Forschungsthema [XMLEnc-CM], [XSpRES]. Öfter als in anderen Bereichen werden neue Schwachstellen bekannt [BreakingXMLEnc], [XSW-Attack].

Aus diesem Grunde wird bei einer Sicherheitsevaluierung gesondert auf derartige Angriffe geachtet. Die gematik beobachtet neue Entwicklungen im Bereich der XML-Sicherheit und leitet falls notwendig Maßnahmen ein.

Nach dem Kerckhoffs'schen Prinzip von 1883 [Ker-1883] darf die Sicherungsleistung von kryptographischen Verfahren alleinig auf der Geheimhaltung der geheimen oder privaten Schlüssel beruhen. Geheimhaltung inkludiert insbesondere, dass sie nicht erraten werden können. Wenn bei einer Schlüsselerzeugung zu wenig Entropie vorhanden ist, kann die Geheimhaltung nicht gewährleistet werden. Die kryptographischen Verfahren, welche mit diesen Schlüsseln dann arbeiten, können die von ihnen verlangten Sicherheitsleistungen nicht mehr erbringen. Aus diesem Grunde verlangt [BSI-TR-03116-1] eine Mindestgüte der Zufallszahlerzeugung u. a. bei einer Schlüsselerzeugung. Die Basis für die Beurteilung der Güte stellt [AIS-20] und [AIS-31] dar.

Aktuell sind nicht alle Produkte in der TI bez. dieser Mindestgüte bewertet worden. Davon sind Smartcards nicht betroffen, da diese eine Sicherheitsevaluierung/-zertifizierung durchlaufen haben, bei der die Güte der Zufallszahlenerzeugung positiv beurteilt wurde. Probleme bereiten insbesondere  HSMs.

Neben einer möglichen Common-Criteria-Zertifizierung dieser Produkte, bei der analog zu den Smartcards die Güte geprüfte wird, gibt es weitere mögliche Lösungen:

1. gesonderte Prüfung der Güte nach [AIS-20] und [AIS-31] ohne komplette Common-Criteria-Zertifizierung,
1. Herstellererklärung über die Güte (wie sie bspw. aktuell bei der Kartenproduktion üblich ist).

Das „Sicherheitsniveau eines kryptographischen Verfahrens“ ist definiert als der Logarithmus zur Basis 2 der Anzahl der „Rechenschritte“ die notwendig sind um ein kryptographisches Verfahren mit hoher Wahrscheinlichkeit zu brechen. Was als „Rechenschritt“ definiert ist, ist vom Verfahren abhängig. Das Sicherheitsniveau wird in Bit angegeben. Beispielsweise nimmt man aktuell an, dass für das Brechen einer AES-Chiffre mit 128 Bit Schlüssellänge rund 2126,4 Rechenschritte, die der Durchführung einer AES-Verschlüsselung (eines 128-Bit Eingabeblocks) entsprechen, im Mittel notwendig sind. Somit erreicht eine AES-128-Bit-Verschlüsselung maximal ein Sicherheitsniveau von ca. 126,4 Bit. Eine RSA-2048-Bit-Verschlüsselung erreicht ein Sicherheitsniveau von ca. 100 Bit. 

Für den qualifizierten Vertrauensraum ist ab Ende 2025 [SOG-IS-2020] und für die TI ab Ende 2023 ein Sicherheitsniveau von mindestens 120 Bit für alle kryptographischen Verfahren vorgeschrieben [BSI-TR-03116-1]. Daher ist bis dahin eine Migration aller Komponenten und Dienste notwendig, die kryptographische Verfahren mit Schlüssellängen bez. Domainparametern verwenden die nur ein Sicherheitsniveau von unter 120 Bit erreichen können. 

Aufgrund der höheren Performanz, insbesondere in Chipkarten und Embedded-Geräten, wird nicht auf RSA-3072-Bit sondern auf ECDSA mit 256-Bit-Schlüsseln migriert.

Es gibt Produkttypen, die kryptographische Verfahren so einsetzen, dass diese keine direkten Wechselwirkungen bei anderen Produkttypen besitzen. Beispielsweise werden von einem ePA-Aktensystem Autorisierungstoken (inkl. Signatur) erzeugt und diese werden von einem ePA-FdV oder als FM ePA als opakes Objekt behandelt. Dabei kann weiterhin RSA verwendet werden, solange die dabei verwendeten Schlüsselgrößen mindestens 3000 Bit betragen (Sicherheitsniveau 120-Bit erzielen) ( ). Ggf. ist es empfehlenswert dennoch auf ECC-basierte Verfahren zu migrieren (schnellere Ausführungsgeschwindigkeit, geringere Signaturgröße). 

Die Migration erfolgt schrittweise und Komponenten und Dienste werden zusätzlich mit Schlüsselmaterial und Zertifikaten auf Basis von ECDSA auf der Kurve brainpoolP256r1 ausgestattet werden. Es gibt bis maximal Ende 2023 (vgl. Abschnitt 2.1.1.1) einen Parallelbetrieb in der TI.

Nachdem die X.509-Root der TI (Produkttyp „gematik Root-CA“), die TSPs der TI und die Objektsysteme der Chipkarten um ECC-Unterstützung für X.509-Identitäten erweitert wurden, erfolgt die schrittweise und parallele Unterstützung dieser Identitäten nun in weiteren Produkttypen bzw. Fachanwendungen.

In [gemKPT\_PKI\_TIP#3.2] wird der Begriff der Schlüsselgeneration eingeführt. Eine CA signiert Zertifikate im abstrahierten Sinne mit „ihrem Signaturschlüssel“. Dieser Schlüssel wird regelmäßig neu erzeugt und solange Verfahren und Schlüssellänge bzw. Domainparameter gleichbleiben, handelt es sich um eine neue Schlüsselversion. Kryptographisch betrachtet wurde der neue Signaturschlüssel zufällig (vgl. GS-A\_4368) erzeugt, ist also kryptographisch unabhängig vom alten Signaturschlüssel, und die CA arbeitet mit mehreren kryptographischen Schlüsseln.

Beispiel: im Fall der X.509-Root der TI (vgl. Abschnitt 5.2) wird ihr Signaturschlüssel im Regelfall alle zwei Jahre neu erzeugt (vgl. GEM.RCA1 und GEM.RCA2, <https://download.tsl.ti-dienste.de/> ). Der Signaturschlüssel liegt hier in zwei Versionen vor. Beide Schlüssel kommen aus der Schlüsselgeneration „RSA“. 

Für die Migration muss ein Signaturschlüssel in der X.509-Root der TI erzeugt werden, der aus der Schlüsselgeneration „ECDSA“ stammt. Für ihn gelten die Vorgaben aus [gemSpec\_Krypt#GS-A\_4357, Schlüsselgeneration „ECDSA“].

Die X.509-Root der TI (Produkttyp: gematik Root-CA) ermöglicht es über eine klassische PKI-Baumstruktur die meisten Zertifikate der TI zu prüfen. Für zukünftige Anwendungen, die nur mit erhöhten Kosten das leistungsstarke, aber auch deutlich komplexere TSL-Modell auswerten können, ist sie eine Infrastrukturleistung der TI, so wie auch die CVC-Root.

Die X.509-Root muss für die Migration ECDSA-basierte Zertifikate für TSPs ausstellen können. Aufgrund von [gemSpec\_PKI#GS-A\_5511] muss die X.509-Root der TI neben dem Signaturschlüssel für die Schlüsselgeneration „RSA“ auch einen Signaturschlüssel für die Schlüsselgeneration „ECDSA“ gemäß GS-A\_4357 (brainpoolP256r1) erzeugen, und diesen verwenden können.

Als Hilfestellung wird im Folgenden ein X.509-Root-TI-Zertifikat betrachtet. Gemäß GS-A\_4357 muss der öffentliche ECDSA-Schlüssel der Schlüsselgeneration „ECDSA“ auf der Kurve brainpoolP256r1 liegen. Sei

d=SHA-256(„gemSpec\_Krypt-Beispiel X.509-Root-TI ECDSA-Schluessel“)
=0x62e50dca4da29b0b10ead635a20b51fb1ec281d11f90cde8b5a9d92371ae8052

Dieses d wird als Ganzzahl (Little-Endian) interpretiert und dies sei der für das Beispiel maßgebliche private Schlüssel. Damit ergibt sich folgender öffentlicher Punkt auf der Kurve brainpoolP256r1:

(0x377434509adcbb827f74acd7adf0ce72aa28ddc53be3f15ea8023a9b0722c09d,
0x5364a99686c02092bbf9efde9878847b90f09d90b7ac4193553820258a58dfd5)

Folgend ist die ASN.1-DER-Kodierung des Schlüssels, so wie sie sich später auch im Zertifikat befindet, aufgeführt:

MFowFAYHKoZIzj0CAQYJKyQDAwIIAQEHA0IABDd0NFCa3LuCf3Ss163wznKqKN3FO+PxXqgCOpsH
IsCdU2SplobAIJK7+e/emHiEe5DwnZC3rEGTVTggJYpY39U=


`   `0  90: SEQUENCE {
`  `2  20:   SEQUENCE {
`  `4   7:     OBJECT IDENTIFIER ecPublicKey (1 2 840 10045 2 1)
` `13   9:     OBJECT IDENTIFIER brainpoolP256r1 (1 3 36 3 3 2 8 1 1 7)
`       `:     }
24  66:   BIT STRING
`       `:     04 37 74 34 50 9A DC BB 82 7F 74 AC D7 AD F0 CE
`       `:     72 AA 28 DD C5 3B E3 F1 5E A8 02 3A 9B 07 22 C0
`       `:     9D 53 64 A9 96 86 C0 20 92 BB F9 EF DE 98 78 84
`       `:     7B 90 F0 9D 90 B7 AC 41 93 55 38 20 25 8A 58 DF
`       `:     D5
`       `:   }

Das selbstsignierte Beispiel-Root-Zertifikat im PEM-Format:

-----BEGIN CERTIFICATE-----
MIICajCCAg+gAwIBAgIBATAKBggqhkjOPQQDAjBtMQswCQYDVQQGEwJERTEVMBMG
A1UECgwMZ2VtYXRpayBHbWJIMTQwMgYDVQQLDCtaZW50cmFsZSBSb290LUNBIGRl
ciBUZWxlbWF0aWtpbmZyYXN0cnVrdHVyMREwDwYDVQQDDAhHRU0uUkNBMzAeFw0x
NjEyMDkwODQxNTZaFw0yNjEyMDcwODQxNTZaMG0xCzAJBgNVBAYTAkRFMRUwEwYD
VQQKDAxnZW1hdGlrIEdtYkgxNDAyBgNVBAsMK1plbnRyYWxlIFJvb3QtQ0EgZGVy
IFRlbGVtYXRpa2luZnJhc3RydWt0dXIxETAPBgNVBAMMCEdFTS5SQ0EzMFowFAYH
KoZIzj0CAQYJKyQDAwIIAQEHA0IABDd0NFCa3LuCf3Ss163wznKqKN3FO+PxXqgC
OpsHIsCdU2SplobAIJK7+e/emHiEe5DwnZC3rEGTVTggJYpY39WjgZ4wgZswHQYD
VR0OBBYEFBERSneTkJZDKt3uLzjddI870TMmMEIGCCsGAQUFBwEBBDYwNDAyBggr
BgEFBQcwAYYmaHR0cDovL29jc3Aucm9vdC1jYS50aS1kaWVuc3RlLmRlL29jc3Aw
DwYDVR0TAQH/BAUwAwEB/zAOBgNVHQ8BAf8EBAMCAQYwFQYDVR0gBA4wDDAKBggq
ghQATASBIzAKBggqhkjOPQQDAgNJADBGAiEApQ6qGHTx97IsdzgoWH9/W32yt4rk
udUis0xxGZ48YOUCIQCTQ4puol5YYIAZYk74mfid3JBOvMBV/XgPV2WpS/99yg==
-----END CERTIFICATE-----

Relativ am Anfang des Zertifikats befindet sich die OID gemäß GS-A\_4357

16  10:   SEQUENCE {
18   8:     OBJECT IDENTIFIER ecdsaWithSHA256 (1 2 840 10045 4 3 2)
`      `:     }

Ab Offset 280 befindet sich der schon o. g. öffentlicher Schlüssel:

282  90:   SEQUENCE {
284  20:     SEQUENCE {
286   7:       OBJECT IDENTIFIER ecPublicKey (1 2 840 10045 2 1)
295   9:       OBJECT IDENTIFIER brainpoolP256r1 (1 3 36 3 3 2 8 1 1 7)
`       `:       }
306  66:     BIT STRING
`       `:       04 37 74 34 50 9A DC BB 82 7F 74 AC D7 AD F0 CE
`       `:       72 AA 28 DD C5 3B E3 F1 5E A8 02 3A 9B 07 22 C0
`       `:       9D 53 64 A9 96 86 C0 20 92 BB F9 EF DE 98 78 84
`       `:       7B 90 F0 9D 90 B7 AC 41 93 55 38 20 25 8A 58 DF
`       `:       D5
`       `:     }

Und am Ende des Zertifikats befindet sich die ECDSA-Signatur:

535  10:   SEQUENCE {
537   8:     OBJECT IDENTIFIER ecdsaWithSHA256 (1 2 840 10045 4 3 2)
`       `:     }
547  73:   BIT STRING, encapsulates {
550  70:     SEQUENCE {
552  33:       INTEGER
`       `:         00 A5 0E AA 18 74 F1 F7 B2 2C 77 38 28 58 7F 7F
`       `:         5B 7D B2 B7 8A E4 B9 D5 22 B3 4C 71 19 9E 3C 60
`       `:         E5
587  33:       INTEGER
`       `:         00 93 43 8A 6E A2 5E 58 60 80 19 62 4E F8 99 F8
`       `:         9D DC 90 4E BC C0 55 FD 78 0F 57 65 A9 4B FF 7D
`       `:         CA
`       `:       }
`       `:     }
`       `:   }

Wenn das oben aufgeführte Zertifikat sich in der Datei "root.pem" befindet, so kann man bspw. mittels

openssl verify -check\_ss\_sig root.pem

die Signatur überprüfen und erhält als Ausgabe:

root.pem: C = DE, O = gematik GmbH, OU = Zentrale Root-CA der Telematikinfrastruktur, CN = GEM.RCA3
error 18 at 0 depth lookup:self signed certificate
OK

Durch die ECC-Migration dürfen bereits produktiv betriebene Komponenten und Dienste in ihrer Verfügbarkeit nicht gefährdet werden. Aus diesem Grunde wird es eine zweite TSL "TSL(ECC-RSA)" geben. Diese wird mittels ECDSA (brainpoolP256r1) signiert sein und RSA- und ECDSA-basierte CA-Zertifikate enthalten. Bis zum Abschluss der ECC-Migration wird es zwei TSL in der TI geben: die seit Beginn des Online-Betriebs der TI bestehende RSA-basierte "TSL(RSA)" und die ECDSA-basierte "TSL(ECC-RSA). Die beiden TSL sind technisch unabhängig voneinander (Kontext Sequenznummern etc.). Dementsprechend wird es in Bezug auf die ECC-Migration keinen Vertrauensankerwechsel im Sinne von [ETSI\_TS\_102\_231\_v3.1.2] geben. Die Vertrauensbeziehung zwischen den beiden durch die zwei TSL beschriebenen Vertrauensräumen  wird über den klassischen Mechanismus der Cross-Zertifizierung realisiert. Die RSA-basierte X.509-TSL-Signer-CA wird ein X.509-Cross-Zertifikat "für" die ECDSA-basierte X.509-TSL-Signer-CA der TI ausstellen (vgl. ) und vice versa. 

Analog zur VL der BNetzA wird es die Möglichkeit geben vom Downloadpunkt des TSL-Dienstes "TSL(ECC-RSA)" einen Hashwert der aktuellen TSL zu erhalten und damit für das Prüfen der Aktualität der lokal gespeicherten TSL nicht immer die gesamte TSL vom Downloadpunkt neu laden zu müssen (vgl.  ). 

Das TLS-Protokoll unterstützt die Verwendung von RSA- und ECC-basierten Cipher-Suiten.

Als Beispiel soll sich ein Konnektor mit ECC-Unterstützung mit einem "alten" eHealth-Kartenterminal (das also nur GS-A\_4359 und nicht A\_17124 kennt) verbinden. Beim Verbindungsaufbau (TLS-ClientHello) gibt der TLS-Client (Konnektor) eine geordnete Liste von unterstützenden Cipher-Suiten an. Der TLS-Server (eHealth-KT) untersucht diese Liste von vorn nach hinten und wählt die erste auch von ihm unterstützte Cipher-Suite. Somit gilt:

1. Ein TLS-Client kann durch die von ihm gewählte Reihenfolge in der Liste der Cipher-Suiten angeben, welche Cipher-Suite der Client präferiert (bspw. ECC-basierte Cipher-Suiten).
1. Ein  TLS-Client und ein TLS-Server können unterschiedliche Fähigkeiten besitzen (ECC-Unterstützung Ja/Nein). Solange sie eine gemeinsame Schnittmenge besitzen (in unserem Fall RSA-basierte Cipher-Suiten), können sie miteinander eine TLS-Verbindung aufbauen. 

Ein TLS-Verbindungsaufbau eines Konnektors mit und ohne ECC-Unterstützung unterscheidet sich inhaltlich nur durch 4 zusätzliche Bytes (c02bc02c, vgl.  ) von einem TLS-Verbindungsaufbau ohne ECC-Unterstützung. 

Verbindet sich beispielsweise ein "alter" Konnektor im Rahmen von VSDM mit einem Intermediär mit Option "ECC-Migration", wählt der Intermediär nach GS-A\_4384 eine RSA-basierte Cipher-Suite. Der Verbindungsaufbau kommt zu Stande und der Konnektor wird quasi nie erfahren, dass der Intermediär ebenfalls ECC-basierte Cipher-Suiten unterstützt. Erst wenn der Konnektor per Firmware-Upgrade sozusagen mit der Option "ECC-Migration" ausgestattet wird, muss er u. a. Spiegelstrich 3 umsetzen. Danach wird der Intermediär nach Spiegelstrich 4 die erste ECC-basierte Cipher-Suite bei einem TLS-Verbindungsaufbau auswählen. 

Die meisten Software-Pakete oder TLS-zentrierten Hardware-Lösungen (TLS-Terminatoren etc.) unterstützen die (wie oft formuliert) "Honorierung" der Reihenfolge aus der Liste "cipher\_suites", aber nicht alle. Deshalb und weil die Honorierung wichtig aber nicht absolut notwendig ist, wurde A\_17775 als SOLL-Anforderung formuliert. 

Hinweis: Im Rahmen der Zulassungstests und der CC-Evaluierung wurde dies (A\_17322) stets so umgesetzt. Mit A\_17322 soll dieses Vorgehen explizit auch auf Spezifikationsebene ausgesprochen und transparent gemacht werden.

Das IKE-Protokoll [RFC-7296] wird verwendet um Schlüsselmaterial auszuhandeln für die folgende Verschlüsselung und Integritätssicherung der über IPsec geschützten IP-Pakete. Auszuhandeln bedeutet, dass ein (elliptische Kurven) Diffie-Hellman -Schlüsselaustausch durchgeführt wird. Im Gegensatz zum TLS-Protokoll Version 1.2 trägt schon die erste Protokollnachricht des Initiators (IKE\_SA\_INIT) einen (EC)DH-Schlüssel, evtl. aus einer kryptographischen Gruppe, die der Responder nicht unterstützt. Im Gegensatz zu TLS Version 1.3 kann dabei genau nur ein (EC)DH-Schlüssel übertragen werden, nicht eine Auswahl von Schlüsseln aus verschiedenen Gruppen. Der Initiator (Konnektor) kann im Normalfall nicht wissen, ob der Responder (VPN-Konzentrator) einen ECC-basierten DH-Schlüsselaustausch unterstützt. Der Initiator versucht es einfach und beginnt die IKE-Schlüsselaushandlung mit folgender Nachricht

Initiator                         Responder
`   `-------------------------------------------
`   `HDR, SAi1, KEi, Ni  -->

[RFC-7296]. In KEi ist der ephemere ECDH-Schlüssel auf Grundlage der Domainparameter brainpoolP256r1 enthalten. Falls der Responder diese Domainparameter (ECC-Kurve) nicht unterstützt, antwortet der Responder mit einer INVALID\_KE\_PAYLOAD-Nachricht, in der eine vom Responder unterstützte und präferierte kryptographische Gruppe angegeben ist [RFC-7296#Abschnitt 1.2]. Somit kommt es bei einem initialen Verbindungsaufbau zwischen einen "neuen" Konnektor und einem "alten" VPN-Zugangsdienst zu einem zusätzlichen "roundtrip", was akzeptiert wird, weil dies die Schlüsselaushandlung und damit den folgenden Verbindungsfall im Normalfall nur unwesentlich verzögert. Ein "neuer" Konnektor, der ggf. solch eine INVALID\_KE\_PAYLOAD-Nachricht erhält, wird dann auf die Vorgaben GS-A\_4382 "zurückfallen". 

Analog zum TLS-Protokoll wählt der Responder die Cipher-Suite und ein "alter" Konnektor kann nicht erkennen, dass es sich evtl. um einen "neuen" VPN-Zugangsdienst handelt.

Hinweis:

"strongSwan" unterstützt diese Algorithmen, vgl. <https://wiki.strongswan.org/projects/strongswan/wiki/IKEv2CipherSuites>  

Die Anforderung   gilt für allgemeine XML-Datensignaturen, also auch für Tokensignaturen etc.   fordert für die Interoperablität bei der Prüfbarkeit von Dokumentensignaturen die Verwendung des interoperablen Containerformats nach [ETSI-XAdES]. 

Die Anforderung A\_17207 gilt für allgemeine (nicht-XML-)Datensignaturen, also auch für Tokensignaturen etc. A\_17359 fordert für die Interoperabilität bei der Prüfbarkeit von Dokumentensignaturen die Verwendung des interoperablen Containerformats nach [ETSI-CAdES].

Hinweis: Signaturen in PDF/A-Dokumenten werden mittels CMS kodiert.

In der TI wird für die ECC-basierte Ver- und Entschlüsselung das "Elliptic Curve Integrated Encryption Scheme (ECIES)" verwendet. Es ist das einzige ECC-basierte, von den Chipkarten der TI unterstützte, Verschlüsselungsverfahren. Das ECIES ist ein hybrides Verfahren basierend auf [ABR-1999]. Es besteht aus einem asymmetrischen Teil (elliptic curve diffie hellman) und einen symmetrischen Teil (Verschlüsselungsverfahren und MAC-Verfahren). Weiterhin ist eine Schlüsselableitungsfunktion für das Verfahren notwendig. In [gemSpec\_COS#6.8.2.3 Asymmetrische Entschlüsselung mittels ELC] wird definiert, welche Varianten dieser drei notwendigen Verfahren eine Chipkarte der TI unterstützt (ECDH [BSI-TR-03111#4.3.1 Key Agreement Algorithm], HKDF mittels SHA-256 und einem Zähler nach X9.63 [BSI-TR-03110-3#A.2.3.2], AES-256-CBC und CMAC). Da im Normalfall immer für eine Identität, die Chipkarten-basiert ist, verschlüsselt wird, muss ein Sender genau diese Verfahren einsetzen. Ansonsten kann die Chipkarte das Chiffrat nicht entschlüsseln, auch wenn die Chipkarte den prinzipiell richtigen privaten Schlüssel in sich trägt.

Da man das gesamte Chiffrat für eine Entschlüsselung auf einmal an die Karte (innerhalb einer APDU) senden muss, kann man nur etwas weniger als 8KiB entschlüsseln (bzw. 64KiB bei extended APDUs, die jedoch nicht alle Kartenterminal unterstützen), obwohl das ECIES-Verfahren an für sich die Ver- und Entschlüsselung praktisch beliebig großer Datenmengen unterstützt. Auch wäre es aus Nutzersicht in Bezug auf die Performanz nicht akzeptabel, schon allein moderat große verschlüsselte Dokumente komplett zu einer Karte für eine Entschlüsselung zu transportieren (mehr als 18 Minuten würde dies für ein 10 MiB großes Dokument benötigen). Deswegen wird für die TI hier eine zusätzliche Metaebene eingeführt und normativ gefordert. Analog zu einer Verschlüsselung mittels RSAES-OAEP muss ein Sender einen Transportschlüssel zufällig erzeugen. Ein solcher Transportschlüssel, ist dann aus Sicht der Chipkarte der zu ver- oder entschlüsselnde Klartext. Der aus Nutzersicht eigentliche Klartext (Dokumente) wird nie an die Karte gesendet. Die Karte entschlüsselt den verschlüsselten Transportschlüssel und übergibt ihn anschließend an den Kartennutzer. Dieser kann mit dem Transportschlüssel nun das Dokument unabhängig von der Chipkarte entschlüsseln. Bei RSAES-OAEP wird der Transportschlüssel als Content-Encryption-Key (CEK) bezeichnet. Im hier vorliegenden Fall bei ECIES kann diese Bezeichnung zu Missverständnissen führen. Mittels ECIES wird über ein ECDH und folgender Schlüsselableitung ein Verschlüsselungsschlüssel erzeugt. Diesen kann man auch als CEK bezeichnen, weswegen im Folgenden immer nur vom Transportschlüssel gesprochen wird.

Da eine solche Metaebene für eine ECIES-Chiffrat-Kodierung unüblich ist (weil ohne TI-Chipkarteneinsatz unnötig), ist die Kodierung der Chiffrate mittels CMS oder XMLEnc nichttrivial und wird daher im Interesse der zu erzielenden Interoperabilität in diesem Abschnitt ausführlicher dargestellt.

Für die symmetrische Verschlüsselung der Nutzerdaten (Dokumente etc.) wird zufällig ein Transportschlüssel erzeugt. Für diesen gelten die Vorgaben aus GS-A\_4389 (symmetrische Verschlüsselung) und GS-A\_4368 (Schlüsselerzeugung). Der Transportschlüssel wird dann unkodiert ("is just the \"value\" of the content-encryption key" [RFC-5652#6.4]) zur Verschlüsselung an das ECIES-Verfahren übergeben. Bei der ECIES-Verschlüsselung müssen dann die Parameter so gewählt werden, dass eine Chipkarte der TI diese unterstützt, d. h. nach [gemSpec\_COS#6.8.2.3 Asymmetrische Entschlüsselung mittels ELC].

Das erhaltene ECIES-Chiffrat muss dann als eine ASN.1-Struktur kodiert werden, die genau dem Aufbau entspricht, den man benötigt um eine Entschlüsselung mittels einer Chipkarte der TI durchzuführen (vgl. [gemSpec\_COS#(N085.068) Spiegelstrich 7).

![](Aspose.Words.2d194658-3910-4b4a-bf6b-abf9f3411a63.002.png)

Abbildung #: ASN.1-Kodierung des Chiffrats was den Transportschlüssel enthält 

Beispiel:

poGOBgkrJAMDAggBAQd/SUOGQQRouC6tM2TQQ+RP3pptgdAaDF8Te7IVCkUBe2H+PJSLK4W/BXIX
kndiBwEfftd5wk4pjzCdC2j1q14/CIWcW89nhjEC7G47UAu2ZqmbIhxstkXV3UI2UUek/qwBwtb2
6aUild+5kkTZXf5674OKHSdj6IFwjggvhYt9b/CTsA==

$ dumpasn1 a.bin
`  `0 142: [6] {
`  `3   9:   OBJECT IDENTIFIER brainpoolP256r1 (1 3 36 3 3 2 8 1 1 7)
` `14  67:   [APPLICATION 73] {
` `17  65:     [6]
`       `:       04 68 B8 2E AD 33 64 D0 43 E4 4F DE 9A 6D 81 D0
`       `:       1A 0C 5F 13 7B B2 15 0A 45 01 7B 61 FE 3C 94 8B
`       `:       2B 85 BF 05 72 17 92 77 62 07 01 1F 7E D7 79 C2
`       `:       4E 29 8F 30 9D 0B 68 F5 AB 5E 3F 08 85 9C 5B CF
`       `:       67
`       `:     }
` `84  49:   [6]
`       `:     02 EC 6E 3B 50 0B B6 66 A9 9B 22 1C 6C B6 45 D5
`       `:     DD 42 36 51 47 A4 FE AC 01 C2 D6 F6 E9 A5 22 95
`       `:     DF B9 92 44 D9 5D FE 7A EF 83 8A 1D 27 63 E8 81
`       `:     70
135   8:   [14] 2F 85 8B 7D 6F F0 93 B0
`       `:   }
Diese Datenstruktur soll konzeptionell so behandelt werden, wie ein RSA-OAEP-Chiffrat eines CEK. Es ist jedoch die hiermit neu definierte OID oid\_ti\_ecies\_transport\_encryption [gemSpec\_OID] zu verwenden. 

Ein Beispiel aus [gemSpec\_SMIME-KOMLE] dient als Vorlage für die Darstellung der zu verwendenden Kodierung mittels CMS (S/MIME):

ContentInfo
.contentType: 1.2.840.113549.1.9.16.1.23 (id-ct-authEnvelopedData)
..AuthEnvelopedData
...version: 0
...recipientInfos
....RecipientInfo
.....ktri
......version: 0
......rid
.......issuerAndSerialNumber
........issuer
........[... weitere Kindelemente ...]
........SerialNumber: 123456789
.......keyEncryptionAlgorithm
........oid\_ti\_ecies\_transport\_encryption
.......encryptedKey: [ ... ASN.1-Struktur (Tupel (PO, C, T) in kartenkompatibler ASN.1-Binärverpackung) ... ]
....RecipientInfo
.....ktriversion: 0
......rid
.......issuerAndSerialNumber
........issuer
........[... weitere Kindelemente ...]
........SerialNumber: 314159265
.......keyEncryptionAlgorithm
........OID TI-ECIES-TransportEncryption
.......encryptedKey: [ ... ASN.1-Struktur (Tupel (PO, C, T) in kartenkompatibler ASN.1-Binärverpackung) ... ]
...authEncryptedContentInfo
....contentType: 1.2.840.113549.1.7.1 (id-data)
....contentEncryptionAlgorithm:
.....algorithm: 2.16.840.1.101.3.4.1.46 (id-aes256-gcm)
......parameters:
.......aes-nonce: [... IV ...]
.......aes-ICVlen: [... ICVLen ... ]
....encryptedContent: [...]
...mac: [...]
...unauthAttrs
....Attribute (id-recipientEmails)
.....attrType: komle-recipient-emails

und so weiter ...

Für die Kodierung von TI-ECIES-Chiffraten innerhalb von XML wird hiermit der neue Identifier "http://gematik.de/ecies/2019" definiert. Für die XML-Kodierung ist eine Kodierung analog der folgenden Struktur zu verwenden.

<?xml version="1.0" encoding="UTF-8"?>
<xenc:EncryptedData
`    `xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
`    `xmlns:xenc="http://www.w3.org/2001/04/xmlenc#"
`    `xmlns:ds="http://www.w3.org/2000/09/xmldsig#"
`    `xmlns:dsig11="http://www.w3.org/2009/xmldsig11#"
`    `xmlns:xenc11="http://www.w3.org/2009/xmlenc11#"
`    `Type="http://www.w3.org/2001/04/xmlenc#">
`  `<xenc:EncryptionMethod Algorithm="http://www.w3.org/2009/xmlenc11#aes256-gcm" />

<!-- Damit ist len(IV)=12 Byte und TagLen=16 Byte, vgl. [XMLEnc#5.2.4 AES-GCM] --> 
`  `<ds:KeyInfo>
`    `<xenc:EncryptedKey>
`    `<!-- Hybridschlüssel für einen Empfänger, für weitere Empfänger gäbe es jeweils ein weiteres EncryptedKey-Element -->
`      `<xenc:EncryptionMethod Algorithm="http://gematik.de/ecies/2019" />
`      `<!-- Die Version des speziellen ECIES -->
`      `<ds:KeyInfo> 
`        `<ds:X509Data>
`         `<ds:X509Certificate>
`       `<!-- Base64-kodiertes X.509-Zertifikat (DER) des Empfängers -->
`         `</ds:X509Certificate> 
`        `</ds:X509Data>
`      `</ds:KeyInfo>
`      `<xenc:CipherData>
`        `<xenc:CipherValue>
<!-- Base64-kodierte ASN.1-Struktur (Tupel (PO, C, T) in kartenkompatibler ASN.1-Binärverpackung) -->
`        `</xenc:CipherValue>
`      `</xenc:CipherData>
`    `</xenc:EncryptedKey>
`  `</ds:KeyInfo>   
`  `<xenc:CipherData>
`    `<xenc:CipherValue>
<!--
Base64-kodiertes symmetrisch mittels AES-256-GCM verschlüsseltes Dokument 
(IV || ciphertext || Tag) mit len(IV)=12 Byte und len(Tag)=16 Byte,
vgl. [XMLEnc#5.2.4 AES-GCM]
-->
`    `</xenc:CipherValue>
`  `</xenc:CipherData> 
</xenc:EncryptedData>

Im Interesse der Interoperabilität stellt die gematik auf Anfrage Testvektoren (Beispiel-Chiffrate mit Klartext) zur Verfügung.

In [SEC1-2009#5.2] und in [RFC-5753#4] wird auf ein potentielles Problem hingewiesen, dass insbesondere bei der Verwendung eines static-static-ECDH innerhalb von ECIES auftreten kann (also Sender und Empfänger verwenden ihre Langzeit-Identität "static-static"). Verallgemeinert formuliert, handelt es sich um das Problem der authentisierten Broadcast-Verschlüsselung. Ein Sender möchte an mehrere Empfänger "gleichzeitig" den gleichen Klartext verschlüsselt senden (vgl. auch [RFC-4082#1]). Bei TI-ECIES-TransportEncryption [gemSpec\_Krypt#ECIES] wird der Transportschlüssel jeweils für jeden Empfänger mittels ECIES verschlüsselt. Jeder Empfänger kennt nun diesen zwischen dem Sender und allen Empfängern geteilten Schlüssel (Transportschlüssel) und kann jetzt (aus kryptographischer Sicht) den Klartext beliebig verändern, ohne dass dies bei einer Entschlüsselung auffällt. Die "authenticated Encryption" via AES-GCM (Transportschlüssel) kann hier also nicht die von ihr evtl. angenommene Sicherheitsleistung erbringen. 

Wenn also bspw. bei KOM-LE eine Nachricht an mehrere Empfänger (eingetragen im CC-Feld) versendet werden soll, so muss an dieser Stelle zusätzlich die Authentizität der versendeten Nachricht gesichert werden. Bei KOM-LE erfolgt dies über die verpflichtende Signatur der Nachricht mit Hilfe der SMC-B (OSIG-Schlüsselmaterial). Es ist davon auszugehen, dass andere Anwendungen, die an mehrere Empfänger Nachrichten/Daten "gleichzeitig" versenden, ebenfalls zusätzliche Maßnahmen ergreifen müssen.

Ein "Mobiles Kartenterminal" [gemSpec\_MobKT] ist so etwas wie ein Tablet mit zwei Chipkartenslots. Es ermöglicht einem LE außerhalb seiner Praxisräumlichkeiten (also insbesondere ohne Konnektor und stationäres eHealth-Karterterminal), auf Daten eines Versicherten auf dessen eGK zuzugreifen. Das Mobile Kartenterminal muss die dabei ausgelesenen versichertenspezifischen Daten verschlüsselt lokal im Gerät ablegen. Wenn das Mobile Kartenterminal verloren geht, sind damit diese Daten geschützt. Sie können erst mit Hilfe des gesteckten und freigeschaltenen HBA des LE wieder entschlüsselt (genutzt) werden, bspw. zur Übertragung ins Primärsystem. Für die Verschlüsselung muss nach Ende 2023 ECIES und nicht mehr RSA-OAEP verwendet werden. Es gelten dafür fachlich quasi die gleichen Vorgaben wie in A\_17220, nur gibt es keine Notwendigkeit in Bezug auf die Kodierung des Chiffrats interoperabel  sein zu müssen. Denn nur das spezifische Mobile Kartenterminal selbst muss die Daten ver- und entschlüsseln können im Sinne von "die Kodierung der Chiffrate auswerten können". Deshalb gibt es nachfolgend eine Spezialisierung von A\_17220 für das Mobile Kartenterminal.

Hinweis zu A\_17575:
In einem HBA steht die Schnittstelle [gemSpec\_COS#6.8.1.4 ELC Verschlüsselung] für die Verschlüsselung des Transportschlüssels zur Verfügung. Dass der Transportschlüssel verschlüsselt werden muss, wird nur sehr selten als Anwendungsfall vorkommen. Die Entschlüsselung - notwendiger Weise mit und durch den HBA - jedoch häufig. 

Mit A\_17089 und A\_17090 (vgl. Abschnitt 3.3.2) wird vom eHealth-Kartenterminal die Unterstützung der mit der Kartengeneration 2.1 (vgl. [gemSpec\_gSMC-KT\_ObjSys\_G2.1]) hinzugekommenen ECDSA-basierten Identität bereitgestellt.

Hinweis: Das in A\_17090 geforderte Verhalten lässt sich bei OpenSSL leicht mit SSL\_get\_current\_cipher() umsetzen.

Ein eHealth-Kartenterminal muss beim TLS-Verbindungsaufbau, der vom Konnektor initiiert wird, dessen TLS-Client-Zertifikat prüfen. Dafür muss ein eHealth-Kartenterminal alle "CA-Zertifikate der relevanten TSP speichern" [gemSpec\_KT#TIP1-A\_3255]. Um diesen kritischen Punkt, jedoch noch einmal zu unterstreichen:

Konnektoren speichern die Pairinginformationen zu den mit ihnen gepairten Kartenterminals als Tupel {Kartenterminal-Zertifikat; Shared Secret}, wobei das beim Pairing vom Kartenterminal genutzte Zertifikat gespeichert wird. Wird später (bspw. durch ein Software-Update des Kartenterminals, welches die Nutzung von ECDSA Identitäten ermöglicht) ein anderes Zertifikat vom Kartenterminal beim TLS-Handshake präsentiert (also bspw. eine ECDSA Identität statt der zuvor genutzten RSA-Identität), passt dies für den Konnektor nicht zur vorhandenen Pairinginformation. Der Verbindungsaufbau scheitert somit, bis ein neues Pairing vorgenommen wird (bei dem dann das ECDSA-Zertifikat vom Kartenterminal verwendet wird). Dieses Verhalten muss vermieden werden, da dies einen massenhaften Ausfall von Kartenterminals durch ein Software-Update der Terminals hervorrufen kann. Daher darf der Konnektor nur solche Cipher-Suiten anbieten, die auch zum für das betroffene Kartenterminal gespeicherte Zertifikat passen.

Zur Sicherstellung der Interoperabilität zwischen Health-KT und Konnektor werden folgende Festlegungen getroffen. Bei den folgend aufgeführten Themen hatte es bezüglich der Interoperabilität Probleme gegeben.

Hinweise zum Thema Renegotiation:

Hinweis 1: Gemäß GS-A\_5525 unterstützt der Konnektor "renegotiation". Daraus folgt, dass er diese Fähigkeit in der ClientHello- Nachricht entweder durch eine "renegotiation\_info" extension anzeigt, oder durch ein TLS\_EMPTY\_RENEGOTIATION\_INFO\_SCSV (siehe [RFC-5746#3.4, §1, erster Punkt]).

Hinweis 2: Gemäß [RFC-5246#7.4.1.3 letzter §] ist es einem Server nur dann erlaubt in der ServerHello-Nachricht eine "renegotiation\_info" extension zu schicken, wenn die ClientHello-Nachricht Informationen zu "renegotiation" enthält. Gemäß dem vorstehenden Hinweis ist das beim TLS-Handshake zwischen Konnektor und eHealth-KT stets der Fall.

Hinweis 3: Die gematik legt nicht fest, wie sich ein eHealth-KT zu verhalten hat, wenn die ClientHello-Nachricht weder eine "renegotiation\_info" extension, noch ein TLS\_EMPTY\_RENEGOTIATION\_INFO\_SCSV enthält.

Hinweis 4: Es gilt für das eHealth-KT GS-A\_5524-\*, womit sichergestellt ist, dass ein eHealth-KT keine unsichere TLS-Renegotiation durchführt.

Die Verpflichtung der Implementierung bestimmter (s. u.) für die ECC-Migration notwendiger Funktionalitäten wird für den PTV5-Konnektor mit Hinblick auf die fristgerechte Umsetzung der ePA zunächst ausgesetzt: 

- Für die TLS-Schnittstellen, die bereits mit dem PTV3-Konnektor zertifiziert wurden (Schnittstellen zu Kartenterminals, Clientsystemen, Intermediär, zentralen Diensten), wird in PTV4 auf eine verpflichtende ECC-Unterstützung zunächst verzichtet.
- Ebenso wird auf die verpflichtende Umsetzung der ECC-Unterstützung an der IPsec/IKE-Schnittstelle zum VPN-Konzentrator zunächst verzichtet. 

Unverändert verpflichtend gefordert wird die ECC-Unterstützung an der Schnittstelle zum ePA-Aktensystem, bei den Karten und für KOM-LE. Insbesondere bedeutet dies, dass ein PTV5-Konnektor auch weiterhin 

- die TSL(ECC-RSA) prüfen und verwenden muss (vgl.  ), 
- die Signaturerstellung und -prüfungen auf ECDSA-Basis beherrschen muss (vgl. , , , ,   und die VAU-Protokoll und die SGD-Protokoll relevanten Operationen) und
- die Ver- und Entschlüsselung über das ECIES-Verfahren (vgl.  ,  A\_17221-\* und die Transport-Verschlüsselung innerhalb des SGD-Protokolls mit  )

unterstützen muss.

Dem VPN-Zugangsdienst sind die IPsec-Anforderungen  und   zugewiesen, ebenso A\_17205. Im Rahmen der Registrierung bei einem VPN-Zugangsdienst wird vom Konnektor eine Signatur mittels einer SMC-B erzeugt. Diese muss der VPN-Zugangsdienst (Registierungsserver) prüfen können, dafür gilt für diesen A\_17206. 

Für die Produkttypen, die bei der Anwendung VSDM verwendet werden, ist die ECC-RSA-TSL-Auswertung   und die ECC-Unterstützung bei TLS  relevant. 

Fachanwendungsspezifische Anpassungen aufgrund der ECC-Migration befinden sich in den jeweiligen Spezifikationen (bspw. ). 

Die Architekturentscheidung, dass auf der Verbindungsstrecke zwischen einem ePA-Frontend eines Versicherten (Client) bzw. eines FM ePA (Client) und einer VAU (Server) immer HTTP über ein Gateway als Kommunikationsprotokoll verwendet wird, hat Vorteile. Ein Nachteil ist, dass damit keine direkte TLS-Verbindung zwischen Client und Server möglich ist. Der TLS-Kanal terminiert am Gateway. Um die "letzten Meile" zwischen Gateway und VAU innerhalb des ePA-Aktensystems nicht ungeschützt zu lassen, wird das "VAU-Protokoll" eingeführt und verwendet. Es wird nicht der Weg gewählt HTTP über TLS über HTTP über TLS zu tunneln. Stattdessen wird das folgende Protokoll eingeführt als eine leichtgewichtige Sicherungsschicht zwischen einer VAU (Server) und einem ePA-Frontend eines Versicherten (Client) bzw. eines FM ePA (Client). Der Server und der Client besitzen jeweils eine kryptographische Langzeitidentität. Diese sind Grundlage für einen beidseitig authentisierten ephemeren ECDH. Aus dem gemeinsamen ECDH-Geheimnis werden mittels einer HKDF zwei AES-Schlüssel abgeleitet (vgl. A\_16943-\*). Per AES-GCM werden nach dem Schlüsselaustausch alle ausgetauschten Nutzerdaten kryptographisch gesichert. Es gibt einen Nachrichtenzähler der vor Replay-Attacken schützt. 

Die gematik stellt eine Beispielimplementierung bereit (<https://fachportal.gematik.de/service/entwicklung/> ). 

Es gibt bei der Kommunikation, die das Protokoll steuert, zwei aktive und einen passiven Teilnehmer. Der Client initiiert die Kommunikation per HTTP-POST-Request. Der Server antwortet als HTTP-Server auf diesen Request mit einer HTTP-Response. Das Gateway leitet die Daten weiter und erscheint unsichtbar. Das Gateway erzwingt die Verwendung des HTTP-Protokolls.

Das Kommunikationsprotokoll hat als Hauptaufgabe die zwischen Client und Server (VAU) auszutauschenden Nutzerdaten vor dem Gateway in Bezug auf Vertraulichkeit, Authentizität, Integrität (inkl. Verhinderung von Replay-Attacken) zu schützen. Das Protokoll bietet (absichtlich) keinen Schutz der HTTP-Header-Informationen. Es ist bei der ePA-Architektur sichergestellt, dass eine Änderung der HTTP-Header-Informationen keine negativen Auswirkungen auf die Vertraulichkeit, Integrität und Authentizität der Nutzerdaten hat. Hinweis zum besseren Verständnis: Zwischen Gateway und Client besteht immer eine TLS-Verbindung, so dass nur das Gateway bzw. nur ein Angreifer im Aktensystem selbst die Header-Informationen ändern könnte.

Ein Designziel ist es, den Verbindungsaufbau möglichst "menschenlesbar" zu gestalten und so die Implementierung und die Fehlersuche (u. a. auch im Betrieb) zu erleichtern. So sind die meisten Nachrichten einfache, menschenlesbare JSON-Objekte. Die im Protokoll definierten Fehlermeldungen (VAUServerError-Nachricht) haben den Hauptzweck, die manuelle Fehleranalyse zu erleichtern. Das VAU-Protokoll ist relativ einfach, so dass ein Client oder ein Server bei Auftreten eines Fehlers selten etwas anderes tun kann, als die Protokollabarbeitung abzubrechen (und als Client einen neuen Protokolldurchlauf zu initiieren). Dies bedeutet: die Art der aufgetretenen Fehlernachricht ist für den Client i. d. R. irrelevant, weil die Handlungsoptionen sehr begrenzt sind. Erst bei der manuellen Fehleranalyse werden die differenzierten Fehlermeldungen hilfreich.

Viele Nachrichten und Datenfelder ähneln fachlich Bestandteilen aus dem TLS-Protokoll und werden absichtlich anders benannt, um Verwechselungen zu vermeiden.

Das Protokoll bietet die Möglichkeit, zukünftig verschiedene CipherConfiguration (im TLS-Protokoll entspricht dies den TLS-Cipher-Suiten) zu unterstützen; aktuell gibt es genau eine ("AES-256-GCM-BrainpoolP256r1-SHA-256").

Der Ablauf der Schlüsselaushandlung des VAU-Protokolls ist im folgenden Ablaufdiagramm dargestellt.

![](Aspose.Words.2d194658-3910-4b4a-bf6b-abf9f3411a63.003.png)

Abbildung #: Übersicht über das VAU-Protokoll 

Da die Werte des ephemeren öffentlichen ECDH-Schlüssels des jeweiligen anderen Kommunikationspartners in die eigene Signatur eingehen, können sowohl Client und Server bei der Signaturprüfung sicherstellen, dass die Schlüsselaushandlung frisch ist (vgl. [Boyd-Mathuria-2003#Abschnitt "1.5 Freshness"]). 

Aus dem gemeinsamen ECDH-Geheimnis wird ein AES-Schlüssel abgeleitet und damit die weitere Kommunikation mittels AES-GCM in Bezug auf Vertraulichkeit und Integrität geschützt. Der dabei explizit mitgelieferte Nachrichtenzähler schützt vor Replay-Attacken.

Die in den Anforderungen angegebenen Reihenfolgen von Attribute-Value-Pairs innerhalb der JSON Objekte sind als Beispiele zu verstehen und nicht in ihrer Reihenfolge normativ. Es gilt der JSON Standard [ecma-262].

Hinweis: Obwohl innerhalb einer der VAUServerHelloData der Wert VAUClientHelloDataHash enthalten ist und damit auch in die Berechnung von VAUServerHelloDataHash mit einfließt, wird der Wert VAUClientHelloDataHash explizit in VAUClientSigFin aufgeführt. Ziel ist es möglichst direkt Transparenz über die bestätigten Daten zu schaffen.

Nachdem die Etablierung des VAU-Kanals abgeschlossen ist, kommuniziert ein VAU-Client (bspw. ein ePA-FdV) mit der VAU bspw. um einen großen verschlüsselten Arztbrief der Akte hinzuzufügen. Dabei ist es für die Performanz (also auch für die Nutzerakzeptanz) günstig, größere Daten mittels der „SOAP Message Transmission Optimization Mechanism (MTOM)“/ „XML-binary Optimized Packaging (XOP)“-Kodierung zu transportieren. MTOM/XOP ist die nach W3C empfohlene Methode, um über HTTP/SOAP größere binäre Daten zu transportieren. Dabei werden die Binärdaten nicht Base64- innerhalb einer XML-Datenstruktur kodiert, sondern beim HTTP/SOAP-Request (bzw. bei der -Response) über eine MIME-Multipart-Kodierung innerhalb von HTTP. Dabei werden innerhalb der SOAP-Nachricht die Binärdaten über eine ID (<xop:Include href=“cid:Beispiel-ID1“/>) referenziert und innerhalb des HTTP-Request bzw. der HTTP-Response über die „Content-ID“ (vgl. das folgende Beispiel) und eine MIME-Kodierung binär kodiert. Dies führt zur Reduktion Datengröße der zu übertragenden Daten von rund 27,5%.

Beispiel:

Ohne MTOM/XOP:

POST /URL1 HTTP/1.1
Content-Type: application/soap+xml; charset=UTF-8
Content-Transfer-Encoding: binary
Content-Length: …

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
`  `<SOAP-ENV:Header />
`  `<SOAP-ENV:Body>
`    `<ns1:uploadFileRequest xmlns:ns1="urn:example:Upload">
`      `<ns1:name>Test-Bild.png</ns1:name>
`      `<ns1:content> … Hier kommen in Base64 kodierte Daten … </ns1:content>
`    `</ns1:uploadFileRequest>
`  `</SOAP-ENV:Body>
</SOAP-ENV:Envelope>



Mit MTOM/XOP:

POST /URL1 HTTP/1.1
Content-Type: Multipart/Related; boundary="----=\_Part\_1\_1234----"; type="application/xop+xml"; start="Eintrag-1"; start-info=“application/soap+xml“; charset=UTF-8
Content-Transfer-Encoding: binary
Content-Length: …

----=\_Part\_1\_1234----
Content-Type: application/xop+xml; type=“application/soap+xml“; charset=“UTF-8“
Content-Transfer-Encoding: 8bit
Content-ID: Eintrag-1

<s11:Envelope xmlns:s11='http://schemas.xmlsoap.org/soap/envelope/' xmlns:xmime='http://www.w3.org/2005/05/xmlmime'>
` `<s11:Body>
`  `<m:data xmlns:m='http://example.org/stuff'>
`  `<m:photo xmime:contentType='image/jpeg'>
`   `<xop:Include xmlns:xop='http://www.w3.org/2004/08/xop/include'
`        `href='cid:Bild-1'/>
</m:photo>
</m:data>
` `</s11:Body>
</s11:Envelope>

----=\_Part\_1\_1234----
Content-Type: image/jpeg
Content-Transfer-Encoding: binary
Content-ID: Bild-1

… hier kommen die binären Daten …
----=\_Part\_1\_1234----


Für die Dekodierung einer solchen MIME-Multipart-Kodierung ist es sehr hilfreich (und ggf. notwendig) als Empfänger den vom Sender intendierten (vollständigen) „Content-Type“ aus dem HTTP-Request-Header bzw. dem HTTP-Response-Header zu kennen. Dieser wird jedoch durch das VAU-Protokoll überschrieben (vgl. A\_16945-\* und A\_16952-\*). Um die u. a. nach [gemSpec\_FM\_ePA#A\_16220] und [gemSpec\_ePA\_FdV#A\_16222] geforderte Verwendung von MTOM/XOP zu unterstützen, wird der originär intendierte Content-Type, der im „start“-Feld ggf. vertrauliche Daten enthalten kann, innerhalb der „zusätzlichen HTTP-Header-Informationen“ (vgl. A\_16945-\* und A\_16952-\*) mitgeliefert.

Für die Fehlersuche -- insbesondere bei IOP-Problemen zwischen Produkten verschiedener Hersteller in einer fortgeschrittenen Entwicklungsphase -- hat es sich als notwendig erwiesen, dass ein Fehlersuchender den Klartext der Kommunikation zwischen ePA-Client und VAU-Instanz mitlesen kann. Vgl. [gemSpec\_Aktensystem#5.8. Tracing in Nichtproduktivumgebungen].

Hinweis-1: SHA-256("gemSpec\_Krypt: privater VAUClient-ECDH-Schluessel fuer Nichtproduktivumgebungen nach A\_21888-\*") ist als hexdump kodiert gleich 078ece94904fc6bf9900cced4c5af4dcd4fbebc585b2054b636cc3f76333bdee

Hinweis-2:

Folgend ist der private Schlüssel aus A\_21888-\* als PKCS8-Container PEM-kodiert aufgeführt:

-----BEGIN PRIVATE KEY-----
MIGIAgEAMBQGByqGSM49AgEGCSskAwMCCAEBBwRtMGsCAQEEIAeOzpSQT8a/mQDM
7Uxa9NzU++vFhbIFS2Nsw/djM73uoUQDQgAEIfr+3Iuh71R3mVooqXlPhjVd8wXx
9Yr8iPh+kcZkNTongD49z2cL0wXzuSP5Fb/hGTidhpw1ZYKMib1CIjH59A==
-----END PRIVATE KEY-----

In diesem Abschnitt wird eine optionale Protokollerweiterung des VAU-Protokolls für ePA dargestellt, die sich aktuell in der gematik in der Evaluierung befindet. Kryptographisch gesehen entspricht sie dem PQC-Vorgehen bei TLS aus [TLS-CC-2021]. Mehr Information über PQC findet man in Abschnitt "". 

Ein Client initiiert mit einer VAUClientHello-Nachricht den VAU-Protokoll-Handshake (Schlüsselvereinbarung). Möchte er zusätzlich zum klassischen ephemeren ECDH-Schlüsselaustausch ein PQC-Verfahren anwenden und die beiden gemeinsam mit dem VAU-Server dabei erzeugten Geheimnisse in die Schlüsselableitung für die symmetrischen Sitzungsschlüssel einfließen lassen, so führt er im Handshake einen Verfahrensidentifikator inkl. dazugehörigen öffentlichen Schlüssel eines der unten aufgeführten PQC-Verfahren mit an.

In [liboqs] sind die Referenzimplementierungen der Round-3-Kandidaten der NIST-PQC-Standardisierung [NIST-PQC] enthalten. Ebenfalls sind dort folgende Identifier definiert, die den Definitionen aus den Round-3-Kandidaten entsprechen:

Key encapsulation mechanisms (KEM):

- BIKE: BIKE-L1, BIKE-L3
- Classic McEliece: Classic-McEliece-348864, Classic-McEliece-348864f, Classic-McEliece-460896, Classic-McEliece-460896f, Classic-McEliece-6688128, Classic-McEliece-6688128f, Classic-McEliece-6960119, Classic-McEliece-6960119f, Classic-McEliece-8192128, Classic-McEliece-8192128f
- FrodoKEM: FrodoKEM-640-AES, FrodoKEM-640-SHAKE, FrodoKEM-976-AES, FrodoKEM-976-SHAKE, FrodoKEM-1344-AES, FrodoKEM-1344-SHAKE
- HQC: HQC-128, HQC-192, HQC-256
- Kyber: Kyber512, Kyber512-90s, Kyber768, Kyber768-90s, Kyber1024, Kyber1024-90s
- NTRU: NTRU-HPS-2048-509, NTRU-HPS-2048-677, NTRU-HPS-4096-821, NTRU-HPS-4096-1229, NTRU-HRSS-701, NTRU-HRSS-1373
- NTRU-Prime: ntrulpr653, ntrulpr761, ntrulpr857, ntrulpr1277, sntrup653, sntrup761, sntrup857, sntrup1277
- SABER: LightSaber-KEM, Saber-KEM, FireSaber-KEM
- SIKE: SIDH-p434, SIDH-p434-compressed, SIDH-p503, SIDH-p503-compressed, SIDH-p610, SIDH-p610-compressed, SIDH-p751, SIDH-p751-compressed, SIKE-p434, SIKE-p434-compressed, SIKE-p503, SIKE-p503-compressed, SIKE-p610, SIKE-p610-compressed, SIKE-p751, SIKE-p751-compressed

Im VAUClientHelloData führt der Client zusätzlich auf:

"PQC.PublicKey" : [ "...Verfahrensidentifikator...", "...base64-kodierter-Public-Key-des-PQC-KEM-Verfahrens..."]

"Verfahrensidentifikator" steht für einen der o. g. KEM-Identifier. In [liboqs] ist jeweils für jedes Verfahren eine "KeyGen"-Funktion definiert. Diese erzeugt zufällig ein Schlüsselpaar und gibt als Ergebnis u. a. den öffentlichen Schlüssel aus. Dieser wird so wie er aus der Referenzimplementierung kommt, per base64-Kodierung kodiert im Feld "base64-kodierter-Public-Key-des-PQC-KEM-Verfahrens" eingetragen.

Der Server akzeptiert optionale Attribute in den JSON-Nachrichten des VAU-Handshakes auf Grund von A\_17074-\*. Wenn er das Verfahren ebenfalls unterstützt, dann fügt er den öffentlichen Teil des Ergbnisses der Encaps(öffentlicher Schlüssel des Clients)-Funktion im VAUServerHelloData wie folgt base64-kodiert auf:

"PQC.Encaps" : "... base64-kodierter-öffentlicher-Teil-von-Encaps(öffentlicher Schlüssel des Clients) ..."

Beim Aufruf von Encaps(öffentlicher Schlüssel des Clients) wird als Ergebnis der Funktion ein öffentlicher Teil und ein geheimer Schlüssel K als Ergebnis berechnet. Der VAU-Server fügt bei der Schlüsselableitung der symmetrischen Sitzungsschlüssel (vgl. A\_16943-\*) neben dem gemeinsamen ECDH-Geheimnisse noch "Verfahrensidentifikator" || K als Eingabe für die HKDF hinzu (IKM= gemeinsames ECDH-Geheimnis || Verfahrensidentifikator || K). Damit hängen die abgeleiteten Sitzungsschlüssel sowohl vom ECDH-Geheimnis als auch vom geheimen Schlüssel K, also vom PQC-KEM, ab.

Bei Erhalt der VAUServerHello-Nachricht im VAU-Client, führt der VAU-Client die Funktion Decaps(s, decodierter öffentlicher Encaps-Wert) aus, wobei s der private Client-PQC-Schlüssel aus der Schlüsselpaarerzeugung für PublicKeyPQC ist (vgl. KeyGen-Funktion). Als Ergebnis erhält er K. Damit kann er genau wie der VAU-Server die Schlüsselableitung der symmetrischen Sitzungsschlüssel (vgl. A\_16943-\*) durchführen (IKM= gemeinsames ECDH-Geheimnis || Verfahren-ID || K). 

Sollte der Client bei Erhalt der VAUServerHello-Nachricht kein "Encaps"-Datenfeld im VAUServerHelloData-Teil vorfinden, so unterstützt der VAU-Server das Verfahren nicht. Dem VAU-Client steht es dann frei, den Verbindungsaufbau ohne PQC-Verfahren weiter durchzuführen, den Verbindungsaufbau abzubrechen oder den Verbindungsaufbau neu zu beginnen.

Wenn die Schlüsselableitung bei beiden Kommunikationspartnern erfolgreich durchgeführt werden konnte -- d. h., der VAU-Protokoll-Handshake konnte erfolgreich abgeschlossen werden, dann verläuft der Protokollablauf wie in Abschnitt ff definiert wie üblich weiter. 

Ähnlich wie bei der Anwendung ePA besitzt der Fachdienst E-Rezept zwei HTTP-Schnittstellen. Die dabei vom Nutzer (Client) aufgebaute TLS-Verbindung endet an einer dieser HTTPS-Schnittstellen. Die E-Rezept-VAU liegt hinter den Webschnittstellen. Um die Verbindungsstrecke zwischen HTTPS-Schnittstellen und E-Rezept-VAU zu schützen, verschlüsselt und kodiert der Client seine HTTP-Requests (als innere Requests bezeichnet) auf die im Abschnitt  definierte Weise. Diese so erzeugten HTTP-Requests (äußere Requests) sendet der Client per HTTPS an eine der Webschnittstellen des E-Rezept-Dienstes. Dabei ist für die Schnittstelle ein regelmäßig wechselndes Nutzerpseudonym im äußeren HTTP-Request sichtbar. Dieses unterstützt den Fachdienst E-Rezept bei der Lastverteilung und beim DoS-Schutz auf Applikationsebene. Von der Webschnittstelle erhält die E-Rezept-VAU die verschlüsselten Requests, entschlüsselt und verarbeitet diese. Als Antwort erzeugt die E-Rezept-VAU einen für den Client verschlüsselte HTTP-Response. Den Schlüssel dafür hat der Client für die VAU ephemer erzeugt und dieser Schlüssel ist Teil des verschlüsselten Requests. Die Webschnittstelle empfängt das Chiffrat von der VAU und gibt dieses als Antwort auf den HTTP-Request an den Client zurück. 

Ablauf:

1. Der Client erfragt initial das X.509-Zertifikat der VAU (A\_20160). Je nachdem, ob die X.509-Root der TI oder die TSL als Prüfbasis verwendet wird, erfolgt die Abfrage des VAU-X.509-Zertifikats spezifisch (entweder A\_21216 oder A\_21218). Im Zertifikat ist der öffentliche Verschlüsselungsschlüssel der E-Rezept-VAU enthalten. Dieses Zertifikat kommt aus der Komponenten-PKI der TI und ist langlebig, d. h. der Client kann dieses Zertifikat (inkl. Schlüssel) für folgende Verschlüsselungen lokal vorhalten.
1. Der Client erzeugt einen HTTP-Request mit Request-Body und Request-Header als Datenstrukturen (= innerer HTTP-Request) (A\_20161).
1. Der Client verschlüsselt diesen Request mit dem Verschlüsselungsschlüssel der E-Rezept-VAU. Im Chiffrat ist ein Authentisierungstoken des Nutzers enthalten, eine zufällig gewählte Request-ID, ein vom Client ephemer erzeugter symmetrischer Antwortschlüssel und der am Anfang erzeugte HTTP-Request als Datenstrom (A\_20161).
1. Der Client erzeugt einen neuen (äußeren) HTTP-Request und überträgt darin das Chiffrat an eine HTTPS-Schnittstelle des Fachdienstes E-Rezept. Dabei gibt der Client ggf. das schon aus einer vorherigen Response des Fachdienstes E-Rezept mitgeteilte Nutzerpseudonym (A\_20161) mit.
1. Die Webschnittstelle nimmt den Request entgegen und trifft eine Routing-Entscheidung oder eine Priorisierungsentscheidung im Lastfall. Anschließend leitet sie den Request an die VAU weiter (A\_20162).
1. Die VAU entschlüsselt den Request und verarbeitet ihn. Die Antwort wird inkl. der Request-ID mit dem vom Nutzer erzeugten Antwortschlüssel verschlüsselt und an die Webschnittstelle gesendet.
1. Die Webschnittstelle antwortet gegenüber dem Client mit diesem Chiffrat auf den HTTP-Request.
1. Der Client entschlüsselt das Chiffrat und prüft die Request-ID in der entschlüsselten Antwort.

Das Protokoll ist statuslos. Zwischen verschiedenen VAU-Instanzen (bspw. VAU-Instanzen in unterschiedlichen Brandabschnitten eines Rechenzentrum) müssen keine Session-Schlüssel oder ähnliches synchronisiert werden.

Die Struktur der inneren HTTP-Request ist so einfach, dass davon auszugehen ist, dass in der VAU-Instanz keine umfangreichen Webserver oder HTTP-Bibliotheken notwendig sind. Ziel der E-Rezept-VAU ist es die Code-Komplexität (Trusted Computing Base, TCB) so weit es nur irgendwie geht minimal zu halten.

![](Aspose.Words.2d194658-3910-4b4a-bf6b-abf9f3411a63.004.png)

Abbildung #: Sicherungsschichten beim Datentransport zwischen E-Rezept-Client und E-Rezept-VAU

Die gematik stellt eine Beispielimplementierung bereit.

Hinweis: Unter "/VAUCertificateOCSPResponse" erhält ein Client (einfacher GET-Request) eine korrekte OCSP-Response für das VAU-Zertifikat (A\_20160-\*, Punkt 1). Dies ist analog wie OCSP-Stapling bei TLS zu sehen, nur auf einer höheren OSI-Schicht. Der FD stellt korrekte OCSP-Responses zur Verfügung damit nicht jeder Client selbst den OCSP-Responder fragen muss. Diese Funktionalität hat nichts mit der OCSP-Proxy-Funktionalität zu tun wie sie bspw. beim Zugangsgateway des Versicherten bei ePA angeboten wird. Der FD fragt bspw. stündlich selbst den OCSP-Status für sein VAU-Zertifikat ab, prüft die Antwort und stellt sie unter "/VAUCertificateOCSPResponse" Clients zur Verfügung. 

Hinweis: A\_20967 beschreibt ein analoges Vorgehen wie es bei den SGD(1,2) üblich ist. Der Betreiber des FD besitzt für bestimmte Rollenauthentisierungen für die HSM Authentisierungschipkarten inkl. PIN, die gematik ebenfalls. Nur bei gleichzeitiger Authentisierung beider Beteiligter erlauben die HSM bestimmte Aktionen/Funktionalitäten.

Bevor ein E-Rezept-Client die E-Rezept-VAU-Identität für die Verschlüsselung seiner Request (vgl.  ) verwendet muss der Client deren X.509-Zertifikat prüfen ([gemSpec\_eRp\_FdV#A\_19739], [gemILF\_PS\_eRP#A\_20769]). 

Ein E-Rezept-Client auf einen Praxisverwaltungssystem (PVS) oder einen Apothekenverwaltungssystem (AVS) muss die TSL als Prüfbasis für solch eine Prüfung verwenden [gemILF\_PS\_eRP#A\_20764].
Da ein E-Rezept-FdV nur zwei TI-Zertifikate prüfen muss, wird im FdV die technisch deutlich einfachere Zertifikatsprüfung auf Basis der TI-X.509-Root verwendet [gemSpec\_eRp\_FdV#A\_20032-\*], und nicht die Prüfung über die TSL wie im Client eines PVS oder AVS [gemILF\_PS\_eRP#A\_20764]. Beide Prüfwege sind sicherheitstechnisch äquivalent. 

Der E-Rezept-FD muss für die Zertifikatsprüfung im E-Rezept-FdV eine (außer für die Verfügbarkeit) sicherheitsunkritische Unterstützungsleistung erbringen und dafür folgend benannte Zertifikate zum Download anbieten. 
Zunächst erfolgen mit Tab\_KRYPT\_ERP\_Zertifikatsliste und Tab\_KRYPT\_ERP\_Algorithmus\_FD\_Zertifikatsliste\_erstellen zwei Hilfsdefinitionen. 

Tabelle #: Tab\_KRYPT\_ERP\_Zertifikatsliste Definition Datenstruktur Zertifikatsliste 

|{<br>`   `"add\_roots" : [ "base64-kodiertes-Root-Cross-Zertifikat-1", ... ],<br>`   `"ca\_certs"  : [ "base64-kodiertes-Komponenten-CA-Zertifikat-1", ... ],<br>`   `"ee\_certs"  : [ "base64-kodiertes-EE-Zertifikat-1-aus-einer-Komponenten-CA", ... ]<br>}|
| :- |
Tabelle #: Tab\_KRYPT\_ERP\_Algorithmus\_FD\_Zertifikatsliste\_erstellen 

|(1)<br>Als Startpunkt muss eine Datenstruktur nach "Tab\_KRYPT\_ERP\_Zertifikatsliste" (ein Associative-Array) erzeugt werden, bei dem die Array-Elemente jeweils leer sind:<br>{ "add\_roots" : [], "ca\_certs" : [], "ee\_certs" : []}<br>(2)<br>Im Array "ee\_certs" wird das E-Rezept-VAU-Zertifikat (vgl. A\_20160) base64-kodiert hinzugefügt werden.<br>(3) <br>Im Array "ee\_certs" werden alle IDP-Signatur-Zertifikate (oid\_idpd [gemSpec\_OID]) die dem FD bekannt sind base64-kodiert am Ende angefügt.<br>Die gematik teilt dem E-Rezept-FD regelmäßig die aktuelle vollständige Liste mit.<br>(4)<br>Im Array "ca\_certs" werden alle Komponenten-CA-Zertifikat base64-kodiert eingetragen, die die Zertifikate aus "ee\_certs" bestätigt haben. Hinweis: Diese Komponenten-CA-Zertifikate findet man in der TSL und ebenfalls auf <https://download.tsl.ti-dienste.de/SUB-CA/> <br>(5) <br>Falls es in "ca\_certs" CA-Zertifikate gibt die nicht per Signaturprüfung auf den Root-Schlüssel vom RCA3 rückführbar sind, werden nacheinander die chronologisch auf einander folgenden base64-kodierten Root-Cross-Zertifikate (RCA3->RCA4, ... RCA(x)->RCA(x+1)) am Ende des Arrays "add\_roots" angefügt, solange bis alle CA-Zertifikate über einen der Root-Schlüssel prüfbar sind, d. h. per Signaturprüfung auf einen Root-Schlüssel im Array rückführbar sind. Hinweis: dieses Cross-Zertifikate findet man auf <https://download.tsl.ti-dienste.de/ROOT-CA/>  |
| :- |
Hinweis: zum produktiven Start des E-Rezept-FD enthält das Array "ee\_certs" drei Elemente (Zertifikat des VAU-Protokolls, Signaturzertifikat des Discovery-Dokumentes, Signaturzertifikat des ID\_Token), das Array "ca\_certs" ein Element und das Array "add\_roots" null Elemente. 

Tabelle #: Tab\_KRYPT\_ERP\_FdV\_Truststore\_aktualisieren 

|(1)<br>Alle Zertifikate im Truststore müssen gelöscht werden mit Ausnahme von RCA3.<br>Der Truststore besitzt, wie in A\_21218 definiert, Prüfschlüssel/Zertifikate in vier Kategorien (A) Root-Schlüssel, (B) CA-Zertifikate, (C) E-Rezept-VAU-Zertifikat, (D) IDP-Zertifikat(e).<br>(2) <br>Falls die Zertifikatsliste im Array "add\_roots" nichtleer ist, so wird das erste Cross-Zertifikat im Array auf Basis von RCA3 per Signaturprüfung geprüft. Ebenfalls wird geprüft, ob der bestätigte CommonName dem Muster "GEM.RCA" + Zahl entspricht. Falls beide Prüfungen mit positiven Prüfergebnis erfolgen konnten, so wird das Zertifikat in Kategorie (A) des Truststores aufgenommen. Weitere Zertifikate im Array werden analog mit dem jeweils vorherigen Cross-Zertifikat per Signaturprüfung und CommonName-Prüfung geprüft und bei positiven Prüfergebnissen in Kategorie (A) des Truststores aufgenommen.<br>(3)<br>Für jedes Zertifikat im Array "ca\_certs" wird überprüft, ob es zeitlich gültig ist, ob es per Signaturprüfung auf einen Root-Schlüssel aus (A) rückführbar ist und ob der bestätigte CommonName dem Muster "GEM.KOMP-CA" + Zahl entspricht. Wenn alle drei Prüfungen ein positives Prüfergebnis liefern, so wird das Zertifikat in Kategorie (B) des Truststores aufgenommen.<br>(4) <br>Für jedes Zertifikat im Array "ee\_certs" wird überprüft ob es zeitlich gültig ist und ob es per Signaturprüfung auf einen CA-Schlüssel aus (B) rückführbar ist. Wenn nicht beide Prüfungen ein positives Prüfergebnis liefern, so wird das Zertifikat verworfen.<br>Anderen falls wird geprüft, ob das Zertifikat eine OID mit dem Wert oid\_erp-vau [gemSpec\_OID] enthält. Dann wird es im Truststore bei Kategorie (C) eingefügt. Falls das Zertifikat eine OID mit dem Wert oid\_idpd [gemSpec\_OID] enthält. Dann wird es im Truststore bei Kategorie (D) eingefügt.|
| :- |
Tabelle #: Tab\_KRYPT\_ERP\_OCSP\_Liste Definition Datenstruktur OCSPList 

|{<br>`   `"OCSP Responses": [ "base64-kodiertes-OCSP-Responce-EE-Zertifikat-1", ... ]<br>} |
| :- |
Tabelle #: Tab\_KRYPT\_ERP Kodierung des Chiffrats aus A\_20161-\* 

|**Offset**|**Länge in Bytes**|**Erläuterung**|
| :- | :- | :- |
|0|1|Versionsfeld|
|1|32|X-Koordinate öffentlicher ephemer Sender-ECDH-Schlüssel|
|33|32|Y-Koordinate öffentlicher ephemer Sender-ECDH-Schlüssel |
|65|12|IV zufällig pro Nachricht zu erzeugen (A\_20161-\* Punkt e)|
|77|gleich Länge des Plaintextes (= LP)|"eigentliche" AES-GCM-Chiffrat|
|77 + LP|16|128 Bit langer Authentication-Tag|
Hinweise zu A\_20161-\*:

1. Beispiel für eine hexadezimalkodierte Request-ID nach A\_20161 (2): "32b6594cc29bb54a14cb2a8e09558817"
1. Beispiel für einen 128-Bit-AES-Schlüssel nach A\_20161 (3): "a576daad8096fc52987250a8e7eb9bd3"
1. Aus kryptographischer Sicht könnte ein Client den Antwort-AES-Schlüssel (A\_20161 Punkt (3)) auch für weitere Requests verwenden. Dies würde jedoch erzwingen, dass es im Client eine komplexere Überwachung des Lebenslaufs des Schlüssels gibt (Wann wurde er erzeugt,  d. h. wann muss er gewechselt werden etc.). Um dies zu verhindern und die Implementierung im Client einfacher zu halten, gibt es A\_20161 Punkt (4).

Beispielverschlüsselung (Testvektor):

Der Langzeit-VAU-Schlüssel nach A\_20160-\* sei folgender:
x=0x8634212830dad457ca05305e6687134166b9c21a65ffebf555f4e75dfb048888 
y=0x66e4b6843624cbda43c97ea89968bc41fd53576f82c03efa7d601b9facac2b29 

Die zu Verschlüsselnde Nachricht sei "Hallo Test" (10 Zeichen).

Der Client erzeugt zufällig den privaten ECC-Schlüssel d=5bbba34d47502bd588ed680dfa2309ca375eb7a35ddbbd67cc7f8b6b687a1c1d

Damit ist dessen öffentlicher ephemerer ECDH-Schlüssel:
x=0x754e548941e5cd073fed6d734578a484be9f0bbfa1b6fa3168ed7ffb22878f0f 
y=0x9aef9bbd932a020d8828367bd080a3e72b36c41ee40c87253f9b1b0beb8371bf 

Nach ECDH ergibt sich damit folgendes gemeinsames Geheimnis:
9656c2b4b3da81d0385f6a1ee60e93b91828fd90231c923d53ce7bbbcd58ceaa

Nach Schlüsselableitung (info="ecies-vau-transport") erhält der Client folgende CEK:
23977ba552a21363916af9b5147c83d4

Der Client erzeugt zufällig einen 12 Byte großen IV:
257db4604af8ae0dfced37ce

Die AES/GCM-Chiffre berechet aus der Nachricht, dem CEK und dem IV folgendes Chiffrat:

86c2b491c7a8309e750b und folgenden 16 Byte großen Authentication Tag 4e6e307219863938c204dfe85502ee0a

Das Gesamt-Chiffrat vollständig kodiert ist damit (ohne Leerzeichen, als Hexdump)

01 754e548941e5cd073fed6d734578a484be9f0bbfa1b6fa3168ed7ffb22878f0f 9aef9bbd932a020d8828367bd080a3e72b36c41ee40c87253f9b1b0beb8371bf 257db4604af8ae0dfced37ce 86c2b491c7a8309e750b 4e6e307219863938c204dfe85502ee0a

In der Webschnittstelle muss ein CMAC-Schlüssel für die Bildung der Nutzerpseudonyme vorliegen (A\_20162-\*). Dieser Schlüssel wird regelmäßig gewechselt (A\_20162-\*) und er kann in der Webschnittstelle als normales Datenobjekt (also nicht innerhalb des HSMs) vorliegen (Schutzbedarf bezüglich Vertraulichkeit: mittel).

Beispiele für mögliche Pfade die nach A\_20162 von einem Client erzeugt werden könnten:

/VAU/0
/VAU/0/Task/create
/VAU/270810c79748768a9b0aefbf52c8d72be7ad5e0d2d328d9bb70dbf58623fc7ae

Der Fachdienst E-Rezept besitzt eine REST-Schnittstelle, d. h. Fehler werden mittels HTTP-Status/Fehler-Codes signalisiert. Die in der folgenden Tabelle (Tab\_KRYPT\_VAUERR) aufgeführten Fehler kann ein E-Rezept-Client in Bezug auf die in diesem Abschnitt definierte kryptographische Sicherung zwischen Client und VAU treffen.

Tabelle #: Tab\_KRYPT\_VAUERR Auftretende Fehler bei auf Anwendungsschicht kryptographisch gesicherten VAU-Kommunikation (E-Rezept) 

|**Fehlerfall**|**HTTP-Response-Code der E-Rezept**|
| :- | :- |
|JWT-Client-Token ungültig|403 Forbidden|
|Entschlüsselung des Chiffrats des äußeren Requests schlug fehl|400 Bad Request|
|Strukturaufbau des Klartextes aus A\_20160 ist falsch|400 Bad Request|
Zur Auffrischung des Entropie-Pools des Clients kann der Client von verschiedenen Diensten der TI Zufall ausreichender Güte (vgl. GS-A\_4367) beziehen. Der FD-E-Rezept ist dafür eine Quelle von mehreren. Ein Client muss verschiedene unabhängige Quellen abfragen und die Zufallsdaten kryptographisch geeignet (bspw. über den Fortuna-PRNG-Algorithmus) zusammenführen.

Um die Anforderung umzusetzen ist es im Normalfall ausreichend /dev/urandom als Zufallsquelle auf einen Linux-Server zu verwenden.

Wie in [BSI-PQC-2020] dargestellt, erscheint es mit Blick auf dem aktuellen Stand von Wissenschaft und Technik als sehr unwahrscheinlich, dass aktuell Quanten-Computer in ausreichender Leistungsstärke verfügbar sind, die der asymmetrischen Kryptographie -- so wie sie aktuell in der TI eingesetzt wird -- gefährlich werden könnten. 

Dies bedeutet, dass insbesondere Authentisierungsvorgänge, die im "Jetzt" mit klassischen asymmetrischen kryptographischen Verfahren mit ausreichend großen Schlüssellängen durchgeführt werden (vgl. [SOG-IS-2020] und [BSI-TR-03116-1]), nicht in Frage stehen.

Schwieriger wird es mit der Verschlüsselung mit klassischen asymmetrischen Verfahren bei denen Chiffrate erzeugt werden, die ein Angreifer sammeln kann, und durch deren Entschlüsselung zu einer Zeit in der Zukunft, bei der solche Quanten-Computer verfügbar sind, dann Schaden entstehen kann.

Dort erscheint es ratsam auf hybride Lösungen zu migriren. D. h., etablierte kryptographische asymmetrische Verfahren und post-quantum-sichere asymmetrische kryptographische Verfahren werden in einer Weise kombiniert, dass wenn genau nur eines der beiden Verfahren gebrochen wird, die Sicherheit (Vertraulichkeit und Integrität) der verschlüsselten Daten nicht gefährdet ist.

Aktuell gibt es diesbezüglich verschiedene Forschungsaktivitäten und Vorschläge für eine entsprechende hybride Protokoll-Erweiterungen von kryptographischen Protokollen wie TLS, IKE oder SSH [TLS-CC-2021], [ENISA-PQC-2021#6.1]. Die gematik beobachtet intensiv die laufenden Forschungs- und Evaluierungsaktivitäten [NIST-PQC] die voraussichtlich 2022/23 einen geeigneten Stand erreichen werden. Bei TI-spezifischen Protokollen (VAU-Protokoll, SGD-Protokoll) evaluiert die gematik aktuell PQC-Protokollerweiterungen die kryptographisch denen bei TLS [TLS-CC-2021] entsprechen (vgl. Abschnitt ""). 

Im Folgerelease wird es in diesem Abschnitt Hinweise für die Anforderungen aus Abschnitt  geben. 

In anderen, nicht-TI Public-Key-Infrastrukturen werden öffentliche Schlüssel bei einer Zertifikatsantragsstellung immer mittels ihrem korrespondieren privaten Schlüssel signiert (vgl. Certificate Signing Request [RFC-2986], proof of posession). Dort kann der TSP sich nach einer erfolgreichen Signaturprüfung sicher sein, dass er aus Kodierungssicht den "richtigen" Schlüssel in den Händen hält, weil ansonsten die Signaturprüfung mit praktischer Sicherheit fehlschlägt. Missverständnisse aufgrund von "falscher" Byte-Order oder verschiedener Kodierung sind somit praktisch (Falsch-Positiv-Rate < 2-100) ausgeschlossen. In der PKI der TI werden mehr als 95 % aller Zertifikatserstellungen ohne eine Signatur mittels der jeweiligen privaten Schlüssel durchgeführt. Ein TSP der TI kann damit bei RSA-Schlüsseln – aus den Schlüsselwerten an sich – im Regelfall nicht sicher erkennen, ob eine Fehlkodierung (Missverständnis zwischen Zertifikatsantragssteller und TSP) aufgetreten ist. Es gibt effiziente Möglichkeiten solche Fehlkodierungen zu erkennen. Den Einsatz solcher Möglichkeiten möchte die gematik befördern und gibt mit   und zwei Verfahren als KANN-Anforderungen an.  

Die Untersuchungen aus [MK-2016] und [ROCA-2017] zeigen, dass es hilfreich ist sich mit den konkreten Werten der RSA-Schlüssel zu beschäftigen. Die folgenden Verfahren nutzen Struktureigenschaften von RSA-Schlüsseln, die nicht-RSA-Schlüssel im Normalfall nicht vorweisen. 

keine kleinen Primteiler:

Der Modulus eines RSA-Schlüssels muss aus genau zwei (oder wenigen [RFC-8017]) "großen" Primfaktoren bestehen. Falls der vom TSP angetroffene Wert durch eine vom TSP vorgegebene Primzahl teilbar ist, so ist der RSA-Schlüssel ungeeignet. Falls dieser Primteiler deutlich kleiner als 2^1023 ist, so kann es sich nicht um einen korrekten RSA-Schlüssel handeln.

Wird ein Modulus unabsichtlich von einem Sender falsch kodiert, so ist der dadurch entstehende Wert statistisch über alle möglichen Fehlkodierungen betrachtet im Normalfall mit der Wahrscheinlichkeit von 1/2 durch zwei teilbar, mit der Wahrscheinlichkeit von 1/3 durch 3 teilbar, mit einer Wahrscheinlichkeit von 1/5 durch 5 teilbar usw. Falls man nun den Modulus durch die ersten Primzahlen kleiner als 100 (25 Primzahlen) versucht zu teilen (was effizient möglich ist) und eine Teilbarkeit ausschließen kann, so kann man eine unabsichtliche Fehlkodierung mit einer hohen Wahrscheinlichkeit erkennen.

In der gematik wurden mehr als eine Billion (10^12) RSA-Schlüssel zufällig erzeugt und verschiedene Fehlkodierungen dieser Schlüssel auf Primteiler kleiner 100 untersucht. Es wurden dabei folgende Erkennungsraten festgestellt.

|**Art der Fehlkodierung**|**Erkennungsrate in Prozent <br>(auf zwei Nachkommastellen gerundet)**|
| :- | :- |
|Byte-Order falsch (vertauscht)|76,03 %|
|Off-by-One (left shift)|100 %|
|Off-by-One (right shift)|88,07 %|
|Base64-kodiert anstatt Binär|87,60 %|
|Base58-kodiert anstatt Binär|88,01 %|
|Hex-kodiert anstatt Binär|87,91 %|
Man muss davon ausgehen, dass die entsprechende Fehlkodierung nicht nur bei einem einzigen RSA-Schlüssel, sondern bei allen RSA-Schlüsseln eines Personalisierungsauftrags auftritt. Somit nähert sich die Erkennungsrate exponentiell 100 % an. Beispiel: bei einer Erkennungsrate von 75 % für eine bestimmte Art der Fehlkodierung (vgl. Tabelle) erhält man bei 1000 RSA-Schlüsseln in Gesamtheit eine Erkennungsrate von mehr als 1-1,15\*10^-125, also nahe 1.

öffentlicher Exponent ist prim:

Sei e der öffentliche Exponent und n der Modulus eines RSA-Schlüssels. Bei der Wahl von e ist es notwendig, dass dieser relativ prim zu phi(n) ist. Um die Schlüsselerzeugung zu vereinfachen (und zu beschleunigen), wählen jedoch faktisch alle kryptographischen Softwarebibliotheken, Chipkarten und HSMs e prim. Wenn also dem TSP ein e vorliegt, das nicht prim ist, so kann er davon ausgehen, dass ein Fehler vorliegt.

Diese Überlegungen führen zu den Tests in  . Diese Tests haben eine Falsch-Positiv-Rate von 0 und benötigen weniger als 7 Mikrosekunden pro RSA-Schlüssel. 

Entropie der Schlüsselkodierung:

Der Modulus eines RSA-Schlüssels muss aus genau zwei (oder wenigen [RFC-8017]) "großen" zufällig gewählten Primfaktoren bestehen. Diese zufällige Wahl hat zur Folge, dass die Entropie der kodierten Schlüsselwerte eine hohe Entropie im Sinne von notwendigen Bits pro Byte besitzt. Eine Fehlkodierung wird evtl. weniger Entropie (Bits pro Byte) besitzen, weil sie, wie die base64-Kodierung, bestimmte Bits immer auf 0 setzt. In [NIST-SP-800-22] werden verschiedene Tests spezifiziert, um die "Zufälligkeit" einer Zeichenfolge zu bestimmen. Diese Tests zielen auf größere Datengrößen (Längen der Zeichenfolge) ab und sind nur teilweise dafür geeignet die Kodierung von 256 Byte langen RSA-Moduli zu bewerten. Anstatt diese Tests als Basis zu verwenden, wird im Folgenden die klassische Berechnung der Shannon-Entropie vieler RSA-Moduli in unterschiedlichen Kodierungsformen betrachtet. Von einer Zeichenkette X wird mittels 

![](Aspose.Words.2d194658-3910-4b4a-bf6b-abf9f3411a63.005.png)

die Entropie im Sinne von notwendigen Bits pro Byte des kodierten Schlüsselwertes berechnet. Dabei ist X die Kodierung (Bytefolge) des Schlüssels und pi die relative Häufigkeit von Byte i (wobei nach Konvention in dem Kontext gilt: log(0)=0). 

Unter <https://rosettacode.org/wiki/Entropy> findet man Implementierung dieser Entropie-Berechnungsfunktion in 78 Programmiersprachen.  

Die gematik verwendet folgende C-Implementierung:

double entropy(char \*S, int len) {
`        `int table[256]={0};
`        `int i;
`        `double H=0;

`        `for(i=0; i<len; i++) {
`            `table[(unsigned char)S[i]]++;
`        `}
`        `for(i=0; i<256; i++) {
`            `if (table[i]>0) {
`                `H-= (double) table[i]/len\*log2( (double) table[i]/len);
`            `}
`        `}
`        `return H;
}

In der gematik wurden mehr als eine Billion (10^12) RSA-Schlüssel zufällig erzeugt und verschiedene Fehlkodierungen auf ihre Entropie (notwendigen Bits pro Byte in der Kodierung) untersucht.

Ein Histogramm eines Beispiel-Testlaufs mit mehr als eine Billion (10^12) RSA-Schlüsseln:

|**8    >=H(X)>7,455**|**3396**|
| :- | :- |
|7,455>=H(X)>7,2135|234195871140|
|7,2135>=H(X)>6,9715|765693789112|
|6,9715>=H(X)>6,7295|112336352|
Es wurde kein Schlüssel gefunden, dessen korrekte Kodierung eine Entropie kleiner als 6,7295 besitzt.

Ein Histogramm eines Beispiel-Testlaufs mit mehr 10 Milliarden (1\*10^10) Schlüsseln (diese wurden jeweils in unterschiedlichen Kodierungsvarianten kodiert und danach wurde die entropy()-Funktion auf die Kodierung angewendet):

|korrekt kodiert (s. o.)<br><br>7.40 49808<br>7.30 97418682<br>7.20 3351624284<br>7.10 6095663118<br>7.00 1210930726<br>6.90 43696816<br>6.80 256390<br>6.70 176|Base64-kodiert<br><br>5.90 9981660<br>5.80 6902282798<br>5.70 3861576302<br>5.60 25792616<br>5.50 6624|Base58-kodiert<br><br>5.80 11220<br>5.70 4102181822<br>5.60 6615817484<br>5.50 81606244<br>5.40 23230|als Hexadezimal-Zahl kodiert<br><br>3.90 10758804076<br>3.80 40835572<br>3.70 352|
| :- | :- | :- | :- |
Diese Überlegungen bezüglich der Entropie der RSA-Schlüsselkodierung führen zu dem Test in . Dieser Test hat eine Falsch-Positiv-Rate von weniger als 2^-40 und benötigen weniger als 7 Mikrosekunden pro RSA-Schlüssel.  

|**Kürzel** |**Erläuterung** |
| :- | :- |
|C2C |Card to Card |
|C2S |Card to Server |
|CEK |Content Encryption Key |
|CA |Certificate Authority |
|CBC |Cipher Block Chaining |
|DNS |Domain Name System |
|DNSSEC |Domain Name System Security Extensions |
|DRNG |Deterministic Random Number Generator |
|eGK |elektronische Gesundheitskarte |
|HKDF |HMAC-based Extract-and-Expand Key Derivation Function |
|HMAC |Hash-based Message Authentication Code |
|IV |Initialization Vector (Initialisierungsvektor) bspw. bei AES-GCM |
|ICV |Integrity Check Value, Authentisierungswert (MAC) bei AES-GCM |
|KDF |Key Derivation Function (Schlüsselableitungsfunktion) |
|MAC |Message Authentication Code |
|OCSP |Online Certificate Status Protocol |
|OID |Object Identifier |
|OSI |Open Systems Interconnection |
|SAK |Signaturanwendungskomponente |
|SGD |Schlüsselgenerierungsdienst |
|SE|Secure Element|
|SM |Service Monitoring |
|TCB|Trusted Computing Base|
|TI |Telematikinfrastruktur |
|TLS |Transport Layer Security |
|TPM|Trusted Plattform Module|
|TSIG |Transaction Signature |
|URI |Uniform Resource Identifier |
|VAU |vertrauenswürdige Ausführungsumgebung, vgl. [gemSpec\_Dokumentenverwaltung] |
|WANDA Basic|Weitere Anwendungen für den Datenaustausch ohne Nutzung der TI oder derer kryptografischen Identitäten  |
Das Glossar wird als eigenständiges Dokument, vgl. [gemGlossar] zur Verfügung gestellt.

Die nachfolgende Tabelle enthält die Bezeichnung der in dem vorliegenden Dokument referenzierten Dokumente der gematik zur Telematikinfrastruktur. Der mit der vorliegenden Version korrelierende Entwicklungsstand dieser Konzepte und Spezifikationen wird pro Release in einer Dokumentenlandkarte definiert; Version und Stand der referenzierten Dokumente sind daher in der nachfolgenden Tabelle nicht aufgeführt. Deren zu diesem Dokument jeweils gültige Versionsnummer entnehmen Sie der aktuellen, von der gematik veröffentlichten Dokumentenlandkarte, in der die vorliegende Version aufgeführt wird.

|**[Quelle]**|**Herausgeber: Titel**|
| :- | :- |
|[gemGlossar]|gematik: Glossar der Telematikinfrastruktur|
|[gemSpec\_COS]|gematik: Spezifikation des Card Operating System (COS)|
|[gemSpec\_Dokumentenverwaltung]|gematik: Spezifikation ePA-Dokumentenverwaltung|
|[gemSpec\_DS\_Anbieter]|Spezifikation Datenschutz- und Sicherheitsanforderungen der TI an Anbieter|
|[gemSpec\_eGK\_ObjSys]|gematik: Die Spezifikation der elektronischen Gesundheitskarte (eGK) – Objektsystem|
|[gemSpec\_KT]|gematik: Spezifikation eHealth-Kartenterminal|
|[gemSpec\_MobKT]|gematik: Spezifikation Mobiles Kartenterminal|
|[gemSpec\_SGD\_ePA]|gematik: Spezifikation Schlüsselkommentierungsdienst ePA|
|[gemSpec\_SST\_FD\_VSDM]|gematik: Schnittstellenspezifikation Fachdienste (UFS/VSDD/CMS)|
|[gemSpec\_Zugangsgateway\_Vers]|gematik: Spezifikation Zugangsgateway des Versicherten ePA|


|**[Quelle]**|**Herausgeber (Erscheinungsdatum): Titel**|
| :- | :- |
|[ABR-1999]|DHIES: An Encryption Scheme Based on the Diffie–Hellman Problem<br>Abdalla, Michel and Bellare, Mihir and Rogaway, Phillip, 1999<br><http://web.cs.ucdavis.edu/~rogaway/papers/dhies.pdf> |
|[AIS-20-1999]|W. Schindler: Functionality Classes and Evaluation Methodology for<br>Deterministic Random Number Generators. Version 1.0, 02.12.1999,<br>ehemalige mathematisch technische Anlage zur AIS20,<br>[https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Zertifierung /Interpretation/AIS20_Functionality_Classes_Evaluation_Methodology_ DRNG.pdf?__blob=publicationFile](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Zertifierung /Interpretation/AIS20_Functionality_Classes_Evaluation_Methodology_ DRNG.pdf?__blob=publicationFile)|
|[AIS-20]|AIS 20: Funktionalitätsklassen und Evaluationsmethodologie für<br>deterministische Zufallszahlengeneratoren, Version 3, 15.05.2013,<br>[https://www.bsi.bund.de/SharedDocs/Downloads/DE/BSI/Zertifierung/Interpretation /AIS_20_pdf.pdf?__blob=publicationFile](https://www.bsi.bund.de/SharedDocs/Downloads/DE/BSI/Zertifierung/Interpretation /AIS_20_pdf.pdf?__blob=publicationFile)|
|[AIS-31]|AIS 31: Funktionalitätsklassen und Evaluationsmethodologie für<br>physikalische Zufallszahlengeneratoren, Version 3, 15.05.2013,<br>[http://www.bsi.bund.de/SharedDocs/Downloads/DE/BS/Zertifierung/Interpretationen/ AIS_31_pdf.pdf?__blob=publicationFile](http://www.bsi.bund.de/SharedDocs/Downloads/DE/BS/Zertifierung/Interpretationen/ AIS_31_pdf.pdf?__blob=publicationFile)|
|[ALGCAT]|Bekanntmachung zur elektronischen Signatur nach dem Signaturgesetz<br>und der Signaturverordnung (Übersicht über geeignete Algorithmen),<br>Bundesnetzagentur für Elektrizität, Gas, Telekommunikation, Post und<br>Eisenbahnen, vom 30.12.2016 (auch online verfügbar:<br><https://www.bundesanzeiger.de> mit dem Suchbegriff<br>„BAnz AT 30.12.2016 B5“)|
|[ANSI-X9.31]|National Institute of Standards and Technology, NIST-Recommended<br>Random Number Generator Based on ANSI X9.31 Appendix A.2.4 Using<br>the 3-Key Triple DES and AES Algorithms, January 31, 2005.    <br><http://csrc.nist.gov/groups/STM/cavp/documents/rng/931rngext.pdf>|
|[ANSI-X9.62]|ANSI X9.62:2005<br>Public Key Cryptography for the Financial Services Industry, The Elliptic<br>Curve Digital Signature Algorithm (ECDSA)|
|[ANSI-X9.63]|American National Standard for Financial Services X9.63–2001<br>Public Key Cryptography for the Financial Services Industry<br>Key Agreement and Key Transport Using Elliptic Curve Cryptography|
|[Boyd-Mathuria-2003]|Protocols for Authentication and Key Establishment, Colin Boyd and Anish Mathuria, 2003|
|[BrainPool]|ECC Brainpool Standard Curves and Curve Generation v. 1.0 19.10.2005<br><http://www.teletrust.de/fileadmin/files/oid/oid_ECC-Brainpool-Standard-curves-V1.pdf>|
|[Breaking-TLS]|Lucky Thirteen: Breaking the TLS and DTLS Record Protocols<br>Nadhem J. AlFardan and Kenneth G. Paterson<br>Information Security Group, Royal Holloway, University of London,<br>Egham, Surrey TW20 0EX, UK, 6th February 2013|
|[BreakingXMLEnc]|How to Break XML Encryption, Tibor Jager, Juraj Somorovsky, 2011<br><http://www.nds.rub.de/media/nds/veroeffentlichungen/2011/10/22/HowToBreakXMLenc.pdf>|
|[BSI-PQC-2020]|Migration zu Post-Quanten-Kryptografie, Handlungsempfehlungen des BSI,<br>Stand: August 2020, <https://www.bsi.bund.de/SharedDocs/Downloads/DE/BSI/Krypto/Post-Quanten-Kryptografie.pdf?__blob=publicationFile&v=2> |
|[BSI-TR-02102-1]|BSI TR-02102-1 Technische Richtlinie „Kryptographische Verfahren:<br>Empfehlungen und Schlüssellängen“<br>Version 2018-02, Stand 29.05.2018<br><https://www.bsi.bund.de/DE/Publikationen/TechnischeRichtlinien/tr02102/index_htm.html>|
|[BSI-TR-02102-2]|BSI TR-02102-3 Technische Richtlinie „Kryptographische Verfahren:<br>Empfehlungen und Schlüssellängen, Teil 2 – Verwendung von Transport Layer Security (TLS), Version 2018-01<br><https://www.bsi.bund.de/DE/Publikationen/TechnischeRichtlinien/tr02102/index_htm.html>|
|[BSI-TR-02102-3]|BSI TR-02102-3 Technische Richtlinie „Kryptographische Verfahren:<br>Empfehlungen und Schlüssellängen, Teil 3 – Verwendung von Internet<br>Protocol Security (IPsec) und Internet Key Exchange (IKEv2)“<br>Version 2018-01<br><https://www.bsi.bund.de/DE/Publikationen/TechnischeRichtlinien/tr02102/index_htm.html>|
|[BSI-TR-03111]|Technical Guideline BSI TR-03111<br>Elliptic Curve Cryptography, Version 2.10, Date: 2018-06-01<br><https://www.bsi.bund.de/DE/Publikationen/TechnischeRichtlinien/tr03111/index_htm.html>   |
|[BSI-TR-03116-1]|Technische Richtlinie BSI TR-03116-1 Kryptographische Vorgaben für<br>Projekte der Bundesregierung, Version: 3.20,<br>Fassung September 2018, 21.09.2018<br><https://www.bsi.bund.de/DE/Publikationen/TechnischeRichtlinien/tr03116/index_htm.html>|
|[CM-2014]|20 Years of SSL/TLS Research, An Analysis of the Internet’s Security<br>Foundation, Christopher Meyer, 9. February 2014<br><http://www-brs.ub.ruhr-uni-bochum.de/netahtml/HSS/Diss/MeyerChristopher/diss.pdf>|
|[eIDAS]|Verordnung (EU) Nr. 910/2014 des europäischen Parlaments und des<br>Rates vom 23. Juli 2014 über elektronische Identifizierung und<br>Vertrauensdienste für elektronische Transaktionen im Binnenmarkt<br>und zur Aufhebung der Richtlinie 1999/93/EG|
|[ecma-262]|JSON Standard <https://www.ecma-international.org/publications/standards/Ecma-262.htm > |
|[EN-14890-1]|DIN EN 14890-1:2008<br>Application Interface for smart cards used as Secure Signature<br>Creation Devices - Part 1: Basic services|
|[ENISA-PQC-2021]|Post-Quantum Cryptography: Current state and quantum mitigation, European Union Agency for Cybersecurity (ENISA), May 2021, <https://www.enisa.europa.eu/publications/post-quantum-cryptography-current-state-and-quantum-mitigation> |
|[ETSI-CAdES]|ETSI TS 101 733 V1.7.4 (2008-07), Electronic Signatures and<br>Infrastructures (ESI); CMS Advanced Electronic Signatures (CAdES)|
|[ETSI\_TS\_102\_231\_v3.1.2]|ETSI (Dezember 2009): ETSI Technical Specification TS 102 231 (‘Provision of harmonized Trust Service Provider (TSP) status information’) – Version 3.1.2|
|[ETSI-XAdES]|ETSI TS 101 903 V1.4.2 (2010-12), Electronic Signatures and<br>Infrastructures (ESI); XML Advanced Electronic Signatures (XAdES)|
|[FIPS-180-4]|Federal Information, Processing Standards Publication 180-4,<br>Secure Hash Standard (SHS), March 2012<br><http://csrc.nist.gov/publications/fips/fips180-4/fips180-4.pdf>|
|[FIPS-186-2+CN1]|FIPS 186-2 - National Institute of Standards and Technology,<br>Digital Signature Standard (DSS), Federal Information Processing<br>Standards Publication 186-2, January 27, 2000 – Appendix 3.1<br>unter der Beachtung des Change Notice 1, vom 5. Oktober 2001<br><http://csrc.nist.gov/publications/fips/archive/fips186-2/fips186-2-change1.pdf>|
|[FIPS-197]|Federal Information Processing Standards Publication 197,<br>(FIPS–197), November 26, 2001, Announcing the<br>ADVANCED ENCRYPTION STANDARD (AES)<br><http://csrc.nist.gov/publications/fips/fips197/fips-197.pdf>|
|[FIPS-202]|NIST, FIPS PUB 202, SHA-3 Standard: Permutation-Based Hash and Extendable-Output Functions, 2015, <http://nvlpubs.nist.gov/nistpubs/fips/NIST.FIPS.202.pdf> |
|[IR-2014]|Bulletproof SSL and TLS: Understanding and deploying SSL/TLS<br>and PKI to secure servers and web applications, Ivan Ristić, 2014<br><https://www.feistyduck.com/books/bulletproof-ssl-and-tls/>|
|[ISO-11770]|ISO/IEC 11770: 1996, Information technology – Security techniques –<br>Key management, Part 3: Mechanisms using asymmetric techniques|
|[Ker-1883]|Auguste Kerckhoffs, "La cryptographie militaire", Journal des sciences<br>militaires, vol. IX, Seite 5–83, Jan. 1883, Seite 161–191, Feb. 1883.<br>siehe auch <http://www.petitcolas.net/fabien/kerckhoffs/>|
|[KS-2011]|W. Killmann, W. Schindler, „A proposal for: Functionality classes for<br>random number generators“, Version 2.0, September 2011<br>[https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Zertifierung/Interpretation /AIS31_Functionality_classes_for_random_numder_generators.pdf?__ blpb=publicationFile](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Zertifierung/Interpretation /AIS31_Functionality_classes_for_random_numder_generators.pdf?__ blpb=publicationFile)|
|[MK-2016]|The Million-Key Question – Investigating the Origins of RSA Public Keys,<br>Petr Svenda, Matus Nemec, Peter Sekan, Rudolf Kvasnovsky, David Formanek, David Komarek, Vashek Matyas, <br>The 25th USENIX Security Symposium (UsenixSec'2016)<br><https://crocs.fi.muni.cz/public/papers/usenix2016> |
|[NIST-PQC]|Post-Quantum Cryptography, National Institute of Standards and Technology (NIST), <br><https://csrc.nist.gov/projects/post-quantum-cryptography> |
|[NIST-SP-800-22]|A. Ruskin et al., A Statistical Test Suite for Random and Pseudorandom Number Generators for Cryptographic Applications, SP 800-22 Rev. 1a , 2010<br><https://csrc.nist.gov/publications/detail/sp/800-22/rev-1a/final> |
|[NIST-SP-800-38A]|NIST Special Publication 800-38A,<br>Recommendation for Block, Cipher Modes of Operation, Methods and<br>Techniques, Morris Dworkin, December 2001 Edition,<br><http://csrc.nist.gov/publications/nistpubs/800-38a/sp800-38a.pdf>|
|[NIST-SP-800-38B]|NIST Special Publication 800-38B,<br>Recommendation for Block Cipher Modes of Operation: The CMAC<br>Mode for Authentication, Morris Dworkin, May 2005 Edition,<br><http://csrc.nist.gov/publications/nistpubs/800-38B/SP_800-38B.pdf>|
|[NIST-SP-800-38D]|NIST Special Publication 800-38D,<br>Recommendation for Block Cipher Modes of Operation: Galois/Counter<br>Mode (GCM) and GMAC, Morris Dworkin, November, 2007|
|[NIST-SP-800-56-A]|NIST Special Publication 800-56A<br>Recommendation for Pair-Wise Key Establishment Schemes Using<br>Discrete Logarithm Cryptography,  <br>April 2018<br><https://csrc.nist.gov/publications/detail/sp/800-56a/rev-3/final> |
|[NIST-SP-800-56-B]|NIST Special Publication 800-56B<br>Recommendation for Pair-Wise Key Establishment Schemes Using Integer Factorization Cryptography, August 2009|
|[NIST-SP-800-56C]|NIST Special Publication 800-56C<br>Recommendation for Key Derivation through Extraction-then-Expansion,<br>November 2011|
|[NIST-SP-800-108]|NIST Special Publication 800-108<br>Recommendation for Key Derivation Using Pseudorandom Functions,<br>October 2009|
|[NK-PP]|Common Criteria Schutzprofil (Protection Profile)<br>Schutzprofil 1:  Anforderungen an den Netzkonnektor, BSI-CC-PP-0097|
|[Oorschot-Wiener-<br>1996]|On Diffie-Hellman Key Agreement with Short Exponents, Paul C. van Oorschot, Michael J Weiner, Eurocrypt’ 96|
|[Padding-Oracle-<br>2005]|Padding Oracle Attacks on CBC-mode Encryption with Secret and<br>Random IVs<br>Arnold K. L. Yau, Kenneth G. Paterson and Chris J. Mitchell, FSE 2005<br><http://www.isg.rhul.ac.uk/~kp/secretIV.pdf>|
|[PAdES-3]|ETSI TS 102 778-3 V1.2.1,<br>PDF Advanced Electronic Signature Profiles; Part 3: PAdES Enhanced –<br>PAdES-BES and PAdES-EPES Profiles<br>Technical Specification, 2010|
|[PDF/A-2]|ISO 19005-2:2011 – Document management – Electronic document file<br>format for long-term preservation – Part 2: Use of ISO 32000-1 (PDF/A-2)|
|[PKCS#1]|vgl. [RFC-8017]|
|[PP-0082]|Common Criteria Protection Profile, Card Operating System Generation<br>2 (PP COS G2), BSI-CC-PP-0082-V2, Version 1.9, 18th November 2014|
|[RFC-2119]|RFC 2119 (März 1997): Key words for use in RFCs to Indicate Requirement<br>Levels, S. Bradner,<br><http://tools.ietf.org/html/rfc2119>|
|[RFC-2590]|RFC 2590 (June 1999): X.509 Internet Public Key Infrastructure Online<br>Certificate Status Protocol - OCSP<br><https://tools.ietf.org/html/rfc2560><br>(Obsoleted by [RFC-6960])|
|[RFC-2986]|RFC 2986 (November 2000): PKCS #10: Certification Request Syntax Specification, Version 1.7<br><https://tools.ietf.org/html/rfc2986> |
|[RFC-3279]|RFC 3279 (April 2002): Algorithms and Identifiers for the Internet X.509<br>Public Key Infrastructure Certificate and Certificate Revocation List (CRL)<br>Profile<br><https://tools.ietf.org/html/rfc3279>|
|[RFC-3526]|RFC 3526 (Mai 2003: More Modular Exponential (MODP) Diffie-Hellman<br>groups for Internet Key Exchange (IKE)<br><http://tools.ietf.org/html/rfc3526>|
|[RFC-4051]|Additional XML Security Uniform Resource Identifiers (URIs), April 2005<br><https://tools.ietf.org/html/rfc4051>|
|[RFC-4635]|RFC 4635 (August 2006): HMAC SHA TSIG Algorithm Identifiers<br><http://tools.ietf.org/html/rfc4635>|
|[RFC-5077]|Transport Layer Security (TLS) Session Resumption without Server-Side<br>State, January 2008, <https://tools.ietf.org/html/rfc5077>|
|[RFC-5084]|RFC 5084: Using AES-CCM and AES-GCM Authenticated Encryption in the<br>Cryptographic Message Syntax (CMS), November 2007<br><https://tools.ietf.org/html/rfc5084>|
|[RFC-5091]|RFC 5091: Identity-Based Cryptography Standard (IBCS) #1: Supersingular Curve Implementations of the BF and BB1 Cryptosystems, X. Boyen, L. Martin, December 2007<br><https://tools.ietf.org/html/rfc5091> |
|[RFC-5246]|The Transport Layer Security (TLS) Protocol Version 1.2, August 2008,<br><https://tools.ietf.org/html/rfc5246>|
|[RFC-5280]|RFC 5280: Internet X.509 Public Key Infrastructure Certificate and<br>Certificate Revocation List (CRL) Profile, Mai 2008<br><https://tools.ietf.org/html/rfc5280>|
|[RFC-5480]|RFC 5480 (March 2009): Elliptic Curve Cryptography Subject Public<br>Key Information, <https://tools.ietf.org/html/rfc5480>|
|[RFC-5639]|RFC 5639 (March 2010): Elliptic Curve Cryptography (ECC) Brainpool<br>Standard Curves and Curve Generation, <http://www.ietf.org/rfc/rfc5639.txt>|
|[RFC-5652]|RFC 5652 (September 2009): Cryptographic Message Syntax (CMS),<br>R. Housley, <http://tools.ietf.org/html/rfc5652> |
|[RFC-5702]|RFC 5702 (October 2009): Use of SHA-2 Algorithms with RSA in DNSKEY<br>and RRSIG Resource Records for DNSSEC, <http://tools.ietf.org/html/rfc5702>|
|[RFC-5746]|RFC 5746: Transport Layer Security (TLS) Renegotiation Indication Extension,<br>February 2010, <https://tools.ietf.org/html/rfc5746>|
|[RFC-5753]|RFC 5753: Use of Elliptic Curve Cryptography (ECC) Algorithms in Cryptographic Message Syntax (CMS), January 2010,  <https://tools.ietf.org/html/rfc5753> |
|[RFC-5869]|HMAC-based Extract-and-Expand Key Derivation Function (HKDF), May 2010,  <https://tools.ietf.org/html/rfc5869> |
|[RFC-5903]|Elliptic Curve Groups modulo a Prime (ECP Groups) for IKE and IKEv2, June 2010,  <https://tools.ietf.org/html/rfc5903> |
|[RFC-6090]|RFC 6090: Fundamental Elliptic Curve Cryptography Algorithms, February 2011,  <https://tools.ietf.org/html/rfc6090> |
|[RFC-6954]|Using the Elliptic Curve Cryptography (ECC) Brainpool Curves for the Internet Key Exchange Protocol Version 2 (IKEv2),July 2013,  <https://tools.ietf.org/html/rfc6954> |
|[RFC-6960]|RFC 6960 (June 2013): X.509 Internet Public Key Infrastructure Online<br>Certificate Status Protocol – OCSP, <https://tools.ietf.org/html/rfc6960>|
|[RFC-7027]|RFC 7027: (October 2013) Elliptic Curve Cryptography (ECC) Brainpool<br>Curves  for Transport Layer Security (TLS), <https://tools.ietf.org/html/rfc7027>|
|[RFC-7296]|RFC 7296 (October 2014): Internet Key Exchange Protocol Version 2<br>(IKEv2), <https://tools.ietf.org/html/rfc7296>|
|[RFC-7427]|RFC 7427 (January 2015): Signature Authentication in the Internet Key<br>Exchange Version 2 (IKEv2), <https://tools.ietf.org/html/rfc7427>|
|[RFC-8017],<br>[PKCS#1]|"Public-Key Cryptography Standards (PKCS) #1: RSA Cryptography<br>Specifications Version 2.2",  November 2016<br><https://tools.ietf.org/html/rfc8017> |
|[RFC-931]|RFC 6931: Additional XML Security Uniform Resource Identifiers (URIs),<br>Donald Eastlake, April 2013, <https://tools.ietf.org/html/rfc6931>|
|[RFC-9155]|RFC 9155: Deprecating MD5 and SHA-1 Signature Hashes in TLS 1.2 and DTLS 1.2, December 2021, <https://datatracker.ietf.org/doc/rfc9155/ > |
|[ROCA-2017]|The Return of Coppersmith's Attack: Practical Factorization of Widely Used RSA Moduli,<br>Matus Nemec, Marek Sys, Petr Svenda, Dusan Klinec, Vashek Matyas<br>24th ACM Conference on Computer and Communications Security (CCS'2017)<br><https://crocs.fi.muni.cz/public/papers/rsa_ccs17> |
|[SEC1-2009]|Standards for Efficient Cryptography, SEC 1: Elliptic Curve Cryptography, Certicom Research, Contact: Daniel R. L. Brown (dbrown@certicom.com), May 21, 2009, Version 2.0<br><https://www.secg.org/sec1-v2.pdf> |
|[SDH-2016]|Measuring the Security Harm of TLS Crypto Shortcuts, Drew Springall, Zakir Durumeic, J. Alex Halderman, November 2016, <https://jhalderm.com/pub/papers/forward-secrecy-imc16.pdf> |
|[SOG-IS-2020]|SOG-IS Crypto Evaluation Scheme Agreed Cryptographic Mechanisms, Version 1.2, January 2020<br><https://www.sogis.eu/documents/cc/crypto/SOGIS-Agreed-Cryptographic-Mechanisms-1.2.pdf> |
|[TLS-Attacks]|Lessons Learned From Previous SSL/TLS Attacks - A Brief Chronology<br>Of Attacks And Weaknesses, Christopher Meyer und Jörg Schwenk,<br>31. Januar 2013, <http://eprint.iacr.org/2013/049>|
|[TLS-CC-2021]|Hybrid Post-Quantum Key Encapsulation Methods (PQ KEM) for Transport Layer Security 1.2 (TLS), September 2021, <https://datatracker.ietf.org/doc/draft-campagna-tls-bike-sike-hybrid/> |
|[XMLCan\_V1.0]|Exclusive XML Canonicalization, Version 1.0, W3C Recommendation<br>18 July 2002, <http://www.w3.org/TR/xml-exc-c14n/>|
|[XMLDSig]|XML Signature Syntax and Processing Version 1.1, W3C<br>Recommendation 11 April 2013<br><https://www.w3.org/TR/xmldsig-core1/>  |
|[XMLDSig-Draft]|XML Signature Syntax and Processing Version 2.0, W3C Editor's Draft<br>04 February 2014, <http://www.w3.org/2008/xmlsec/Drafts/xmldsig-core-20/>|
|[XMLDSig-RSA-<br>PSS]|RSA-PSS in XMLDSig, 25/26 September 2007, Konrad Lanz,<br>Dieter Bratko, Peter Lipp,<br><http://www.w3.org/2007/xmlsec/ws/papers/08-lanz-iaik/>|
|[XMLEnc]|XML Encryption Syntax and Processing, W3C Recommendation<br>10 December 2002, <http://www.w3.org/TR/xmlenc-core/>|
|[XMLEnc-CM]|Technical Analysis of Countermeasures against Attack on XML<br>Encryption - or - Just Another Motivation for Authenticated<br>Encryption.<br>Juraj Somorovsky, Jörg Schwenk. 2011<br><http://www.w3.org/2008/xmlsec/papers/xmlEncCountermeasuresW3C.pdf>|
|[XMLEnc-1.1]|XML Encryption Syntax and Processing, W3C Recommendation<br>11 April 2013, <http://www.w3.org/TR/xmlenc-core1/>|
|[XSpRES]|XML Spoofing Resistant Electronic Signature (XSpRES) --<br>Sichere Implementierung für XML-Signaturen<br>Bundesamt für Sicherheit in der Informationstechnik 2012<br><https://www.bsi.bund.de/SharedDocs/Downloads/DE/BSI/SOA/XSpRESS.pfd?__blob=publicationFile> |
|[XSW-Attack]|On Breaking SAML: Be Whoever You Want to Be<br>Juraj Somorovsky, Andreas Mayer, Jörg Schwenk, Marco Kampmann,<br>Meiko Jensen, Usenix 2012<br><http://www.nds.rub.de/media/nds/veroeffentlichungen/2012/08/03/BreakingSAML.pdf>|
|[Vaudenay-2002]|Security Flaws Induced by CBC Padding: Applications to SSL, IPsec,<br>WTLS … , Serge Vaudenay, Eurocrypt 2002, LNCS 2332/2002, 535-545<br><https://www.iacr.org/cryptodb/data/paper.php?pubkey=2850>|

