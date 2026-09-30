# Ingesting the data

- Download the dataset from 'data/source/data.txt'
- Create an EC2 instance > docker container > mcr/microsoft.com/mssql/server:2025-latest
- spin up the legacy MSSQL server

docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=SqlServer@2026Dev#01" -p 1433:1433 --name legacy-mssql -d mcr.microsoft.com/mssql/server:2025-latest

# multi-line with volume inside EC2
docker run -v mssql_data:/var/opt/mssql \
-e "ACCET_EULA=Y" \
-e "MSSQL_SA_PASSWORD=SqlServer@2026Dev#01" \
-p 1433:1433 \
--name legacy-mssql \
-d mcr.microsoft.com/mssql/server:2025-latest



