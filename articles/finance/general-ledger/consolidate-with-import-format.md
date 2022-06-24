---
title: Importar formato para consolidação
description: Este artigo fornece informações detalhadas sobre o formato de importação que é usado quando você consolida dados financeiros de várias entidades legais.
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 0aee830f8fbfa384c86dc16465b202be36f07b73
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871294"
---
# <a name="import-format-for-consolidation"></a>Importar formato para consolidação

[!include [banner](../includes/banner.md)]

Este artigo fornece informações detalhadas sobre o formato de importação que é usado quando você consolida dados financeiros de várias entidades legais. O formato de importação deve ser salvo como um arquivo de texto (.txt).

## <a name="import-format"></a>Formato de importação

A tabela a seguir lista o formato de importação que você deve usar ao fazer uma consolidação durante uma importação.

| Tabela de registros | Formatar | Observação |
|--------------|---------|-------|
| 1            | 170150, Reputação da empresa, 4 | <ul><li>A tabela de registros</li><li>A ID da conta principal de origem</li><li>A linha da conta principal</li><li>O tipo de conta principal</li></ul> |
| 2            | 110130, 01/01/2015, 1, USD, 0,0,80699.39,0,1 | <ul><li>A ID da conta principal</li><li>A data da transação</li><li>O tipo de período fiscal (**0** = abertura, **1** = operacional e **2** = fechamento)</li><li>A moeda da transação</li><li>Débito ou crédito (**0** = débito e **1** = crédito)</li><li>O nível de lançamento</li><li>Valores da transação</li><li>Quantidade</li><li>A RecID local (ambíguo, valor Int64 único para a transação)</li></ul> |
| 3            | USMF0000009, 2017/01/01, FY2017, 1, 2017,01,01, 602200, USD, 6053.6.0 | <ul><li>O número da entrada (número da transação do cabeçalho de orçamento)</li><li>A data padrão do cabeçalho de orçamento</li><li>A ID do modelo de orçamento</li><li>Tipo de orçamento (**1** - Orçamento original, **2** - Transferência, **3** - Revisão, **4** - Ônus, **5** - Pré-ônus, **6** - Orçamento levado adiante, **7** - Projeto, **8** - Ativos fixos, **9** - Previsão de demanda, **10** - Previsão de suprimento, **11** - Rateios, **12** - Orçamento preliminar.)</li><li>A data da linha</li><li>A ID da conta principal da linha</li><li>O código de moeda da linha</li><li>O valor da linha na moeda da transação</li><li>O valor inteiro da enumeração para o tipo de orçamento da linha (despesa ou receita)</li></ul> |
| 4            | DEMF | RecordCompany é a entidade legal de origem. |
| 5            | 110130, 01/01/2015, 1, USD, 0,0,80699.39,0,1 | <ul><li>ID da conta principal</li><li>Data da transação</li><li>Tipo de período fiscal (0 - Abertura, 1 - Operacional e 2 - Fechamento)</li><li>Moeda da transação</li><li>Débito ou crédito (0 para Débito e 1 para Crédito)</li><li>Nível de lançamento</li><li>Valor da transação</li><li>Quantidade</li><li>Um recid local (ambíguo, valor Int64 único para a transação)</li></ul>  |
| 6            | BusinessUnit, 1 departamento, 2 | Os atributos de dimensão financeira que são definidos na ordem de segmento.<p>Você pode usar a página **Exportar** para verificar como os atributos são definidos.</p> |
| 7            | 002,1,658 | <ul><li>O valor de dimensão financeira</li><li>A dimensão financeira, como o índice que é fornecido em RecordDimensions</li><li>Uma ID de registro única e ambígua associada à ID de registro única de RecordTrans ou RecordTrans2</li></ul> |
| 8            | 002,1,1 | <ul><li>Valores de dimensão que são associados à transação de RecordBudget</li><li>A dimensão financeira, como o índice que é fornecido em RecordDimensions</li><li>Uma ID de registro de linha ambígua que é alinhada com a ordem das linhas de transação no arquivo</li></ul> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
