## Testrapport  Säkerhet


**Testare:** *Maria Olsson*

**Datum:** *2023-05-12 - 2023-05-12*

### Testresultat

| Krav     | Testfall     | Resultat    | Kommentar |
| -------- | ------------ | ----------- | --------- |
| *SH1.1* | TC *1.1* | Fail |OpenAI:s api validerar mängd indata för att förhindra för stora mängder. |
| *SH1.2* | TC *1.2* | Fail |Finns ingen skriven kod som validerar indata för att förhindra kod som input      |
| *SH2* | TC *2* | Pass |Implementering av paketet express-rate-limit som begränsar förfrågningar till 100st/15 min.           |
| *SH3* | TC *3* | *Fail* |Använder inte OpenAIs moderation. 

### Bilagor
TC1.1 Error när mer än 4097 tokens skickas in från klienten
![[Pasted image 20230516104856.png]]

Behöver ladda om sidan så att contexten återställs till noll
![[Pasted image 20230516105647.png]]

### Kommentar
TC1.1 Skulle vara bra med kontroll av mängd indata, som ligger under OpenAIs cutoff värde för att förhindra att användaren behöver göra en refresh och börja om. 

TC3.0 Att använda OpenAIs moderation för validering blir aktuellt vid driftsättning och publik användning. Applikationen är nu ett proof of concept endast. |
