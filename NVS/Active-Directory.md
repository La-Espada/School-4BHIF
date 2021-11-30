# Active Directory
---
- **Was ist ein Active Directory?**
  Der **Active Directory** wurde von Microsoft entwickelt, damit die Verwaltung von Benutzern und Computern vereinfacht wird, indem die Benutzer- und Computerinformatione auf einem einzigen Verzeichnis gespeichert wird.
  
  Ein Beispiel dafür wäre unser Schulnetzwerksystem.
  Jeder Lehrer und Schüler kann sich mit denselben Daten auf Moodle, Mail, Spengerhub,Schul-Wlan usw. anmelden. Dies ist durch dem Active Directory möglich. 
  
### Wie funktioniert AD?
 1. Datenbank wird erstellt
     - Daten der Benutzer und der Geräte werden in der DB eingespeichert
 2.  Multimaster replication
      - Wenn zum System noch ein Server hinzugefügt wird, wird die Datenbank vom anderen Server repliziert.
      - Ebenso werden Veränderungen der DB von den anderen Servern übernommen. 
 ### Domain Controller (DC)
  Der Domain Controller ist eine Active Directory mit einem Windows Server.
  
  **Services**, die ein Domain Controller verwendet bzw. verwenden kann:
   - **AD-DS**(domain service)
   - AD-CS (Certificate service)
   - AD-FS(Federation service)
   - AD-LDS(Lightweight Directory Services)
   - AD-RMS(Rights Management Services)
   
   Konfiguration eines Domain Controllers:
   - Installierung der Role mit AD-DS
   -  AD-DS braucht DNS 
         -  Damit der host weiß zu welchem Domain Controller er sich verbinden soll, wird ein DNS benötigt.
      
- Der Domainname besteht mindestens aus zwei Komponenten 
   Beispiel: 4bhif.local
- Organizational Units(OU)
     - Group Policies können in OU hinzugefügt werden
     - Geräte, Benutzer und Groups können OU sein 

- Sites
-physische Standorte Default Site: default-first site Jeder Domain Controller ist standardmäßig in der Default Site. Wenn es mehrere Sites gibt, dann wird zuerst innerhalb der Site repliziert (intersitereplication) und dann erst mit den anderen Sites. Host melden sich je nach der IP-Adresse bei dem richtigen Domain Controller. Die Domain Controller replizieren sich zwischen den Sites. Jedoch muss aufgepasst werden, dass nicht zu viel Bandbreite verbraucht wird. **Service Record**: zeigt an welche DNS-Server es gibt und welche davon LDAP und KERBEROS. Wenn ein Domain Controller ausfällt, wird dieser aus der Liste entfernt. Der Client findet den Domain Controller in der Site, indem er zu dem DNS-Server aus dem Service Record geht. **KCC**: versucht die DCs effizient wie möglich zu replizieren
- DFS
DFS Replikation: Ordner und Files werden auf mehren Domain Controller repliziert wird am häufigsten zwischen zwei oder mehreren Standorten verwendet, um auf wichtige Files zuzugreifen
- Wie erkennen die Clients wer der Domain Controller ist?
- SRV Record



