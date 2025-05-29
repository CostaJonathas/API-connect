API-connect - Integração com PBXWare e SQL Server
Este script em Python conecta-se à API de múltiplas plataformas PBXWare (MT01 a MT04), coleta informações sobre tenants e licenças, exporta os dados em arquivos Excel e envia tudo para um banco de dados SQL Server.
Funcionalidades
- Consulta à API de tenants de várias plataformas
•	- Coleta de informações como:
•	  - Nome, pacote, código do tenant, país, etc.
•	  - Uso de licenças (OFFICE, AGENT, SUPERVISOR, etc.)
- Exportação dos dados em dois arquivos Excel
•	- Inserção dos dados em tabelas do SQL Server:
•	  - ConnectTenants_teste
•	  - ConnectTenantsConfig_teste
Requisitos
- Python 3.x
Instale os pacotes necessários com o comando:
pip install requests pandas openpyxl pyodbc pytz
Etapas do Processo
1.	1. Define plataformas e URLs da API
2.	2. Consulta os tenants e salva no Excel
3.	3. Consulta o uso de licenças por tenant e salva no Excel
4.	4. Conecta ao banco de dados SQL Server
5.	5. Apaga os dados antigos (TRUNCATE TABLE)
6.	6. Insere os dados atualizados nas tabelas
Configurações Necessárias
Antes de executar o script, edite o código para configurar:
- {domínio} = domínio da sua API
- {Token} = token de autenticação da API
- excel_file_path e excel_file_path2 = caminhos para salvar os arquivos Excel
- Conexão com o banco SQL Server:
  - server
  - database
  - username
  - password
Observações
- As tabelas ConnectTenants_teste e ConnectTenantsConfig_teste devem existir no banco de dados.
- Os dados antigos são apagados com TRUNCATE antes da nova inserção.
- Alguns campos são truncados para respeitar o limite de caracteres do banco.
Como executar
1. Salve o código como script Python (.py)
2. Execute com o comando:
python nome_do_arquivo.py
