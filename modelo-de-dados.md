# Modelo de Dados

## Tabela fato
`F_Vendas`

## Dimensões
- `D_Produtos`
- `D_Produtos_Detalhes`
- `D_Descontos`
- `D_Detalhes`
- `D_Calendário`

## Tabela de origem
`Financials_origem`

## Relacionamentos principais

- `D_Produtos[ID_Produto]` 1 → N `F_Vendas[ID_Produto]`
- `D_Descontos[ID_Desconto]` 1 → N `F_Vendas[ID_Desconto]`
- `D_Detalhes[ID_Detalhe]` 1 → N `F_Vendas[ID_Detalhe]`
- `D_Calendário[Date]` 1 → N `F_Vendas[Date]`

## Observação sobre D_Produtos_Detalhes
A dimensão deve ser validada para garantir unicidade da chave escolhida. Caso o nível de detalhe seja o mesmo de `D_Produtos`, pode ser mais elegante incorporar os atributos na própria dimensão de produtos. Se o desafio exigir a tabela separada, mantenha-a conforme solicitado, mas evite relacionamentos muitos-para-muitos.
