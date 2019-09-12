# VCS

Clasa Main este folosita drept entry point in tema.
Va primi in linia de comanda fisiere de intrare/iesire.

IDGenerator este folosit pentru a genera id-uri unice pentru fisiere,
directoare si commituri.
Checkerul testeaza id-urile commiturilor.

OperationParser are rolul de a parsa o linie fisierul de intrare si de a chema
OperationFactory pentru a crea operatiile specifice.
Atat OperationParser, cat si OperationFactory trebuie sa fie completate cu 
metodele de parsare/creare specifice operatiilor de vcs.

Toate mesajele de eroare necesare acestei aplicatii sunt definite in ErrorCodeManager.

Clasa Vcs contine un activeSnapshot. El este, de fapt, instanta curenta de
filesystem pe care se ruleaza comenzile de filesystem. Aceasta poate fi
schimbata in momentul in care dam rollback, dam checkout si in alte situatii,
in functie de implementarea voastra.

How to use it:
Checkerul se ruleaza prin comanda:
./tema-checker-local.sh

Pentru a testa doar operatiile de vcs:
./tema-checker-local.sh vcs

Pentru a testa doar operatiile de fs:
./tema-checker-local.sh fs

In folderul checker exista 2 fisiere care descriu ce operatii se ruleaza per fiecare test:
./checker/VCSTestsDescription
./checker/FSTestsDescription
