# Medidas DAX do Projeto

## Total de Vendas
```DAX
Total Vendas =
SUM(F_Vendas[Sales])
```

## Vendas Brutas
```DAX
Vendas Brutas =
SUM(F_Vendas[Gross Sales])
```

## Total de Lucro
```DAX
Total Lucro =
SUM(F_Vendas[Profit])
```

## Unidades Vendidas
```DAX
Unidades Vendidas =
SUM(F_Vendas[Units Sold])
```

## Total de Descontos
```DAX
Total Descontos =
SUM(F_Vendas[Discounts])
```

## Margem de Lucro
```DAX
Margem Lucro % =
DIVIDE(
    [Total Lucro],
    [Total Vendas],
    0
)
```

## Ticket Médio
```DAX
Ticket Médio =
DIVIDE(
    [Total Vendas],
    COUNTROWS(F_Vendas),
    0
)
```

## Tabela Calendário
```DAX
D_Calendário =
VAR DataMinima =
    MINX(F_Vendas, F_Vendas[Date])
VAR DataMaxima =
    MAXX(F_Vendas, F_Vendas[Date])
RETURN
ADDCOLUMNS(
    CALENDAR(DataMinima, DataMaxima),
    "Ano", YEAR([Date]),
    "MesNumero", MONTH([Date]),
    "MesNome", FORMAT([Date], "MMMM"),
    "Trimestre", "T" & QUARTER([Date]),
    "AnoMes", FORMAT([Date], "YYYY-MM"),
    "Dia", DAY([Date]),
    "DiaSemanaNumero", WEEKDAY([Date], 2),
    "DiaSemana", FORMAT([Date], "dddd")
)
```
