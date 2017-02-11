# LX-DBA-5to
Exercises about Oracle DB - LX 5to 2017

-- creacion de tablas

create table Empleados
(IDEmpleado number(4) not null, Nombre varchar2(20), Apellidos varchar2(30), 
fec_ingreso date, Sexo varchar2(1), Edo_civ varchar2(1), ID_ocupa varchar2(4), 
ID_pais varchar2(4), ID_provincia varchar2(7), ID_ciudad varchar2(4));

create table Ocupacion
(ID_ocupa varchar2(4) not null, Ocupacion varchar2(20), Ingreso_dia number(4));

create table Pais
(ID_pais varchar2(4) not null, Pais varchar2(20));

create table Provincia
(ID_provincia varchar2(7) not null, Provincia varchar2(20)):

create table Ciudad
(ID_ciudad varchar2(4) not null, Ciudad varchar2(20));


-- crear llaves primarias

alter table Empleados add constraint pk_empleados
 primary key(IDEmpleado);

alter table Ocupacion add constraint pk_ocaupacion
 primary key(ID_ocupa);

alter table Pais add constraint pk_pais
 primary key(ID_pais);

alter table Provincia add constraint pk_provincia
 primary key(ID_provincia);

alter table Ciudad add constraint pk_ciudad
 primary key(ID_ciudad);


-- llaves foraneas

alter table Empleados add constraint fk_ocupa
foreign key(ID_ocupa) references Ocupacion(ID_ocupa);

alter table Empleados add constraint fk_pais
foreign key(ID_pais) references Pais(ID_pais);

alter table Empleados add constraint fk_provincia
foreign key(ID_provincia) references Provincia(ID_provincia);

alter table Empleados add constraint fk_ciudad
foreign key(ID_ciudad) references Ciudad(ID_ciudad);

commit;

Alter table "nombre de la tabla donde se creará la llave foranea" add constraint fk_"alguna etiqueta" 
foreign key "llave primaria" references "tabla de donde se toma la llame primaria"("llave primaria"); 
