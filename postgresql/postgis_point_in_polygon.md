Point in Polygon using PostGIS
---

```
create temp table poly
(
  name varchar
);

select AddGeometryColumn('poly', 'geom', 4269, 'GEOMETRY', 2);

insert into poly (name, geom) 
values ('CP',ST_GeomFromText('POLYGON((
0 0,
0 40,
40 40,
40 0,
0 0))',4269));

insert into poly (name, geom)
values ('AS', ST_GeomFromText('
MULTIPOLYGON(((-74.013751 40.711976, -74.01344 40.712439,
-74.012834 40.712191,
-74.013145 40.711732,
-74.013751 40.711976)),
((-74.013622 40.710772,
-74.013311 40.711236,
-74.012699 40.710992,
-74.013021 40.710532,
-74.013622 40.710772)))',4269));

select * from poly;

select name, ST_CONTAINS(geom, ST_GeomFromText('POINT(10 10)', 4269)) from poly;
```
