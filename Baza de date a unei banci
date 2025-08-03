--CREAREA TABELEI CLIENTI
CREATE TABLE Clienti(
 id_client number(6),
 Nume varchar2(20),
 Prenume varchar2(20),
 CNP number(13),
 Adresa varchar2(50),
 Numar_de_telefon number(10),
 Email varchar2(20)
);
ALTER TABLE Clienti
 ADD CONSTRAINT id_client_pk primary key(id_client);
describe Clienti;

--CREAREA TABELEI CONTURI
CREATE TABLE Conturi(
 id_cont number(6) primary key,
 id_client number(6),
 Tip_cont varchar2(15),
 Sold number(10),
 Data_deschiderii date,
 CONSTRAINT id_client_fk foreign key (id_client) REFERENCES Clienti (id_client)
);

--CREAREA TABELEI IMPRUMUTURI
CREATE TABLE Imprumuturi(
 id_imprumut number(6),
 id_client number(6),
 Suma_imprumutata number(10),
 Data_acordarii date,
 Data_scadenta date,
 Rata_dobanzii number(4),
 Suma_rambursata number(10),
 Status varchar2(15),
 CONSTRAINT id_imprumut_pk primary key (id_imprumut),
 CONSTRAINT fk_id_client foreign key (id_client) REFERENCES Clienti (id_client)
);
ALTER TABLE Imprumuturi
 DROP COLUMN Suma_rambursata;
 describe Imprumuturi;

--CREAREA TABELEI TRANZACTII
CREATE TABLE Tranzactii(
 id_tranzactie number(6) primary key,
 id_cont number(6),
 Tip_tranzactie varchar2(10),
 Suma number(10),
 Data_tranzactiei date,
 Descriere varchar2(30)
);
ALTER TABLE TRANZACTII
 DROP COLUMN TIP_TRANZACTIE;
ALTER TABLE TRANZACTII
 ADD CONSTRAINT id_cont_fk foreign key (id_cont) REFERENCES Conturi (id_cont);
describe Tranzactii;

--CREAREA TABELEI ORASE
CREATE TABLE Orase(
 id_oras number(6) primary key,
 nume_oras varchar2(15)
);
describe Orase;

--CREAREA TABELEI DEPARTAMENTE
CREATE TABLE Departamente(
 id_departament number(6) primary key,
 id_oras number(6),
 nume_departament varchar2(50)
);
ALTER TABLE Departamente
 ADD CONSTRAINT id_oras_fk FOREIGN KEY (id_oras) REFERENCES Orase(id_oras);
 describe Departamente;

--CREAREA TABELEI ANGAJATI
CREATE TABLE Angajati(
 id_angajat number(6) primary key,
 id_departament number(6),
 id_manager number(6),
 Nume varchar2(20),
 Prenume varchar2(20),
 Salariu number(8),
 Data_angajarii date
);
ALTER TABLE ANGAJATI
 ADD CONSTRAINT id_departament_fk foreign key (id_departament) REFERENCES Departamente
(id_departament);
ALTER TABLE ANGAJATI
 ADD Varsta number(2);
ALTER TABLE ANGAJATI
 ADD CONSTRAINT restrictie_varsta CHECK (Varsta BETWEEN 18 AND 62);
 describe Angajati;

--CREAREA TABELEI SUCURSALE
CREATE TABLE Sucursale(
 id_sucursala number(6) primary key,
 id_oras number(6),
 Nume_sucursala varchar2(15),
 Adresa varchar2(40),
 CONSTRAINT fk_id_oras FOREIGN KEY (id_oras) REFERENCES Orase (id_oras)
);
ALTER TABLE Sucursale
 ADD CONSTRAINT fk_id_oras FOREIGN KEY (id_oras) REFERENCES Orase(id_oras);
DROP TABLE Sucursale;
CREATE TABLE Sucursale(
 id_sucursala number(6) primary key,
 id_oras number(6),
 Nume_sucursala varchar2(15),
 CONSTRAINT fk_id_oras FOREIGN KEY (id_oras) REFERENCES Orase (id_oras)
);
ALTER TABLE Sucursale
 ADD Adresa varchar2(40);
 describe Sucursale;

--POPULAREA TABELEI CLIENTI
INSERT INTO CLIENTI (id_client, Nume, Prenume, CNP, Adresa, Numar_de_telefon, Email)
VALUES (1, 'Lungu', 'Vanesa-Denisa', 6040105170041, 'Str. Ghioceilor', 0752884130, 'denisalungu434');
INSERT INTO CLIENTI (id_client, Nume, Prenume, CNP, Adresa, Numar_de_telefon, Email)
VALUES (2, 'Istrate', 'Andreea', 8530162842134, 'Str Batranetii', 0752884131, 'istrateandreea');
UPDATE CLIENTI SET Adresa='Str. Batranetii' WHERE ID_CLIENT=2;
UPDATE CLIENTI SET Prenume='Andreea-Alexandra' WHERE ID_CLIENT=2;
INSERT INTO CLIENTI (id_client, Nume, Prenume, CNP, Adresa, Numar_de_telefon, Email)
VALUES (3, 'Firan', 'Marian', 5926148294145, 'Str 18 Decembrie', 0752884132, 'firanmarian');
UPDATE CLIENTI SET Adresa='Str. 18 Decembrie' WHERE ID_CLIENT=3;
INSERT INTO CLIENTI (id_client, Nume, Prenume, CNP, Adresa, Numar_de_telefon, Email)
VALUES(4, 'Fluturu', 'Andreea', 6925174284718, 'Str Frumoasa', 0752884133, 'fluturuandreea');
UPDATE CLIENTI SET Adresa='Str. Frumoasa' WHERE ID_CLIENT=4;
INSERT INTO CLIENTI (id_client, Nume, Prenume, CNP, Adresa, Numar_de_telefon, Email)
VALUES(5, 'Fluturu', 'Patrisia', 7291752956247, 'Str Frumoasa', 0728519274, 'fluturupatrisia');
UPDATE CLIENTI SET Adresa='Str. Frumoasa' WHERE ID_CLIENT=5;
INSERT INTO CLIENTI (id_client, Nume, Prenume, CNP, Adresa, Numar_de_telefon, Email)
VALUES(6, 'Fuica', 'Andreea', 5195274915284, 'Str. Margeanului', 0751927539, 'fuicaandreea');
INSERT INTO CLIENTI (id_client, Nume, Prenume, CNP, Adresa, Numar_de_telefon, Email)
VALUES(7, 'Fuica', 'Diana', 8192548164294, 'Str Frunzei', 0715294629, 'fuicadiana');
UPDATE CLIENTI SET Adresa='Str. Frunzei' WHERE ID_CLIENT=7;
INSERT INTO CLIENTI (id_client, Nume, Prenume, CNP, Adresa, Numar_de_telefon, Email)
VALUES(8, 'Tudor', 'Razvan-Constantin', 5927149265172, 'Str. Salciei', 0724678123, 'tudorrazvan');
SELECT * FROM CLIENTI
ORDER BY ID_CLIENT;

--POPULAREA TABELEI CONTURI
INSERT INTO CONTURI (id_cont, id_client, Tip_cont, Sold, Data_deschiderii)
VALUES(10, 1, 'Economii', 12000, to_date('12.01.2022', 'dd.mm.yyyy'));
INSERT INTO CONTURI (id_cont, id_client, Tip_cont, Sold, Data_deschiderii)
VALUES(20, 2, 'Bursa', 900, to_date('17.11.2023', 'dd.mm.yyyy'));
INSERT INTO CONTURI (id_cont, id_client, Tip_cont, Sold, Data_deschiderii)
VALUES(30, 3, 'Salariu', 8200, to_date('19.05.2018', 'dd.mm.yyyy'));
INSERT INTO CONTURI (id_cont, id_client, Tip_cont, Sold, Data_deschiderii)
VALUES(40, 4, 'Economii', 4800, to_date('13.07.2020', 'dd.mm.yyyy'));
INSERT INTO CONTURI (id_cont, id_client, Tip_cont, Sold, Data_deschiderii)
VALUES(50, 5, 'Bursa', 730, to_date('20.01.2018', 'dd.mm.yyyy'));
INSERT INTO CONTURI (id_cont, id_client, Tip_cont, Sold, Data_deschiderii)
VALUES(60, 6, 'Economii', 2800, to_date('12.12.2023', 'dd.mm.yyyy'));
INSERT INTO CONTURI (id_cont, id_client, Tip_cont, Sold, Data_deschiderii)
VALUES(70, 7, 'Economii', 5200, to_date('05.03.2021', 'dd.mm.yyyy'));
INSERT INTO CONTURI (id_cont, id_client, Tip_cont, Sold, Data_deschiderii)
VALUES(80, 8, 'Salariu', 7300, to_date('25.10.2017', 'dd.mm.yyyy'));
SELECT * FROM CONTURI
ORDER BY ID_CLIENT;

--POPULAREA TABELEI IMPRUMUTURI
INSERT INTO IMPRUMUTURI (id_imprumut, id_client, Suma_imprumutata, Data_acordarii,
Data_scadenta, Rata_dobanzii, Status)
VALUES (100, 1, 5000, to_date('14.02.2023', 'dd.mm.yyyy'), to_date('14.02.2043', 'dd.mm.yyyy'), 7.5,
'Activ');
UPDATE IMPRUMUTURI SET RATA_DOBANZII=7 WHERE ID_CLIENT=1;
INSERT INTO IMPRUMUTURI (id_imprumut, id_client, Suma_imprumutata, Data_acordarii,
Data_scadenta, Rata_dobanzii, Status)
VALUES (300, 3, 30000, to_date('09.11.2021', 'dd.mm.yyyy'), to_date('09.11.2051', 'dd.mm.yyyy'), 8,
'Activ');
UPDATE IMPRUMUTURI SET RATA_DOBANZII=NULL WHERE ID_CLIENT=3;
INSERT INTO IMPRUMUTURI (id_imprumut, id_client, Suma_imprumutata, Data_acordarii,
Data_scadenta, Rata_dobanzii, Status)
VALUES (800, 8, 24000, to_date('20.05.2020', 'dd.mm.yyyy'), to_date('20.05.2048', 'dd.mm.yyyy'), 7,
'Activ');
SELECT * FROM IMPRUMUTURI
ORDER BY ID_CLIENT;

--POPULAREA TABELEI TRANZACTII
INSERT INTO TRANZACTII (id_tranzactie, id_cont, Suma, Data_tranzactiei, Descriere)
VALUES(1,10, 20, to_date('12.12.2023', 'dd.mm.yyyy'), 'Cumparaturi');
INSERT INTO TRANZACTII (id_tranzactie, id_cont, Suma, Data_tranzactiei, Descriere)
VALUES(2,10, 500, to_date('11.12.2023', 'dd.mm.yyyy'), 'Comanda online');
INSERT INTO TRANZACTII (id_tranzactie, id_cont, Suma, Data_tranzactiei, Descriere)
VALUES(3,10, 150, to_date('12.12.2023', 'dd.mm.yyyy'), 'Plata factura');
INSERT INTO TRANZACTII (id_tranzactie, id_cont, Suma, Data_tranzactiei, Descriere)
VALUES(4,30, 1500, to_date('20.11.2023', 'dd.mm.yyyy'), 'Chirie');
INSERT INTO TRANZACTII (id_tranzactie, id_cont, Suma, Data_tranzactiei, Descriere)
VALUES(5,30, 2000, to_date('01.12.2023', 'dd.mm.yyyy'), 'Rata credit');
INSERT INTO TRANZACTII (id_tranzactie, id_cont, Suma, Data_tranzactiei, Descriere)
VALUES(6,50, 300, to_date('08.12.2023', 'dd.mm.yyyy'), 'Transfer bancar');
INSERT INTO TRANZACTII (id_tranzactie, id_cont, Suma, Data_tranzactiei, Descriere)
VALUES(7,80, 1000, to_date('04.12.2023', 'dd.mm.yyyy'), 'Chirie');
INSERT INTO TRANZACTII (id_tranzactie, id_cont, Suma, Data_tranzactiei, Descriere)
VALUES(8,80, 500, to_date('15.05.2020', 'dd.mm.yyyy'), 'Transfer bancar');
INSERT INTO TRANZACTII (id_tranzactie, id_cont, Suma, Data_tranzactiei, Descriere)
VALUES(9,60, 86, to_date('12.12.2023', 'dd.mm.yyyy'), 'Cumparaturi');
INSERT INTO TRANZACTII (id_tranzactie, id_cont, Suma, Data_tranzactiei, Descriere)
VALUES(10,20, 300, to_date('10.10.2023', 'dd.mm.yyyy'), 'Facturi');
UPDATE TRANZACTII SET DESCRIERE='Plata factura' WHERE ID_TRANZACTIE=10;
INSERT INTO TRANZACTII (id_tranzactie, id_cont, Suma, Data_tranzactiei, Descriere)
VALUES(11,70, 330, to_date('05.06.2023', 'dd.mm.yyyy'), 'Comanda online');
SELECT * FROM TRANZACTII
ORDER BY ID_TRANZACTIE;

--POPULAREA TABELEI ORASE
INSERT INTO ORASE (id_oras, nume_oras)
VALUES (1, 'Bucuresti');
INSERT INTO ORASE (id_oras, nume_oras)
VALUES (2, 'Galati');
INSERT INTO ORASE (id_oras, nume_oras)
VALUES (3, 'Craiova');
SELECT * FROM ORASE
ORDER BY ID_ORAS;

--POPULAREA TABELEI DEPARTAMENTE
INSERT INTO DEPARTAMENTE(id_departament, id_oras, nume_departament)
VALUES (110, 1, 'FINANTE');
INSERT INTO DEPARTAMENTE(id_departament, id_oras, nume_departament)
VALUES (120, 1, 'MARKETING');
INSERT INTO DEPARTAMENTE(id_departament, id_oras, nume_departament)
VALUES (130, 1, 'IT');
INSERT INTO DEPARTAMENTE(id_departament, id_oras, nume_departament)
VALUES (140, 1, 'RESURSE UMANE');
INSERT INTO DEPARTAMENTE(id_departament, id_oras, nume_departament)
VALUES (210, 2, 'FINANTE');
INSERT INTO DEPARTAMENTE(id_departament, id_oras, nume_departament)
VALUES (220, 2, 'MARKETING');
INSERT INTO DEPARTAMENTE(id_departament, id_oras, nume_departament)
VALUES (230, 2, 'IT');
INSERT INTO DEPARTAMENTE(id_departament, id_oras, nume_departament)
VALUES (240, 2, 'RESURSE UMANE');
INSERT INTO DEPARTAMENTE(id_departament, id_oras, nume_departament)
VALUES (310, 3, 'FINANTE');
INSERT INTO DEPARTAMENTE(id_departament, id_oras, nume_departament)
VALUES (320, 3, 'MARKETING');
INSERT INTO DEPARTAMENTE(id_departament, id_oras, nume_departament)
VALUES (330, 3, 'IT');
INSERT INTO DEPARTAMENTE(id_departament, id_oras, nume_departament)
VALUES (340, 3, 'RESURSE UMANE');
SELECT * FROM DEPARTAMENTE
ORDER BY ID_DEPARTAMENT;

--POPULAREA TABELEI ANGAJATI
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Salariu,
Data_angajarii)
VALUES (1, 110, 100, 'Lungu', 'Dragos', 8000, to_date('11.02.2020', 'dd.mm.yyyy'));
UPDATE ANGAJATI SET VARSTA=24 WHERE ID_ANGAJAT=1;
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Salariu,
Data_angajarii)
VALUES (100, 110, NULL, 'Popescu', 'Ana', 7000, to_date('12.02.2018', 'dd.mm.yyyy'));
UPDATE ANGAJATI SET VARSTA=40 WHERE ID_ANGAJAT=100;
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(2, 120, 100, 'Ionescu', 'Mihai', 35, 9000, to_date('12.02.2018', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(3, 130, 1, 'Popa', 'Ioana',40, 7500, to_date('13.02.2010', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(4, 140, 1, 'Radu', 'Elena',41, 8200, to_date('14.02.2015', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(5, 210, 3, 'Dumitru', 'Andrei',40, 8500, to_date('15.02.2011', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(6, 220, 100, 'Stanescu', 'Maria',35, 7800, to_date('16.02.2011', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(7, 230, 2, 'Moldovan', 'Cristina',32, 9200, to_date('17.02.2013', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(8, 240, 100, 'Dinu', 'Alexandru',34, 8700, to_date('18.02.2014', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(9, 310, 5, 'Gheorghiu', 'Laura',33, 8000, to_date('19.02.2015', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(10, 320, 100, 'Antonescu', 'Robert',25, 9300, to_date('20.02.2020', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(11, 330, 5, 'Mihai', 'Andreea',23, 7600, to_date('21.02.2022', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(12, 340, 2, 'Georgescu', 'Alex',21, 8800, to_date('22.02.2023', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(13, 110, 4, 'Florescu', 'Diana',28, 9200, to_date('23.02.2018', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(14, 120, 100, 'Dobre', 'Gabriel',29, 7900, to_date('24.02.2017', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(15, 130, 12, 'Stanciu', 'Elena',38, 8700, to_date('25.02.2012', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(16, 140, 100, 'Ilie', 'Ana-Maria',45, 9400, to_date('26.02.2010', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(17, 210, 1, 'Balan', 'Ionut',42, 8100, to_date('27.02.2015', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(18, 220, 2, 'Cristea', 'Teodora',29, 8700, to_date('28.02.2018', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(19, 230, 5, 'Serban', 'Raluca',36, 8000, to_date('29.02.2016', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(20, 240, 12, 'Anton', 'Adrian',30, 9100, to_date('01.03.2016', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(21, 310, 100, 'Tudor', 'Madalina',49, 7800, to_date('02.03.2013', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(22, 320, 15, 'Costin', 'Sorin',50, 9300, to_date('03.03.2012', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(23, 330, 12, 'Gavrila', 'Catalina',55, 8600, to_date('04.03.2020', 'dd.mm.yyyy'));
INSERT INTO ANGAJATI (id_angajat, id_departament, id_manager, Nume, Prenume, Varsta, Salariu,
Data_angajarii)
VALUES(24, 340, 1, 'Mocanu', 'Alina',20, 8900, to_date('05.03.2023', 'dd.mm.yyyy'));
SELECT * FROM ANGAJATI
ORDER BY ID_ANGAJAT;

--POPULAREA TABELEI SUCURSALE
INSERT INTO SUCURSALE (id_sucursala, id_oras, Nume_sucursala)
VALUES(11,1,'BT CENTRU');
UPDATE SUCURSALE SET NUME_SUCURSALA='BT UNIRII' WHERE ID_SUCURSALA=11;
UPDATE SUCURSALE SET ADRESA='BLD UNIRII 25' WHERE ID_SUCURSALA=11;
INSERT INTO SUCURSALE (id_sucursala, id_oras, Nume_sucursala)
VALUES(12,1,'BT UNIVERSITATE');
UPDATE SUCURSALE SET ADRESA='BLD REGINA ELISABETA 16' WHERE ID_SUCURSALA=12;
INSERT INTO SUCURSALE (id_sucursala, id_oras, Nume_sucursala)
VALUES(13,1,'BT RAHOVA');
UPDATE SUCURSALE SET ADRESA='SOS ALEXANDRIEI 16' WHERE ID_SUCURSALA=13;
INSERT INTO SUCURSALE (id_sucursala, id_oras, Nume_sucursala)
VALUES(14,2,'BT BRAILEI');
UPDATE SUCURSALE SET ADRESA='STRADA BRAILEI 152' WHERE ID_SUCURSALA=14;
INSERT INTO SUCURSALE (id_sucursala, id_oras, Nume_sucursala)
VALUES(15,2,'BT MICRO 18');
UPDATE SUCURSALE SET ADRESA='STRADA BRAILEI 192' WHERE ID_SUCURSALA=15;
INSERT INTO SUCURSALE (id_sucursala, id_oras, Nume_sucursala)
VALUES(16,2,'BT MAZEPA');
UPDATE SUCURSALE SET ADRESA='STRADA BRAILEI 132' WHERE ID_SUCURSALA=16;
INSERT INTO SUCURSALE (id_sucursala, id_oras, Nume_sucursala)
VALUES(17,2,'BT MICRO 14');
UPDATE SUCURSALE SET ADRESA='STRADA BRAILEI 200' WHERE ID_SUCURSALA=17;
INSERT INTO SUCURSALE (id_sucursala, id_oras, Nume_sucursala)
VALUES(18,3,'BT ELECTROPTR');
UPDATE SUCURSALE SET ADRESA='STR. IMPARATUL TRAIAN 219' WHERE ID_SUCURSALA=18;
INSERT INTO SUCURSALE (id_sucursala, id_oras, Nume_sucursala)
VALUES(19,3,'BT CRAIOVITEI');
UPDATE SUCURSALE SET ADRESA='STRADA TUFANELE 1' WHERE ID_SUCURSALA=19;
INSERT INTO SUCURSALE (id_sucursala, id_oras, Nume_sucursala)
VALUES(20,3,'BT VALEA ROSIE');
UPDATE SUCURSALE SET NUME_SUCURSALA='BT VALEA FETII' WHERE ID_SUCURSALA=20;
UPDATE SUCURSALE SET ADRESA='STRADA CARACAL 95' WHERE ID_SUCURSALA=20;
DELETE FROM SUCURSALE WHERE ADRESA='STRADA BRAILEI 152';
SELECT * FROM SUCURSALE
ORDER BY ID_SUCURSALA;

INTEROGARI PENTRU TABELELE CREATE:
1) Creati un index pentru data angajarii si pe baza acestuia, afisati angajatii si data angajarii
pentru cei angajati in anul 2020.
CREATE INDEX anul_angajarii_idx
ON Angajati (TO_CHAR(data_angajarii, 'yyyy'));
SELECT id_angajat, nume, prenume, data_angajarii
FROM Angajati
WHERE TO_CHAR(data_angajarii, 'yyyy')='2020';

2) Creati un sinonim pentru tabela Angajati si pe baza acestuia, afisati numele, prenumele si id_ul
de angajat al subordonatilor angajatului cu id-ul 12, impreuna cu nivelul de subordonare.
CREATE SYNONYM ang
FOR Angajati;
SELECT id_angajat, id_manager, nume, prenume, LEVEL, SYS_CONNECT_BY_PATH(nume, '/')
FROM ang
CONNECT BY PRIOR id_angajat=id_manager
START WITH id_angajat=12;

3) Afisati numele, prenumele si salariul managerului principal.
SELECT nume, prenume, salariu
FROM ang
WHERE id_manager IS NULL;

4) Creati o tabela virtuala pe baza tabelei Clienti fara a i se putea face modificari si afisati
continutul acesteia.
CREATE VIEW Clienti_virtual
AS SELECT * FROM Clienti
WITH READ ONLY;
SELECT * FROM Clienti_virtual
ORDER BY id_client;

5) Afisati anagajatii ai caror salariu depaseste suma de 6000lei, dar si cei care au cel mult un
manager, fara cei care au fost angajati in anul 2018.
SELECT id_angajat, id_manager, nume, prenume, salariu, data_angajarii, COUNT(id_manager)
FROM Angajati
WHERE salariu>6000
GROUP BY id_angajat, id_manager, nume, prenume, salariu, data_angajarii
INTERSECT
SELECT id_angajat, id_manager, nume, prenume, salariu, data_angajarii, COUNT(id_manager)
FROM Angajati
GROUP BY id_angajat, id_manager, nume, prenume, salariu, data_angajarii
HAVING COUNT(id_manager)<2
MINUS
SELECT id_angajat, id_manager, nume, prenume, salariu, data_angajarii, COUNT(id_manager)
FROM Angajati
WHERE EXTRACT (YEAR FROM data_angajarii)=2018
GROUP BY id_angajat, id_manager, nume, prenume, salariu, data_angajarii;

6) Afisati clientii bancii care au cerut un imprumut, impreuna cu id_ul de cont al fiecaruia si suma
imprumutata, iar pentru fiecare, stabiliti tipul imprumutului, pe baza informatiilor urmatoare:
--Daca suma imprumutata este mai mica de 10000 lei, atunci creditul va fi pe termen scurt
--Daca suma imprumutata este intre 20000 si 80000 lei, atunci creditul va fi pe termen lung
--Daca suma imprumutata este mai mare de 80000 lei, atunci creditul nu exista
SELECT c.id_client,id_cont, id_imprumut, nume, prenume, suma_imprumutata,
CASE
WHEN suma_imprumutata<10000 THEN 'Credit pe termen scurt'
WHEN suma_imprumutata BETWEEN 20000 AND 80000 THEN 'Credit pe termen lung'
ELSE 'Nu exista un credit' END Tip_imprumut
FROM Conturi c, Imprumuturi i, Clienti cl
WHERE c.id_client=i.id_client AND c.id_client=cl.id_client;

7) Afisati clientii bancii care au cerut un imprumut, impreuna cu id_ul de cont si suma
imprumutata, iar pentru fiecare imprumut, stabiliti suma care trebuie rambursata.
SELECT c.id_client, id_cont, id_imprumut, nume, prenume,suma_imprumutata,
(suma_imprumutata+suma_imprumutata*NVL(rata_dobanzii,0)) suma_rambursata
FROM Conturi c, Imprumuturi i, Clienti cl
WHERE c.id_client=i.id_client AND c.id_client=cl.id_client;

8) Afisati angajatii bancii, iar pentru fiecare, stabiliti statulul pe baza vechimii, astfel:
--Cei angajati de mai putin sau exact 5 ani sunt juniori
--Cei angajati de 6-10 ani sunt seniori
--Cei angajati de peste 10 ani sunt experti
SELECT id_angajat, nume, prenume, data_angajarii,
CASE WHEN EXTRACT(YEAR FROM SYSDATE)-EXTRACT(YEAR FROM DATA_ANGAJARII)<=5 THEN 'JUNIOR'
 WHEN EXTRACT(YEAR FROM SYSDATE)-EXTRACT(YEAR FROM DATA_ANGAJARII) BETWEEN 6 AND 10
THEN 'SENIOR'
 ELSE 'EXPERT' END statut
FROM Angajati;

9) Afisati tranzactiile clientilor si modificati descrierea fiecareia astfel:
--Daca suma tranzactiei este 2000 lei, vor fi folositi pentru chirie
--Daca suma tranzactiei este 500 lei, vor fi folositi pentru facturi
--Daca suma tranzactiei este 86 lei, vor fi folositi pentru un transfer bancar
UPDATE TRANZACTII
SET Descriere=DECODE(Suma, 2000, 'Chirie', 500, 'Plata factura', 86, 'Transfer bancar', Descriere);
SELECT id_tranzactie, id_cont, suma, data_tranzactiei, descriere FROM Tranzactii;

10) Afisati clientii si conturile acestora si extrageti primele 3 litere din numele celor ale caror nume
incep cu litera F
SELECT c.id_client, id_cont, nume, prenume, SUBSTR(nume,1,3) Primele_3_litere
FROM Clienti cl, Conturi c
WHERE cl.id_client=c.id_client AND nume LIKE 'F%';

11) Afisati angajatii bancii care nu au fost angajatii in data de 15.02.2011 si 16.02.2011, suma totala a
salariilor lor si media salariilor.
SELECT id_angajat, nume, prenume,data_angajarii, salariu, SUM(salariu) OVER () suma_salariilor ,
ROUND(AVG(salariu) OVER (), 1) media_salariilor
FROM angajati
WHERE TO_DATE(data_angajarii, 'MM.DD.YYYY') != TO_DATE('02.15.2011', 'MM.DD.YYYY')
 AND TO_DATE(data_angajarii, 'MM.DD.YYYY') != TO_DATE('02.16.2011', 'MM.DD.YYYY')
GROUP BY id_angajat, nume, prenume, data_angajarii, salariu;
ORDER BY data_angajarii;

12) Clientul cu id-ul 6 si a inchis contul la banca, astfel, stergeti din baza de date clientului cu id-ul 6,
impreuna cu contul acestuia (deschis la data de 12.12.2023) si imprumutul sau, doar daca a fost
inregistrat si achitat.
ALTER TABLE Conturi
DISABLE CONSTRAINT id_client_fk;
ALTER TABLE Imprumuturi
DISABLE CONSTRAINT fk_id_client;
ALTER TABLE Tranzactii
DISABLE CONSTRAINT id_cont_fk;
DELETE FROM Conturi WHERE data_deschiderii=TO_DATE('12.12.2023', 'DD.MM.YYYY');
SELECT * FROM Conturi
ORDER BY id_client;
DELETE FROM Clienti WHERE id_client=6;
SELECT * FROM Clienti
ORDER BY id_client;
DELETE FROM Tranzactii WHERE id_cont=60;
SELECT * FROM Tranzactii
ORDER BY id_cont;
ALTER TABLE Conturi
ENABLE CONSTRAINT id_client_fk;
ALTER TABLE Imprumuturi
ENABLE CONSTRAINT fk_id_client;
ALTER TABLE Tranzactii
ENABLE CONSTRAINT id_cont_fk;

13) Afisati numele, prenumele, managerul fiecarui angajat si salariul angajatilor care au salariul mai
mare decat angajatul cu id-ul 9, impreuna cu cei care lucreaza in acelasi departament ca si angajatul cu
id-ul 3
SELECT id_angajat, nume, prenume, id_departament, salariu, id_manager
FROM angajati
WHERE salariu > (SELECT salariu FROM angajati WHERE id_angajat=9)
UNION
SELECT id_angajat, nume, prenume, id_departament, salariu, id_manager
FROM angajati
WHERE id_departament IN (SELECT id_departament FROM angajati WHERE id_angajat=3)
ORDER BY salariu;

14) O noua sucursala s-a deschis in orasul Buzau. Introduceti sucursala in tabela Sucursale, cat si orasul
in tabela Orase, deoarece pana in momentul de fata nu exista nicio sucursala in orasul Buzau.
INSERT INTO ORASE (id_oras, nume_oras)
VALUES (4, 'Buzau');
SELECT * FROM ORASE
ORDER BY ID_ORAS;
INSERT INTO SUCURSALE (id_sucursala, id_oras, Nume_sucursala, Adresa)
VALUES(21,4,'BT CENTRU', 'Bulevardul Unirii 232');
SELECT * FROM SUCURSALE
ORDER BY ID_SUCURSALA DESC;

15) Creati o secventa numita Viitori_clienti care va genera id_ul viitorilor clienti incepand cu 1, va
merge din 2 in 2 valori si va atinge valoarea maxima de 20.
CREATE SEQUENCE id_viitori_clienti_seq
INCREMENT BY 2
START WITH 1
MAXVALUE 20
NOCACHE
NOCYCLE;
SELECT sequence_name, min_value, max_value, increment_by, last_number
FROM user_sequences;

16) Afisati clientii care au cel putin un imprumut, dar si pe cei care nu au niciun imprumut, printr-o
junctiune externa la stanga.
SELECT c.id_client, nume, prenume, id_imprumut
FROM clienti c, imprumuturi i
WHERE c.id_client=i.id_client(+);

17) Afisati clientii care au cel putin un imprumut, dar si pe cei care nu au niciun imprumut, printr-o
junctiune externa la dreapta.
SELECT c.id_client, nume, prenume, id_imprumut
FROM clienti c, imprumuturi i
WHERE i.id_client(+)=c.id_client;

18) Afisati superiorii angajatului care are salariul egal cu cel al angajatului cu id_ul 13, fara a-l include si
pe acesta.
SELECT id_angajat, nume, prenume, id_manager, LEVEL , SYS_CONNECT_BY_PATH(NUME, '*')
FROM angajati
CONNECT BY id_angajat=PRIOR id_manager
START WITH salariu IN (SELECT salariu FROM angajati WHERE id_angajat=13)
MINUS
SELECT id_angajat, nume, prenume, id_manager, LEVEL , SYS_CONNECT_BY_PATH(NUME, '*')
FROM angajati
WHERE id_angajat=13
CONNECT BY id_angajat=PRIOR id_manager
START WITH salariu IN (SELECT salariu FROM angajati WHERE id_angajat=13)
ORDER BY id_angajat;

19) Realizati o statistica pe fiecare department referitoare la salariul minim, salariul mediu, salariul
maxim si numarul total de angajati.
SELECT a.id_departament, nume_departament, min(salariu) Salariu_minim, max(salariu) Salariu_maxim,
ROUND(AVG(salariu),1) Salariu_mediu, count(id_angajat) Numar_angajati
FROM Angajati a, Departamente d
WHERE a.id_departament=d.id_departament
GROUP BY a.id_departament, nume_departament
order by id_departament;

20) Sa se modifice tabela angajati astfel: salariul creste cu 5% pentru cei angajati de cel mult de 5 ani,
10% pentru cei angajati de 6-10 ani, iar pentru ceilalti, 15%
UPDATE ANGAJATI
SET salariu=CASE WHEN EXTRACT(YEAR FROM SYSDATE)-EXTRACT(YEAR FROM DATA_ANGAJARII)<=5
THEN salariu*1.05
 WHEN EXTRACT(YEAR FROM SYSDATE)-EXTRACT(YEAR FROM DATA_ANGAJARII) BETWEEN 6 AND 10
THEN salariu*1.1
 ELSE salariu*1.15 END
SELECT * FROM ANGAJATI;
