# databricks-google-sheets

Este projeto tem como objetivo extrair dados de planilhas do Google Sheets e transformá-los em DataFrames ou arquivos para posterior uso em pipelines de dados, análises ou integrações.

## Funcionalidades
Autenticação via conta de serviço (Service Account)<br>
Leitura de abas específicas de planilhas privadas<br>
Conversão dos dados para pandas.DataFrame ou Spark DataFrame


## Autenticação com Conta de Serviço
1 - Acesse o Google Cloud Console<br>
2 - Crie ou selecione um projeto<br>
3 - Ative a API Google Sheets<br>
4 - Vá até APIs e serviços > Credenciais<br>
5 - Clique em Criar credenciais > Conta de serviço<br>
6 - Após a criação, vá até a conta criada e clique em "Chaves" > "Adicionar chave" > "Criar nova chave" > JSON<br>
7 - Faça o download do arquivo JSON. Ele será usado no código como "credenciais.json"<br>

**É recomendável utilizar secret scopes do Databricks para realizar a leitura do json.**

## Observações
**A planilha precisa estar compartilhada com a conta de serviço**<br>
O ID da planilha é o trecho da URL entre /d/ e /edit<br>
Exemplo:<br>
URL: https://docs.google.com/spreadsheets/d/1a2B3cD4eF5GhIjKlmNOPqrSTUvwXYZ/edit#gid=0<br>
ID: 1a2B3cD4eF5GhIjKlmNOPqrSTUvwXYZ<br>
Não há necessidade de autenticação interativa/manual

# Próximos passos
Validação de dados de ingestão, com aplicação de regras de esquema e qualidade de conteúdo antes da persistência no lakehouse, utilizando a biblioteca SparkDQ: https://github.com/sparkdq-community/sparkdq
