عمل شاشة دخول مستخدمين فى اوريكال ابيكس

Login Application with Database Table User in Oracle Apex | Mr Gactack

https://www.youtube.com/watch?v=DOn4f8UWZcQ

-----------------------------------------------------------------------------------------------------------------------------
Table:-

create table user_information
(
id number,
user_name varchar2(50),
password varchar2(50),
status char(1)
)
-----------------------------------------------------------------------------------------------------------------------------
Function:-

CREATE OR REPLACE FUNCTION USER_AUTH_FUNC (P_USERNAME IN VARCHAR2,P_PASSWORD IN VARCHAR2)
RETURN BOOLEAN
AS
MVAL NUMBER := 0;
BEGIN
SELECT 1 INTO MVAL FROM USER_INFORMATION A
WHERE UPPER(A.ID) = UPPER(P_USERNAME)
AND A.PASSWORD = P_PASSWORD
AND A.STATUS = 'Y';
RETURN (TRUE);
EXCEPTION
WHEN NO_DATA_FOUND THEN
RETURN FALSE;
END;
-----------------------------------------------------------------------------------------------------------------------------

