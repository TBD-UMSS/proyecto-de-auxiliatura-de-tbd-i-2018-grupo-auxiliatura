/**********************I-DEP-DENIKIN-CURR-0-08-05-2018**********************/
--------------- SQL ---------------

ALTER TABLE curr.estudio
  ADD CONSTRAINT estudio_fk FOREIGN KEY (id_dato_personal)
    REFERENCES curr.dato_personal(id_dato_personal)
    ON DELETE CASCADE
    ON UPDATE NO ACTION
    NOT DEFERRABLE;

--------------- SQL ---------------

ALTER TABLE curr.estudio
  ADD CONSTRAINT estudio_fk1 FOREIGN KEY (id_institucion_educatica)
    REFERENCES curr.instruccion_educativa(id_institucion_educativa)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION
    NOT DEFERRABLE;

--------------- SQL ---------------

ALTER TABLE curr."table"
  ADD CONSTRAINT table_fk FOREIGN KEY (id_empresa)
    REFERENCES curr.empresa(id_empresa)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION
    NOT DEFERRABLE;

--------------- SQL ---------------

ALTER TABLE curr."table"
  ADD CONSTRAINT table_fk1 FOREIGN KEY (id_dato_personal)
    REFERENCES curr.dato_personal(id_dato_personal)
    ON DELETE CASCADE
    ON UPDATE NO ACTION
    NOT DEFERRABLE;

--------------- SQL ---------------

ALTER TABLE curr.certificado
  ADD CONSTRAINT certificado_fk FOREIGN KEY (id_dato_personal)
    REFERENCES curr.dato_personal(id_dato_personal)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION
    NOT DEFERRABLE;

--------------- SQL ---------------

ALTER TABLE curr.tipo_certificado
  ADD CONSTRAINT tipo_certificado_fk FOREIGN KEY (id_certificado)
    REFERENCES curr.certificado(id_certificado)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION
    NOT DEFERRABLE;




/**********************F-DEP-DENIKIN-CURR-0-08-05-2018**********************/ 