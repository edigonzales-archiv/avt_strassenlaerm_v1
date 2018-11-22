# avt_strassenlaerm

```
java -jar /Users/stefan/apps/ili2pg-3.12.2/ili2pg-3.12.2.jar --dbhost 192.168.50.8 --dbdatabase edit --dbusr ddluser --dbpwd ddluser --nameByTopic --strokeArcs --sqlEnableNull --defaultSrsCode 2056 --modeldir "http://models.geo.admin.ch;." --models SO_AVT_LBK_Haupt_uebrigeStrassen_20181122 --dbschema avt_strlaerm1 --schemaimport

java -jar /Users/stefan/apps/ili2pg-3.12.2/ili2pg-3.12.2.jar --dbhost 192.168.50.8 --dbdatabase edit --dbusr ddluser --dbpwd ddluser --nameByTopic --strokeArcs --sqlEnableNull --defaultSrsCode 2056 --modeldir "http://models.geo.admin.ch;." --models LBK_Haupt_uebrigeStrassen_Codelisten_V1_1 --dbschema avt_strlaerm1 --import LBK_Haupt_uebrigeStrassen_Catalogues_V1_1.xml


INSERT INTO avt_strlaerm1.immission_strasse_dispersion_calculation
(t_id, t_type, dispcal_remark, dispersionmodel, dispersionapplication, versionnr_dispapp, meterologydata, heightmodel, building_database, noisebarrier_geodata, emissiondata, refyear_register, npr_name, i_measurement)
VALUES(101, 'so_vt_l0181122immission_strasse_dispersion_calculation', 'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 1, 'j', true);

INSERT INTO avt_strlaerm1.immission_strasse_pointofdetermination
(t_id, t_type, determination_remark, lr_day, lr_night, mcd_street, mcn_street, id_pod, egid, edid, address_pod, exposure_limit_date, operation_status, pointofdetermination_t, exposure_limit_value_d, exposure_limit_value_n, dispersion_calculation, incl_highway, geometry_pod)
VALUES(102, 'so_vt_l0181122immission_strasse_pointofdetermination', 'aa', 11.0, 22.0, 33.0, 44.0, 'bb', 55, 66, 'cc', '2018-11-23', 12, NULL, NULL, NULL, 101, true, NULL);

UPDATE avt_strlaerm1.immission_strasse_pointofdetermination SET geometry_pod = ST_SetSRID(ST_MakePoint(2600000, 1200000, 500),2056);

INSERT INTO avt_strlaerm1.emission_strasse_inputdata_estreet
(t_id, t_type, inputdata_remark, adtf, nt, nn, p_nt2, p_nn2, gradient, trafficcol_remark, refyear_trafficcol, scs, track_number, direction_seperate, roadsurface_correction, modelcorrection_day, modelcorrection_night, modelcorrection_remark, refyear_modcal_str, trafficcollection, used_roadspeed, vt1_str, vt2_str, vn1_str, vn2_str, rollingnoise_correction, streetemission, vt_str, vn_str, streetemission1)
VALUES(103, 'emission_strasse_inputdata_estreet_so', 'aaa', 123, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL);

INSERT INTO avt_strlaerm1.emission_strasse_inputdata_estreet
(t_id, t_type, inputdata_remark, adtf, nt, nn, p_nt2, p_nn2, gradient, trafficcol_remark, refyear_trafficcol, scs, track_number, direction_seperate, roadsurface_correction, modelcorrection_day, modelcorrection_night, modelcorrection_remark, refyear_modcal_str, trafficcollection, used_roadspeed, vt1_str, vt2_str, vn1_str, vn2_str, rollingnoise_correction, streetemission, vt_str, vn_str, streetemission1)
VALUES(104, 'emission_strasse_inputdata_esonroad_so', 'bbb', 678.0, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, 999, NULL, NULL, NULL, NULL, NULL, NULL, NULL);

java -jar /Users/stefan/apps/ili2pg-3.12.2/ili2pg-3.12.2.jar --dbhost 192.168.50.8 --dbdatabase edit --dbusr ddluser --dbpwd ddluser --nameByTopic --strokeArcs --defaultSrsCode 2056 --disableValidation --modeldir "http://models.geo.admin.ch;." --models SO_AVT_LBK_Haupt_uebrigeStrassen_20181122 --dbschema avt_strlaerm1 --disableValidation --export fubar.xtf

java -jar /Users/stefan/apps/ili2pg-3.12.2/ili2pg-3.12.2.jar --dbhost 192.168.50.8 --dbdatabase edit --dbusr ddluser --dbpwd ddluser --nameByTopic --strokeArcs --defaultSrsCode 2056 --disableValidation --modeldir "http://models.geo.admin.ch;." --models LBK_Haupt_uebrigeStrassen_Codelisten_V1_1 --dbschema avt_strlaerm1 --disableValidation --export fubar_codeliste.xml

xmllint --format fubar.xtf -o fubar.xtf
xmllint --format fubar_codeliste.xml -o fubar_codeliste.xml

java -jar /Users/stefan/apps/ili2pg-3.12.2/ili2pg-3.12.2.jar --dbhost 192.168.50.8 --dbdatabase edit --dbusr ddluser --dbpwd ddluser --nameByTopic --strokeArcs --defaultSrsCode 2056 --disableValidation --modeldir "http://models.geo.admin.ch;." --models SO_AVT_LBK_Haupt_uebrigeStrassen_20181122 --exportModels LBK_Haupt_uebrigeStrassen_LV95_V1_1  --dbschema avt_strlaerm1 --disableValidation --export fubar_ch.xtf

xmllint --format fubar_ch.xtf -o fubar_ch.xtf
```