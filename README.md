# Aplicatie-embedded-folosind-sistemul-de-operare-freeRTOS-si-kit-ul-de-dezvoltare-F401RE
Intrarea analogică este achiziționată la fiecare X ms în Taskul T1.
• Taskul T2 va comanda ledurile astfel:
o L1 aprins, L2 și L3 stinse dacă valoarea citită este < 512
o L1 aprins, L2 aprins și L3 stins dacă valoarea citită este >= 512 și < 768
o Toate ledurile aprinse dacă valoarea citită >= 768
• Taskul T2 se va executa la fiecare Y ms. Unde Y > X.
• Taskul T3 va primi valorile achiziționate și le va trimite către interfața serială
respectând următorul format: ADC_read_value: val, unde val este valoarea citită de pe
intrarea analogică.
• Pe lângă modul automat de comandă, aplicația va pune la dispoziție și un mod manual
de comandă folosind un al doilea potențiometru.
• Schimbarea modului (automat / manual) se va face folosind un switch conectat la un
pin cu întrerupere externă.
• În modul manual de funcționare, T1, T2 și T3 sunt suspendate și se va activa T4 care va
comanda ledurile și, de asemenea, va trimite către portul serial: mod manual.
• Când se comută din manual în automat, T4 este suspendat și T1,T2, T3 sunt activate.
• Comunicarea între taskuri se va face folosind cozi (queue).
