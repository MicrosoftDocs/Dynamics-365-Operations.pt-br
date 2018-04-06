---
title: Impostos brasileiros
description: "O Microsoft Dynamics 365 for Finance and Operations calcula os impostos brasileiros com base no tipo de imposto especificado para o código do imposto. É possível configurar e calcular os impostos sobre vendas nas vendas, nas compras, nas transferências entre estabelecimentos fiscais, na entrega de itens a um terceiro, ou no recebimento de itens de um terceiro."
author: sndray
manager: AnnBe
ms.date: 08/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 268704
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 075356e1f5589c9e48bb99e4b3ba1bca7f4af57e
ms.contentlocale: pt-br
ms.lasthandoff: 03/26/2018

---

# <a name="brazilian-taxes"></a>Impostos brasileiros

[!include[banner](../includes/banner.md)]


O Finance and Operations calcula os impostos brasileiros com base no tipo de imposto especificado para o código do imposto. É possível configurar e calcular os impostos sobre vendas nas vendas, nas compras, nas transferências entre estabelecimentos fiscais, na entrega de itens a um terceiro, ou no recebimento de itens de um terceiro.

Você pode configurar códigos de tributação para Imposto sobre Circulação de Mercadorias e Serviços (ICMS), Imposto sobre Produtos Industrializados (IPI), Programa de Integracao Social (PIS) e Contribuição para Financiamento da Seguridade Social (COFINS) Os códigos de tributação são usados para o relatório fiscal e a geração de documentos eletrônicos fiscais (NF-e). Também é possível configurar códigos de tributação em outros tipos de imposto. Ao configurar um código de tributação para um tipo de imposto, você atribui um valor fiscal para indicar o tipo de tratamento que se aplica aos impostos, como tributáveis, não tributáveis ou isentos, ou tributáveis sem crédito. Quando um código de tributação não é configurado para um tipo de imposto, configure o valor fiscal selecionando as opções **Sem crédito de imposto** e **Isento** nas páginas **Grupos de impostos** e **Grupos de impostos do item**. Os impostos de vendas são calculados e salvos na página **Imposto lançado**. É possível especificar um código de tributação padrão para o código do imposto no campo **Código de tributação** na página **Códigos de imposto**. Também é possível especificar o código de tributação para um código de imposto quando você anexa o código de impostos ao seguinte:
-   Um grupo de impostos e o código do imposto é isento.
-   Um grupo de impostos do item.

Ao criar e lançar transações de impostos de ordens de venda, ordens de compra, faturas de texto livre, ou de propostas de fatura de projeto, os impostos serão calculados com base no valor fiscal dos códigos de tributação que estão selecionados no campo no campo **Valor fiscal** na página **Código de tributação**, ou o valor fiscal é determinado com base nas opções **Sem crédito de imposto** e **Isento** nas páginas **Grupos de impostos** e **Grupos de impostos do item**. Os valores de base e de imposto são exibidos nas páginas **Imposto lançado** e **Transações temporárias de imposto**, como segue:
-   Para transações com códigos de tributação que possuem um valor **1. com crédito/débito fiscal**, ou grupos de impostos do item para os quais a opção **Sem crédito** **de imposto** não estiver marcada, o valor do imposto é calculado para ser igual ao valor base tributável. O valor do imposto é calculado de acordo com a taxa de imposto, e é atualizado no campo **Valor real do imposto**.
-   Para transações com códigos de tributação que têm um valor fiscal **2. sem crédito/débito** **(isento ou não tributável)**, ou grupos de imposto ou grupos de impostos do item para os quais a opção **Isento** é selecionada, o valor base de isenção é igual ao valor da transação e nenhum valor de imposto é calculado.
-   Para transações com códigos de tributação que possuem um valor fiscal de **3. sem crédito/débito (outros)** ou grupos de impostos do item para os quais a opção **Sem crédito de imposto** estiver marcada, o outro valor base é igual ao valor da transação. O valor do imposto é calculado de acordo com a taxa de imposto, e é atualizado no campo **Outro valor de imposto**.

## <a name="brazilian-tax-types"></a>Tipos de impostos brasileiros
Os seguintes tipos de imposto estão disponíveis na configuração de código de imposto.
-   IPI – Imposto sobre Produtos Industrializados
-   PIS – Programa de Integração Social
-   ICMS – Imposto sobre Circulação de Mercadorias e Serviços
-   COFINS – Contribuição para Financiamento da Seguridade Social
-   ISS – Imposto sobre Serviços
-   IRRF – Imposto de Renda Retido na Fonte
-   INSS – Imposto Nacional de Seguridade Social.
-   Imposto de importação
-   Outros impostos
-   INSS Retido
-   CSLL – Contribuição Social sobre Lucro Líquido
-   ICMS-ST – Substituição tributária do ICMS. Além disso, o usuário pode especificar um dos seguintes métodos de cálculo:
    -   Operação própria, IPI e marcação
    -   Somente operação própria
-   ICMS-DIF (diferencial de ICMS). Este tipo de imposto usado para calcular o valor diferencial do ICMS nos seguintes cenários:
    -   A nota fiscal será emitida ao consumidor final localizado em outro estado.
    -   A nota fiscal é recebida em um estado diferente. Aplicável para ativos fixos e itens de uso e consumo.

## <a name="examples"></a>Exemplos
Para o valor de uma transação de base de R$ 1.000,00 e uma taxa de imposto de 18%, o Microsoft Dynamics 365 for Finance and Operations calcula os impostos da seguinte maneira para valores fiscais diferentes.
| Valor fiscal                                    | Origem do valor | Valor real do imposto | Valor base de isenção | Outro valor base | Outro valor de imposto |
|-------------------------------------------------|---------------|-------------------------|--------------------|-------------------|------------------|
| 1. Com Crédito/Débito                            | R$ 1.000,00  | R$ 180,00              |                    |                   |                  |
| 2. Sem Crédito/Débito (Isento ou Não Tributável) |               |                         | R$ 1.000,00       |                   |                  |
| 3. sem crédito/débito (outros)                 |               |                         |                    | R$ 1.000,00      | R$ 180,00       |

Para o valor de uma transação de base de R$ 1.000,00, uma taxa de imposto de 18% e uma porcentagem de redução de imposto de 40%, os impostos são calculados da seguinte maneira para valores fiscais diferentes.
| Valor fiscal                                    | Origem do valor | Valor real do imposto | Valor base de isenção | Outro valor base | Outro valor de imposto |
|-------------------------------------------------|---------------|-------------------------|--------------------|-------------------|------------------|
| 1. Com Crédito/Débito                            | R$ 600,00    | R$ 108,00              | R$ 400,00         |                   |                  |
| 2. Sem Crédito/Débito (Isento ou Não Tributável) |               |                         | R$ 1.000,00       |                   |                  |
| 3. sem crédito/débito (outros)                 |               |                         | R$ 400,00         | R$ 600,00        | R$ 108,00       |

Para transações de venda com códigos de tributação que têm um valor fiscal **1. com crédito/débito**, ou grupos de impostos do item para os quais a opção **Sem crédito de imposto** não estiver marcada, o valor do imposto real é lançado em contas principais para as quais **Imposto** e **Despesas com imposto** são selecionados no campo **Tipo de lançamento** na página **Contas para transações automáticas**. Para transações de compra com códigos de tributação que têm um valor fiscal **1. com crédito/débito**, ou grupos de impostos do item para os quais a opção **Sem crédito de imposto** não estiver marcada, o valor do imposto real é lançado em contas principais para as quais **Imposto** é selecionado no campo **Tipo de lançamento** na página **Contas para transações automáticas**.

## <a name="additional-resources"></a>Recursos adicionais
-   [Atributos de impostos brasileiros](latam-bra-tax-attributes.md)
-   [Pagamentos de impostos brasileiros](latam-bra-tax-payments.md)
-   [Impostos retidos na fonte no Brasil ](tasks/br-00009-brazilian-withholding-taxes.md)



