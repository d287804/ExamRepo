# ExamRepo

Hierin staat informatie zoals hoe je projectstructuur het beste kan indelen en dingen zoals handige links.

# Project structure

Map structure for C# MVC:

- Solution:
    - Project:
        - Controls:
            - Controls:
            - Forms:
            - UserControl:
        - Data:
            - Context:
            - DAL:
            - Models:
        - Helpers:
            - StringHelper:
            - DateTimeHelper:
        - Overige:

Controls folder:
    De control folder is de folder voor alle controls zoals forms en usercontrols.
    Dit is de PresentationLayer van je applicatie.

Data folder:
    De control folder is de folder voor alles wat met de database te maken heeft.
    Dit is de Data Acces Layer van je applicatie.

Helpers folder:
    De helper folder is de folder voor alle helper functies. Functies zoals Encrypt en Decrypt. Functies die een string nodig hebben en nog belangrijker, functies die een string returnen.

Overige:
    De overige items staan niet in een folder. Files zoals de program class en settings.json. Deze files kunnen niet gesorteerd, omdat er vaak maar een van is en de type komt maar een keer voor.

# Connection

Connection strings:
    Stel je weet niet meer hoe je een connection string moet maken, ga dan naar deze website: https://www.connectionstrings.com

Hierin de meest gebruikte connections in C#:

Enitity Framework:

- MySQL:
    protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
    {
        optionsBuilder.UseMySql("server=localhost;user=root;password=;database=nasa_apiuser;port=3306", ServerVersion.Parse("5.7.33 mysql"));
    }

- SQLExpress:
    protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
    {
        optionsBuilder.UseSqlServer("Data Source=SCORPIGGYLAPTOP\\SQLEXPRESS;Initial Catalog=stagebureau;Integrated Security=True;TrustServerCertificate=True;");
    }

Als je SQLExpress is het belangrijk dat je de TrustServerCertificate erbij zet en op true zet, anders heb je geen rechten op de database en kan hij geen connectie maken. Dus vergeet die niet!

LINQ to SQL:
    Het beste is om LINQ to SQL te vermijden, want dit is outdated. Dit wordt al sinds .net 3.5 niet meer ondersteund. Dus als je een core app wilt maken, kan je beter ef gebruiken, want LINQ to SQL gaat niet werken. Maar als je .net wilt gebruiken, wat alleen gebruikt wordt voor Legacy applications, kan je LINQ to SQL nog wel gebruiken. Als je de tabellen wilt gebruiken in je code, maak je een dbml file aan. Daarna verbindt je de juiste database vanuit de server explorer die te vinden is via het view knopje(in visual studio). Daarna sleep je de tabellen in het dbml class en daarna kan je de tabellen gebruiken als objecten.

# Conventions

Als je de C# conventies niet meer weet, kan je het vinden in deze link: https://github.com/ktaranov/naming-convention/blob/master/C%23%20Coding%20Standards%20and%20Naming%20Conventions.md

Verder is het ook belangrijk om de coventie DRY(don't repeat yourself) aan te houden. Zo blijft de code beter leesbaar en is het makkelijker te onderhouden. Dit is niet alleen in C# en native te maken. Dit is een universele conventie in het programmeren en software engineering.

Je mag natuurlijk je eigen conventies bedenken, maar toch raad ik aan om de universele conventies van C# te gebruiken. Die zijn vaak bekend bij andere programmeurs en is de kans dat de conventies toegepast worden groter.

# Commenting

Het gebruiken van comments is belangrijk. Zo kan je duidelijk aangeven wat een stukje code doet. Zo weet je collega's wat je gedaan hebt en het kan als handige reminder gebruikt worden als je bent vergeten wat je gedaan hebt. Dus het wordt aangeraden je code te commenten. Verder kan je ook regions gebruiken. Zo kan je functies en variabelen van het hetzelde type bij elkaar zetten. Zo maak je een region aan:
- Je typt in #region
- Dan spatie en schrijf je de naam van je region op
- En daarna, onderaan de items die je in je region wilt includen, typ je #endregion zodat de region afgesloten wordt

Ook is het gebruik van summaries heel handig. Met een summary kan je extra informatie meegeven aan een variabele en/of functie. Die informatie kan je zien in de tooltip, de tooltip krijg je te zien als je over een item hovert. Zo maak je een summary aan:
- In visual studio typ je drie keer een slash in
- Als je dat gedaan hebt, wordt er automatisch een summary voor je gemaakt
- Daarna kan je tussen de summary informatie meegeven over de summary
- Onder de summary kan je params meegeven voor functies en variabelen
- Tussen de >< pijltjes van param kan je dan informatie geven over dat param item
- En als laatste hover je over het item van je de param voor gemaakt hebt en kan je zien dat je tekst die je hebt ingevuld er staat

Mijn tip is om je summary pas aan te maken als je klaar bent met dat bestand, wordt dan maak de params automatisch aan en hoe je alleen maar nog de extra informatie in te vullen.

# Other repositories

BarrocItens: https://github.com/Smydro/Barroc-Intens
Landbouwmonitor: https://github.com/lucianoKa/landbouwkasMonitor