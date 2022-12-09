---
title: Gerenciador de fontes contábeis
description: Este artigo fornece informações sobre a página Explorador de origem da contabilidade, que pode ser usada para análise detalhada das informações de origem, além das entradas contábeis da contabilidade.
author: RyanCCarlson2
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingSourceExplorer
audience: Application User
ms.reviewer: kfend
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5bd5580dc0be37ec89e6c7934b47c7d5593d8716
ms.sourcegitcommit: 5f8f042f3f7c3aee1a7303652ea66e40d34216e3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/29/2022
ms.locfileid: "9806424"
---
# <a name="accounting-source-explorer"></a>Gerenciador de fontes contábeis

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre a página **Explorador de origem da contabilidade**, que pode ser usada para análise detalhada das informações de origem, além das entradas contábeis da contabilidade.

A página **Explorador de origem contábil** mostra informações de origem. Você pode usá-la como uma ferramenta independente ou para analisar os detalhes das entradas de contas contábeis. Por exemplo, você pode usar a página para obter as informações mais detalhadas da origem para um saldo no rastreamento de saldos ou para uma transação do comprovante. Você pode usar o recurso **Exportar para MS Excel** para dividir ainda mais as informações no Microsoft Excel (por exemplo, em uma Tabela Dinâmica ou em um relatório de Tabela Dinâmica).

A página **Explorador de origem contábil** sempre exibe o mesmo valor total por conta contábil mostrado pela contabilidade (por exemplo, no balancete). Como no Balancete, é possível exibir segmentos nas colunas separadas. Selecione o conjunto de dimensões financeiras apropriado. 

É possível usar os parâmetros para definir um intervalo de datas para análise. Esta funcionalidade também se assemelha à funcionalidade no balancete.

Para todos os documentos que usam estrutura do documento de origem, a página **Explorador da origem contábil** exibe informações adicionais, com base nas distribuições contábeis e, se aplicável, em distribuições contábeis do projeto Essas informações incluem os valores **Tipo de valor monetário**, **Projeto**, **Atividade**, **Categoria** e **Propriedade da linha**. Veja alguns exemplos da análise que você pode fazer:

- Variações entre ordens de compra e faturas de fornecedor, pois cada variação é representada por um tipo de valor monetário, como a variação de encargo
- Horas faturáveis versus horas não faturáveis e despesas por projeto, unidade de negócios e conta principal

Para documentos de origem que usam o conceito de identidades de referência do documento de origem, a página **Explorador de origem contábil** exibe ainda mais detalhes, como **Cliente**, **Fornecedor**, **Trabalhador**, **Produto**, **Quantidade**, **Texto de unidade** e **Descrição**. Veja alguns exemplos da análise que você pode fazer:

- Despesas com hotéis por unidade de negócios e nome do hotel para um período fiscal, com base nos relatórios de despesas
- Descontos por fornecedor, produtos, departamento

Para esses documentos, também é possível navegar no documento de origem real da página **Explorador de origem contábil**.

> [!NOTE]
> A partir da versão 10.0.31, um novo recurso **Filtragem avançada do gerenciador de origens contábeis** está disponível no gerenciamento de recursos. Esse recurso substitui o botão **Atualizar** para fornecer uma experiência de consulta avançada mais sólida, semelhante ao que está disponível na página **Transações de comprovante**. O filtro avançado permite filtrar os campos semelhantes do que você encontra na página **Consulta de transações de comprovante**, como **Conta contábil**, **Unidade de negócios**, **Centro de custo** e **Departamento**. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
