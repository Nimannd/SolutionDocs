# Zielsetzung
Was ist das Problem?
Kurzbeschreibung des Geschäfts- oder Technikproblems, das gelöst werden soll.

# Organisation
## Team
Wer ist im Team? Welche Rollen gibt es? Wer ist der Product Owner, Scrum Master, Entwickler, Tester, Architekt?

## Grobplan
Grober Projektplan. Phasen, Meilensteine, Abhängigkeiten, aktuell geplantes GoLive-Datum.
Gant mermaid
```mermaid
gantt
    title Projektplan
    dateFormat YYYY-MM-DD
    
    section Analyse
        Anforderungserhebung    :a1, 2023-01-01, 14d
        Anforderungsanalyse     :a2, after a1, 10d
    
    section Design
        Architekturentwurf      :d1, after a2, 15d
        Detaildesign            :d2, after d1, 20d
    
    section Implementierung
        Frontend-Entwicklung    :i1, after d2, 30d
        Backend-Entwicklung     :i2, after d2, 35d
        Integration             :i3, after i1, 10d
    
    section Test
        Unit Tests              :t1, after i2, 10d
        Integrationstests       :t2, after i3, 15d
        Systemtests             :t3, after t2, 10d
    
    section Deployment
        Vorbereitung Umgebung   :dep1, after t3, 5d
        Deployment              :dep2, after dep1, 3d
        Schulung                :dep3, after dep2, 7d
    
    section Abhängigkeiten
        Server-Bereitstellung   :ab1, 2023-02-15, 10d
        API-Freigabe            :ab2, 2023-03-01, 5d
        Lizenzierung            :ab3, 2023-04-15, 7d
    
    section Milestones
        Projektstart            :milestone, 2023-01-01, 0d
        Design abgeschlossen    :milestone, after d2, 0d
        UAT                     :milestone, after t3, 0d
        Go-Live                 :milestone, after dep3, 0d
```

Alternativ für einfachere Pläne oder etwas spezifischere Vorgehen geht auch ein Flow Chart
```mermaid
flowchart TD
    A[Projektstart] --> B[Anforderungsanalyse]
    B --> C[Design & Planung]
    C --> D[Entwicklung]
    D --> E[Test & Validierung]
    E --> F[Implementierung]
    F --> G[Projektabschluss]
    
    B --> H[Stakeholder-Meetings]
    H --> B
    
    C --> I[Design-Reviews]
    I --> C
    
    D --> J[Code-Reviews]
    J --> D
    
    E --> K[Fehlerbehebung]
    K --> D

```

Wann sind welche Ressourcen verfügbar, benötigt oder nicht verfügbar.

Wo und wie werden Arbeitspackete gemanaged?

# Kontext
Was ist der Kontext des Problems/der Lösung?

Idealerweise ein Kontext Diagramm mit folgenden Informationen:
Die Lösung ist als Blackbox repräsentiert. Wer benutzt die Lösung? Wer interagiert mit der Lösung? Welche Systeme sind beteiligt? 


```mermaid
    C4Context
      title System Context diagram for Internet Banking System
      Enterprise_Boundary(b0, "BankBoundary0") {
        Person(customerA, "Banking Customer A", "A customer of the bank, with personal bank accounts.")
        Person(customerB, "Banking Customer B")
        Person_Ext(customerC, "Banking Customer C", "desc")

        Person(customerD, "Banking Customer D", "A customer of the bank, <br/> with personal bank accounts.")

        System(SystemAA, "Internet Banking System", "Allows customers to view information about their bank accounts, and make payments.")

        Enterprise_Boundary(b1, "BankBoundary") {

          SystemDb_Ext(SystemE, "Mainframe Banking System", "Stores all of the core banking information about customers, accounts, transactions, etc.")

          System_Boundary(b2, "BankBoundary2") {
            System(SystemA, "Banking System A")
            System(SystemB, "Banking System B", "A system of the bank, with personal bank accounts. next line.")
          }

          System_Ext(SystemC, "E-mail system", "The internal Microsoft Exchange e-mail system.")
          SystemDb(SystemD, "Banking System D Database", "A system of the bank, with personal bank accounts.")

          Boundary(b3, "BankBoundary3", "boundary") {
            SystemQueue(SystemF, "Banking System F Queue", "A system of the bank.")
            SystemQueue_Ext(SystemG, "Banking System G Queue", "A system of the bank, with personal bank accounts.")
          }
        }
      }

      BiRel(customerA, SystemAA, "Uses")
      BiRel(SystemAA, SystemE, "Uses")
      Rel(SystemAA, SystemC, "Sends e-mails", "SMTP")
      Rel(SystemC, customerA, "Sends e-mails to")

      UpdateElementStyle(customerA, $fontColor="red", $bgColor="grey", $borderColor="red")
      UpdateRelStyle(customerA, SystemAA, $textColor="blue", $lineColor="blue", $offsetX="5")
      UpdateRelStyle(SystemAA, SystemE, $textColor="blue", $lineColor="blue", $offsetY="-10")
      UpdateRelStyle(SystemAA, SystemC, $textColor="blue", $lineColor="blue", $offsetY="-40", $offsetX="-50")
      UpdateRelStyle(SystemC, customerA, $textColor="red", $lineColor="red", $offsetX="-50", $offsetY="20")

      UpdateLayoutConfig($c4ShapeInRow="3", $c4BoundaryInRow="1")



```

# Lösungsstrategie
Kurze Beschreibung der Lösungsansätze. Mit welchen Ansätzen soll das Problem gelöst werden?


## Lösungsansatz 1



# Architektur
## Komponentensicht

## Deploymentsicht

## Verhaltenssicht

## Datenmodell
