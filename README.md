# Projeto de ETL com Python: Extração de Dados da API da Coinbase

Este projeto implementa um pipeline de ETL (Extract, Transform, Load) utilizando Python, com foco na extração de dados de preços do Bitcoin a partir da API pública da Coinbase, sua transformação e armazenamento em um banco de dados PostgreSQL.

## Funcionalidades

- **Extração de Dados**: Conexão com a API da Coinbase para obter informações atualizadas sobre o preço do Bitcoin.
- **Transformação de Dados**: Processamento dos dados extraídos, incluindo a adição de um timestamp para referência temporal.
- **Carregamento de Dados**: Armazenamento dos dados transformados em uma tabela específica dentro de um banco de dados PostgreSQL.
- **Automatização**: Execução contínua do processo de ETL a cada 15 segundos para manter os dados sempre atualizados.
- **Monitoramento**: Implementação de logs utilizando a biblioteca `logging` para acompanhamento e depuração do processo.

## Tecnologias Utilizadas

- **Python 3.8+**: Linguagem principal para desenvolvimento do pipeline.
- **Bibliotecas Python**:
  - `requests`: Para realizar requisições HTTP à API da Coinbase.
  - `pandas`: Para manipulação e transformação dos dados.
  - `sqlalchemy`: Para interação com o banco de dados PostgreSQL.
  - `logging`: Para registro de logs durante a execução do processo.
- **PostgreSQL**: Banco de dados relacional utilizado para armazenar os dados extraídos e transformados.

## Estrutura do Projeto

- `app/`: Dashboards de visualização do processo de ETL da API.
- `src/`: Contém os scripts principais para execução do pipeline ETL.
- `.gitignore`: Arquivo que especifica quais arquivos ou pastas devem ser ignorados pelo Git.
- `README.md`: Este arquivo, contendo informações detalhadas sobre o projeto.
- `requirements.txt`: Lista de dependências necessárias para executar o projeto.

## Configuração e Execução

1. **Clonar o Repositório**:

   ```bash
   git clone https://github.com/QU4TR0/ETLProjectAPIExtract.git
   cd ETLProjectAPIExtract
   ```

2. **Configurar o Ambiente Virtual** (opcional, mas recomendado):

   ```bash
   python -m venv venv
   source venv/bin/activate  # No Windows, use 'venv\Scripts\activate'
   ```

3. **Instalar as Dependências**:

   ```bash
   pip install -r requirements.txt
   ```

4. **Configurar Variáveis de Ambiente**:

   Crie um arquivo `.env` na raiz do projeto com as seguintes informações:

   ```ini
   DB_USER=seu_usuario
   DB_PASSWORD=sua_senha
   DB_HOST=localhost
   DB_PORT=5432
   DB_NAME=nome_do_banco
   ```

   Substitua os valores conforme a configuração do seu banco de dados PostgreSQL.

5. **Executar o Pipeline ETL**:

   ```bash
   python src/pipeline_02.py
   ```

   O script iniciará o processo de ETL, extraindo dados da API da Coinbase, transformando-os e carregando-os no banco de dados PostgreSQL a cada 15 segundos.

6. **Executar o Pipeline ETL com logfire**:

    Adicione ao arquivo `.env` um `LOGFIRE_TOKEN`. [Logfire Documentation](https://logfire.pydantic.dev/docs/how-to-guides/create-write-tokens/)

   ```bash
   python src/pipeline_03.py
   ```
   Ao executar o script ele iniciará o processo de ETL, extraindo dados da API da Coinbase, transformando-os e carregando-os no banco de dados PostgreSQL a cada 15 segundos, além do processo de ETL, irá realizar o salvamento dos logs de execução na ferramenta [Logfire](https://logfire-us.pydantic.dev/).

## Observações

- Certifique-se de que o serviço do PostgreSQL esteja em execução e acessível conforme as configurações fornecidas no arquivo `.env`.
- Verifique se as tabelas necessárias no banco de dados são criadas automaticamente pelo SQLAlchemy ou crie-as manualmente conforme a modelagem definida no código.
- O intervalo de 15 segundos para execução contínua pode ser ajustado conforme a necessidade, modificando o parâmetro adequado no código.

## Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar pull requests com melhorias, correções ou novas funcionalidades.

## Licença

Este projeto está licenciado sob a Licença MIT. Consulte o arquivo LICENSE para mais detalhes.
