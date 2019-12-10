# Oracle Express Edition 11g

This template creates a oracle XE database.

## Usage
**IMPORTANT:** The resulting images will be an image with the Oracle binaries installed. On first startup of the container a new database will be created, the following lines highlight when the database is ready to be used:

    #########################
	DATABASE IS READY TO USE!
	#########################


There are two ports that are exposed in this image:
* 1521 which is the port to connect to the Oracle Database.
* 8080 which is the port of Oracle Application Express (APEX).

On the first startup of the container a random password will be generated for the database if not provided. You can find this password in the output line:

	ORACLE PASSWORD FOR SYS AND SYSTEM:

**Note:** The ORACLE_SID for Express Edition is always `XE` and cannot be changed, hence there is no ORACLE_SID parameter provided for the XE build.

The password for those accounts can be changed via the **docker exec** command. **Note**, the container has to be running:
	docker exec <container name> /u01/app/oracle/setPassword.sh <your password>

Once the container has been started you can connect to it just like to any other database:

	sqlplus sys/<your password>@//localhost:1521/XE as sysdba
	sqlplus system/<your password>@//localhost:1521/XE

