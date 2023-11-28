-----------------------------1------------
ADD JAR  /Shamsidate.jar; --Aval Hatman Bayad in Jar ejra shavad

ADD JAR /jars/S2M-0.0.1.jar;

ADD JAR /jars/M2S-0.0.1.jar;

ADD JAR /jars/M2SF-0.0.1.jar;

ADD JAR /jars/N2T-0.0.1.jar;

-----------------------------2------------

CREATE TEMPORARY FUNCTION M2S as 'com.sakthiinfotec.hive.custom.M2S';

CREATE TEMPORARY FUNCTION M2SF as 'com.sakthiinfotec.hive.custom.M2SF';

CREATE TEMPORARY FUNCTION S2M as 'com.sakthiinfotec.hive.custom.S2M';

CREATE TEMPORARY FUNCTION N2T as 'com.sakthiinfotec.hive.custom.N2T';

-----------------------------3------------

select S2M('1375-05-11');

select M2S('2012-02-10') ;

select M2SF('2012-02-10','d F Y') ;

select N2T('125365','ریال') ;

-----------------------------4------------

list jars;


select M2S(cast(hire_date as date)) Tarikhshamsi
from emps where cast(hire_date as date) between S2M('1375-02-01') and  S2M('1402-05-01');