# Passo a passo para montar o projeto no Power BI

## 1. Importar a base
Abra o Power BI Desktop e importe a base Financial Sample.

## 2. Criar a consulta de origem
No Power Query, duplique ou referencie a tabela original e renomeie para `Financials_origem`.

Use essa consulta como base das transformações.

## 3. Criar D_Produtos
Crie uma referência de `Financials_origem`.

Mantenha os campos relacionados a produto e faça os agrupamentos necessários para calcular:
- média das unidades vendidas;
- média do valor de vendas;
- mediana do valor de vendas;
- maior valor;
- menor valor.

Crie um identificador `ID_Produto`.

## 4. Criar D_Produtos_Detalhes
Crie nova referência da origem.

Mantenha:
- ID_Produto;
- Produto;
- Manufacturing Price.

Remova duplicidades.

## 5. Criar D_Descontos
Crie uma dimensão com as categorias de desconto.

Mantenha:
- ID_Desconto;
- Discount Band;
- Desconto.

Garanta que o campo de chave seja único.

## 6. Criar D_Detalhes
Monte a dimensão com:
- ID_Detalhe;
- Segment;
- Country.

Cada combinação válida deve ter uma chave própria.

## 7. Criar F_Vendas
A tabela fato deve preservar os registros de venda.

Campos sugeridos:
- SK_ID;
- ID_Produto;
- ID_Desconto;
- ID_Detalhe;
- Produto;
- Units Sold;
- Sale Price;
- Gross Sales;
- Discounts;
- Sales;
- COGS;
- Profit;
- Date.

## 8. Criar D_Calendário
Use o código DAX disponível em `docs/dax-medidas.md`.

Depois:
1. selecione a tabela calendário;
2. vá até Ferramentas de tabela;
3. escolha Marcar como tabela de datas;
4. selecione o campo `Date`.

## 9. Criar os relacionamentos
Na tela Modelo:
- D_Produtos → F_Vendas;
- D_Descontos → F_Vendas;
- D_Detalhes → F_Vendas;
- D_Calendário → F_Vendas.

Priorize cardinalidade 1:N e filtro em uma direção.

## 10. Organizar a tela Modelo
Deixe `F_Vendas` no centro.

Posicione as dimensões ao redor para que o desenho do esquema estrela fique visualmente evidente.

## 11. Criar medidas
Use as medidas disponíveis em `docs/dax-medidas.md`.

## 12. Validar
Confirme:
- ausência de relacionamentos ambíguos;
- chaves únicas nas dimensões;
- tipos de dados corretos;
- tabela calendário funcionando;
- valores das medidas compatíveis com a base.

## 13. Salvar e documentar
Salve o arquivo `.pbix` na pasta `powerbi/`.

Faça uma captura real da tela Modelo e substitua ou complemente as imagens ilustrativas na pasta `images/`.
