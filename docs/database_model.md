
Table greenhouse {
id integer [primary key]
sensor_id integer
name varchar
location varchar
size_m2 integer
created_at timestamp
}

Table sensor {
id integer [primary key]
sensor_type integer
created_at timestamp
}

Table sensor_type{
id integer
name varchar
}

Table measurement {
id integer [primary key]
sensor_id integer
greenhouse_id integer
value double
timestamp timestamp
}

Table plant {
id integer [primary key]
name varchar
species varchar
ideal_temperature float
ideal_humidity float
ideal_light_level float
}

Ref: sensor.id < sensor_type.id // many-to-one

Ref: greenhouse.sensor_id < sensor.id
Ref: greenhouse.id < measurement.id

Ref: sensor.id > measurement.sensor_id