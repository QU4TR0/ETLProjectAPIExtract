# Projeto de ETL com Python usando Requests

Este projeto é um exemplo simples de como construir um pipeline de ETL (Extract, Transform, Load) utilizando Python. O foco principal é realizar a extração de dados de uma API pública utilizando a biblioteca `requests`, transformar esses dados conforme necessário e carregar os resultados em um formato apropriado (como um arquivo CSV).

## Tecnologias Utilizadas

- **Python 3.x**: Linguagem de programação utilizada para desenvolver o pipeline ETL.
- **requests**: Biblioteca para fazer requisições HTTP e buscar dados de uma API.
- **pandas**: Biblioteca opcional para manipulação e transformação de dados.
- **JSON**: Formato de dados utilizado para comunicação com a API e transformação dos dados.

## Objetivo

O objetivo deste projeto é fornecer um exemplo funcional de como:

1. **Extrair** dados de uma API pública utilizando a biblioteca `requests`.
2. **Transformar** os dados conforme a necessidade do projeto (limpeza, formatação, cálculos, etc.).
3. **Carregar** os dados transformados em um arquivo CSV ou banco de dados para análise posterior.

## Estrutura do Projeto
```
etl_project/
│
├── main.py              # Script principal que executa o processo de ETL
├── requirements.txt     # Arquivo com as dependências do projeto
├── config.py            # Arquivo de configuração (opcional)
└── data/                # Pasta para armazenar dados extraídos e resultados
    └── output.csv       # Arquivo CSV de saída (opcional)
```

## Instalação

1. Clone este repositório:

```bash
git clone https://github.com/seu-usuario/etl-project.git
cd etl-project
