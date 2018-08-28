Install Postgis
---
notes:
- PostGIS's features must be activated on a per-database basis before you can store spacial data.


Ubuntu:
- sudo apt-get install postgis
- login to database
- enable postgis `CREATE EXTENSION postgis;`
- verify postgis `SELECT PostGIS_version();`
