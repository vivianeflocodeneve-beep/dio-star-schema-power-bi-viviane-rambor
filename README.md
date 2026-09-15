📊 Criando um Star Schema para Cenários de Vendas com Power BI

Projeto prático — DIO

Autora: Viviane Rambor
Tecnologia: Microsoft Power BI
Tema: Modelagem dimensional — Star Schema
Repositório: https://github.com/vivianeflocodeneve-beep/dio-star-schema-power-bi-viviane-rambor

Sobre o projeto

Este projeto foi desenvolvido como parte do desafio da DIO voltado à criação de um Star Schema para um cenário de vendas no Power BI. A proposta foi organizar uma base transacional em uma estrutura dimensional simples, clara e adequada para análises.

O modelo final utiliza uma tabela fato de vendas no centro e dimensões relacionadas a calendário, produtos, detalhes de produtos, descontos e características da operação.

Evidência do modelo construído

A imagem abaixo é uma captura real da tela Modelo do Power BI Desktop utilizada na etapa final do projeto:



Como referência visual complementar, também foram mantidas as representações organizadas do esquema:



Estrutura do modelo

No arquivo .pbix, as tabelas importadas aparecem com os seguintes nomes técnicos:

Papel no modelo

Tabela no Power BI

Finalidade

Fato

tblFVendas

Registros e métricas das vendas

Dimensão

tblDCalendario

Análises por data e período

Dimensão

tblDProdutos

Informações consolidadas dos produtos

Dimensão

tblDProdutosDetalhes

Detalhes complementares dos produtos

Dimensão

tblDDescontos

Faixas e informações de desconto

Dimensão

tblDDetalhes

Segmento e país

A tabela fato fica posicionada no centro, enquanto as dimensões ficam ao redor, caracterizando o esquema estrela.

Principais campos analisados

A tabela fato concentra informações como quantidade vendida, preço de venda, vendas brutas, descontos, vendas líquidas, custos, lucro e data. As dimensões permitem analisar esses resultados por produto, calendário, desconto, segmento e país.

Conceitos aplicados

modelagem dimensional;

Star Schema;

tabela fato e tabelas dimensão;

relacionamentos e cardinalidade;

Power Query;

DAX;

dimensão calendário;

organização de modelo semântico no Power BI;

preparação de projeto para GitHub.

Medidas DAX documentadas

O repositório inclui exemplos das medidas utilizadas no projeto, entre elas:

Total de Vendas;

Vendas Brutas;

Total de Lucro;

Unidades Vendidas;

Total de Descontos;

Margem de Lucro;

Ticket Médio.

Os códigos estão disponíveis em docs/dax-medidas.md.

Arquivo do Power BI

O projeto final está disponível em:

powerbi/StarSchema_Vendas_Viviane_Rambor.pbix

Estrutura do repositório

dio-star-schema-power-bi-viviane-rambor/
│
├── README.md
├── ENTREGA_DIO.md
├── CHECKLIST_FINAL.md
├── SUBMISSAO_DIO.txt
├── .gitignore
│
├── data/
│   ├── Financial Sample.xlsx
│   └── FONTE_DADOS.md
│
├── docs/
│   ├── dax-medidas.md
│   ├── modelo-de-dados.md
│   ├── passo-a-passo-power-bi.md
│   └── texto-entrega-dio.md
│
├── images/
│   ├── modelo-star-schema-real.jpg
│   ├── modelo-star-schema.png
│   └── modelo-star-schema-wide.png
│
└── powerbi/
    ├── StarSchema_Vendas_Viviane_Rambor.pbix
    ├── README.md
    └── REVISAO_PBIX.md

O que aprendi

O principal aprendizado deste projeto foi perceber que uma análise confiável começa na organização do modelo. Separar fatos e dimensões torna os relacionamentos mais claros e facilita a criação de indicadores e análises no Power BI.

Além da parte técnica, o exercício também ajudou a consolidar uma forma mais organizada de documentar e apresentar um projeto de dados no GitHub.

Conclusão

O projeto permitiu aplicar na prática conceitos de modelagem dimensional no Power BI e transformar uma base de vendas em uma estrutura preparada para análises por diferentes perspectivas. O resultado final reúne o arquivo Power BI, base utilizada, documentação e evidências do modelo construído.

Autora

Viviane Rambor

Projeto desenvolvido para fins educacionais e composição de portfólio profissional.
