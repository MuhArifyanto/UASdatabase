# Tugas UAS

|**Nama**|**NIM**|**Kelas**|**Matkul**|
|----|---|-----|------|
|Muhammad Arif Mulyanto|312310359|TI.23.A.5|Basis Data

***Query MySQL Pada Tabel Perusahaan***
```
CREATE TABLE Perusahaan(
id_p VARCHAR(10) PRIMARY KEY,
nama VARCHAR(45) NOT NULL,
alamat VARCHAR(45) DEFAULT NULL
);
INSERT INTO Perusahaan VALUES
('P01', 'Kantor Pusat', NULL),
('P02', 'Cabang Bekasi', NULL);
SELECT * FROM Perusahaan;
```
***Output :***
![Screenshot (483)](https://github.com/Maullynn/UASBasisData/assets/144296695/153faa4a-42de-4312-83fc-9df5deb4f021)
***Query MySQL Pada Tabel Departemen***
```
CREATE TABLE Departemen(
id_dept VARCHAR(10) PRIMARY KEY,
nama VARCHAR(45) NOT NULL,
id_p VARCHAR(10) NOT NULL,
manajer_nik VARCHAR(10) DEFAULT NULL
);
INSERT INTO Departemen VALUES
('D01', 'Produksi', 'P02', 'N01'),
('D02', 'Marketing', 'P01', 'N03'),
('D03', 'RnD', 'P02', NULL),
('D04', 'Logistik', 'P02', NULL);
SELECT * FROM Departemen;
```
***Query MySQL Pada Tabel Karyawan***
```
CREATE TABLE Karyawan(
    nik VARCHAR(10) PRIMARY KEY,
    nama VARCHAR(45) NOT NULL,
    id_dept VARCHAR(10) NOT NULL,
    sup_nik VARCHAR(10) DEFAULT NULL,
    gaji_pokok INT
);
INSERT INTO Karyawan VALUES
('N01', 'Ari', 'D01', NULL, 2000000),
('N02', 'Dina', 'D01', NULL, 2500000),
('N03', 'Rika', 'D03', NULL, 2400000),
('N04', 'Ratih', 'D01', 'N01', 3000000),
('N05', 'Riko', 'D01', 'N01', 2800000),
('N06', 'Dani', 'D02', NULL, 2100000),
('N07', 'Anis', 'D02', 'N06', 5000000),
('N08', 'Dika', 'D02', 'N06', 4000000),
('N09', 'Raka', 'D03', NULL, 2000000);
SELECT * FROM Karyawan;
```
***Query MySQL Pada Tabel Project***
```sql
CREATE TABLE Project(
id_proj VARCHAR(10) PRIMARY KEY,
nama VARCHAR(45) NOT NULL,
tgl_mulai DATETIME,
tgl_selesai DATETIME,
status TINYINT(1)
);
INSERT INTO Project VALUES
('PJ01', 'A', '2019-01-10', '2019-03-10', '1'),
('PJ02', 'B', '2019-02-15', '2019-04-10', '1'),
('PJ03', 'C', '2019-03-21', '2019-05-10', '1');
SELECT * FROM Project;
```
***Output :***


***Query MySQL Pada Tabel Project Deatil***
```sql
CREATE TABLE Project_detail(
id_proj VARCHAR(10) NOT NULL,
nik VARCHAR(10) NOT NULL
);
INSERT INTO Project_detail VALUES
('PJ01', 'N01'),
('PJ01', 'N02'),
('PJ01', 'N03'),
('PJ01', 'N04'),
('PJ01', 'N05'),
('PJ01', 'N07'),
('PJ01', 'N08'),
('PJ02', 'N01'),
('PJ02', 'N03'),
('PJ02', 'N05'),
('PJ03', 'N03'),
('PJ03', 'N07'),
('PJ03', 'N08');
SELECT * FROM Project_detail;
```
***Output :***

![tugas uas 3](https://github.com/MuhArifyanto/UASdatabase/assets/147913440/d31fd2b5-f051-434b-bdf0-59a8746d4a55)


## if you get trouble "Cannot add or update a child row: a foreign key constraint fails| MySQL error Solution"
```
set FOREIGN_KEY_CHECKS = 0;
```


