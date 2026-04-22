Logg – Azure (Nettside hosting setup)

Dato: I dag
Prosjekt: Oppsett av Azure Storage for nettsidehosting

1. Opprettelse av Storage Account

Startet prosessen med å lage en Azure Storage Account.
Valgte følgende innstillinger:

Storage type: Azure Blob Storage
Performance: Standard
Redundancy: LRS
Primary workload: Other
2. Første problem (validering feilet)

Fikk feilmeldingen “Validation failed” ved forsøk på å opprette ressursen.
Gikk tilbake for å undersøke konfigurasjonen.

3. Feilsøking

Sjekket “View error details” og fant at feilen var knyttet til Azure policy.
Feilen indikerte at abonnementet har begrensninger for hvilke regioner som kan brukes.

4. Forsøk på å løse region-problem

Testet flere regioner:

North Europe (feilet)
West Europe (feilet)
Norway East (feilet)
5. Analyse av problem

Feilmeldingen “RequestDisallowedByAzure” viser at abonnementet kun tillater bestemte regioner.
Problemet skyldes ikke feil i oppsett, men policybegrensning i Azure-kontoen.

6. Videre tiltak

Vurderte følgende løsninger:

Bruke samme region som resource group
Opprette ny resource group i en tillatt region
Identifisere eksakt tillatt region via Azure policy
7. Skjermbilder

Skjermbilde 1: Oppsett av Storage Account

<img width="1888" height="790" alt="Skjermbilde 2026-04-22 110856" src="https://github.com/user-attachments/assets/39797e78-c47f-463e-869d-0dc601be5ec4" />


Skjermbilde 2: Feilmelding ved validering
<img width="1864" height="796" alt="Skjermbilde 2026-04-22 110821" src="https://github.com/user-attachments/assets/344284d8-568d-4014-ac9d-7ad0ae6b6b3b" />
Utforkset web apps
<img width="1898" height="1011" alt="Skjermbilde 2026-04-22 092128" src="https://github.com/user-attachments/assets/f5f8796e-7c06-485c-b150-0b8c7b85cee1" />


Skjermbilde 3: Error details (RequestDisallowedByAzure)
<img width="858" height="699" alt="Skjermbilde 2026-04-22 111207" src="https://github.com/user-attachments/assets/72e193a3-e6c9-4a2f-ad24-b9eb7b0aed5f" />
