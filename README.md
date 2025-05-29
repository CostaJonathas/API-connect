Script de Integração com API PBXWare e SQL Server
Descrição
Este script realiza:

Consulta à API de múltiplas plataformas (MT01 a MT04) para extrair dados de tenants e licenças.

Geração de dois arquivos Excel com os dados coletados.

Inserção desses dados em duas tabelas SQL Server (ConnectTenants_teste e ConnectTenantsConfig_teste).

Requisitos
Python 3.x

Bibliotecas necessárias:

requests

pandas

openpyxl

pyodbc

pytz

Você pode instalar todas com o comando:

nginx
Copiar
Editar
pip install requests pandas openpyxl pyodbc pytz
Etapas do Script
Define as plataformas e URLs da API.

Coleta dados dos tenants (id, nome, pacote, país, etc.).

Salva os dados dos tenants em um arquivo Excel.

Para cada tenant, coleta dados sobre o uso de licenças (OFFICE, AGENT, CRM, etc.).

Salva os dados das licenças em outro arquivo Excel.

Conecta ao banco de dados SQL Server.

Limpa as tabelas usando TRUNCATE.

Insere os dados das planilhas no banco.

Configurações Necessárias
Você deve substituir no código:

{domínio} pelo domínio da sua API

{Token} pelo seu token da API

excel_file_path e excel_file_path2 pelos caminhos onde os arquivos Excel serão salvos

Dados do SQL Server: server, database, username, password

Observações
As tabelas ConnectTenants_teste e ConnectTenantsConfig_teste precisam existir no SQL Server.

O script apaga os dados antigos com TRUNCATE antes de inserir os novos.

Os dados são truncados para não ultrapassar os limites de caracteres das colunas no banco.
