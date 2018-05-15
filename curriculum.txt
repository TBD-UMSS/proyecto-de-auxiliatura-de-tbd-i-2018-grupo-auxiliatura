/*****************I-PATH-DENIKIN-CURR-0-08-05-2018*****************/
--------------- SQL ---------------

CREATE SCHEMA curr AUTHORIZATION postgres;

--------------- SQL ---------------

CREATE TABLE curr.instruccion_educativa (
  id_institucion_educativa SERIAL,
  institucion_educativa VARCHAR NOT NULL,
  direccion VARCHAR,
  telefono VARCHAR,
  CONSTRAINT instruccion_educativa_pkey PRIMARY KEY(id_institucion_educativa)
) 
WITH (oids = false);

--------------- SQL ---------------

CREATE TABLE curr.dato_personal (
  id_dato_personal SERIAL NOT NULL,
  nombre VARCHAR NOT NULL,
  apellido_paterno VARCHAR NOT NULL,
  apellido_materno VARCHAR NOT NULL,
  ci INTEGER NOT NULL,
  fecha_nacimiento DATE NOT NULL,
  fecha_registro TIMESTAMP WITHOUT TIME ZONE DEFAULT now() NOT NULL,
  PRIMARY KEY(id_dato_personal)
) 
WITH (oids = false);

--------------- SQL ---------------

CREATE TABLE curr.estudio (
  fecha_graduacion DATE,
  nivel_academico VARCHAR,
  fecha_inicio DATE,
  fecha_fin DATE,
  mencion VARCHAR(1),
  id_dato_personal INTEGER,
  id_institucion_educatica INTEGER
) 
WITH (oids = false);

--------------- SQL ---------------

CREATE TABLE curr.empresa (
  id_empresa SERIAL NOT NULL,
  nit SERIAL NOT NULL,
  ubicacion VARCHAR NOT NULL,
  ciudad VARCHAR NOT NULL,
  PRIMARY KEY(id_empresa)
) 
WITH (oids = false);

--------------- SQL ---------------

CREATE TABLE curr."table" (
  cargo VARCHAR NOT NULL,
  detalle VARCHAR NOT NULL,
  "años_servivio" INTERVAL NOT NULL,
  id_empresa INTEGER NOT NULL,
  id_dato_personal INTEGER NOT NULL
) 
WITH (oids = false);

--------------- SQL ---------------

CREATE TABLE curr.certificado (
  id_certificado VARCHAR NOT NULL,
  curso VARCHAR NOT NULL,
  fecha_finalizacion DATE NOT NULL,
  id_dato_personal INTEGER,
  PRIMARY KEY(id_certificado)
) 
WITH (oids = false);

--------------- SQL ---------------

CREATE TABLE curr.tipo_certificado (
  id_tipo_certificado VARCHAR,
  nombre_tipo_certificado VARCHAR NOT NULL,
  grado VARCHAR(1),
  id_certificado VARCHAR
) 
WITH (oids = false);


/*****************F-PATH-DENIKIN-CURR-0-08-05-2018*****************/