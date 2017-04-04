---
title: Impostos brasileiros
description: "Microsoft Dynamics 365 para operações calcula os impostos brasileiros base no tipo de imposto especificados para o código de imposto. É possível configurar e calcular os impostos sobre vendas nas vendas, nas compras, nas transferências entre estabelecimentos fiscais, na entrega de itens a um terceiro, ou no recebimento de itens de um terceiro."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 268704
ms.assetid: 00f3d59f-4c5b-4053-ac68-22063079bd91
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: bec019d218d80ba059d5a1c232072f46b1ae3ee2
ms.openlocfilehash: 0c8619573fd06393e214f8e4ef51f6a44aaac357
ms.lasthandoff: 03/31/2017


---

# <a name="brazilian-taxes"></a>Impostos brasileiros

Microsoft Dynamics 365 para operações calcula os impostos brasileiros base no tipo de imposto especificados para o código de imposto. É possível configurar e calcular os impostos sobre vendas nas vendas, nas compras, nas transferências entre estabelecimentos fiscais, na entrega de itens a um terceiro, ou no recebimento de itens de um terceiro.

Você pode configurar códigos de tributação para Imposto sobre Circulação de Mercadorias e Serviços (ICMS), Imposto sobre Produtos Industrializados (IPI), Programa de Integracao Social (PIS) e Contribuição para Financiamento da Seguridade Social (COFINS) Os códigos de tributação são usados para o relatório fiscal e a geração de documentos eletrônicos fiscais (NF-e). Também é possível configurar códigos de tributação em outros tipos de imposto. Ao configurar um código de tributação para um tipo de imposto, você atribui um valor fiscal para indicar o tipo de tratamento que se aplica aos impostos, como tributáveis, não tributáveis ou isentos, ou tributáveis sem crédito. Quando um código de tributação não é configurado para um tipo de imposto, configure o valor fiscal selecionando ** sem crédito fiscal ** ** e isenção ** opções ** em grupos de impostos ** ** e grupos de impostos sobre itens ** em páginas. Os impostos são calculados e salvos ** vendas lançadas ** na página. Você pode especificar um código de tributação padrão para o código de impostos ** código de tributação ** o campo ** códigos de impostos ** na página. Você pode especificar o código de tributação para um código de impostos quando você anexa o código de impostos a seguir:
-   Um grupo de impostos e o código são isentos.
-   Um grupo de impostos do item.

Quando você criar e lançar transações de imposto de ordens de venda, ordens de compra, o texto livre ou nota fiscal, propostas de nota fiscal de projeto, os impostos são calculados com base em qualquer a um valor fiscal códigos de tributação selecionados em ** valor fiscal ** ** campo código de tributação ** na página, ou no valor fiscal que é determinado com base no fiscal ** sem crédito ** ** e isenção ** em opções ** em grupos de impostos ** ** e os impostos do item se agrupam ** em páginas. O valor de base e de imposto é exibido em ** vendas lançadas ** e ** transações temporárias com impostos ** em páginas, como se segue:
-   Para transações com códigos de tributação que têm a ** 1. no crédito/débito fiscais ** valor, ou grupos de impostos de itens para o quais ** sem impostos ** ** crédito ** a opção não for selecionada, o valor dos impostos serão calculados para é igual ao valor base tributáveis. Os impostos são calculados de acordo com a taxa de impostos e atualizados ** valor real ** de imposto no campo.
-   Para transações com códigos de tributação que têm a ** 2. sem crédito/débito ** ** (isenção ou não tributáveis ** valor fiscal), ou grupos de impostos sobre vendas ou impostos do item para que grupos ** isenção ** a opção for selecionada, o valor base isenção é igual ao valor da transação, e nenhum valor do imposto é calculado.
-   Para transações com códigos de tributação que têm a ** 3. sem crédito/débito (outro) fiscais ** valor, ou grupos de impostos de itens para o quais ** sem crédito fiscal ** a opção for selecionada, o outro valor base é igual ao valor de transação. O valor é calculado de acordo com a taxa de imposto e atualizado ** o valor de outro imposto ** no campo.

## <a name="brazilian-tax-types"></a>Tipos de impostos brasileiros
Os seguintes tipos de imposto estão disponíveis na configuração de código de imposto.
-   – IPI Sobre Produtos Industrializados de impostos (IPI)
-   PIS – Programa de Integracao Social (PIS)
-   ICMS – Sobre Circulação de Mercadorias e Serviços EDI (Imposto ICMS)
-   COFINS – Contribuição para Financiamento da Seguridade Social (COFINS)
-   ISS – Imposto sobre Serviços (ISS)
-   IRRF – Imposto de Renda Retido na Fonte (IRRF)
-   INSS – Retenção Nacional da Seguridade Social INSS ().
-   Imposto de importação
-   Outros impostos
-   INSS Retido
-   CSLL – Contribuição Social sobre o Lucro Líquido (CSLL)
-   ICMS-ST – de substituto tributário de ICMS (ICMS-ST). Além disso, o usuário pode especifique um dos seguintes métodos de cálculo:
    -   Possuir para a operação, o IPI, e a marcação
    -   Somente operação própria
-   – ICMS-DIF (diferencial ICMS ICMS-DIF). Este tipo de imposto usado para calcular o valor diferencial de IMPOSTO ICMS nos seguintes cenários:
    -   A nota fiscal será emitido final localizado ao consumidor em outro estado.
    -   A nota fiscal é anterior recebimento de um estado diferente. Qualificação para ativos fixos e itens de uso e consumo.

## <a name="examples"></a>Exemplos
Para um valor de transação de BRL 1,000.00 e uma taxa de impostos de 18, Microsoft Dynamics 365 para operações calcula os impostos a seguir para valores fiscais diferentes.
| Valor fiscal                                    | Origem do valor | Valor real do imposto | Valor base de isenção | Outro valor base | Outro valor de imposto |
|-------------------------------------------------|---------------|-------------------------|--------------------|-------------------|------------------|
| 1. Com Crédito/Débito                            | R$ 1.000,00  | R$ 180,00              |                    |                   |                  |
| 2. Sem Crédito/Débito (Isento ou Não Tributável) |               |                         | R$ 1.000,00       |                   |                  |
| 3. sem crédito/débito (outros)                 |               |                         |                    | R$ 1.000,00      | R$ 180,00       |

Para um valor de transação de BRL 1,000.00, a taxa de impostos de 18, e a porcentagem de redução de impostos de 40, o imposto é calculado a seguir para valores fiscais diferentes.
| Valor fiscal                                    | Origem do valor | Valor real do imposto | Valor base de isenção | Outro valor base | Outro valor de imposto |
|-------------------------------------------------|---------------|-------------------------|--------------------|-------------------|------------------|
| 1. Com Crédito/Débito                            | R$ 600,00    | R$ 108,00              | R$ 400,00         |                   |                  |
| 2. Sem Crédito/Débito (Isento ou Não Tributável) |               |                         | R$ 1.000,00       |                   |                  |
| 3. sem crédito/débito (outros)                 |               |                         | R$ 400,00         | R$ 600,00        | R$ 108,00       |

Para transações de venda com códigos de tributação que têm a ** 1. em crédito/débito ** valor fiscal, ou grupos de impostos de itens para o quais ** sem crédito fiscal ** a opção não for selecionada, o valor real do imposto sobre vendas é lançado ou principal para impostos que ** ** ** e despesas de imposto estão selecionados ** ** tipo de postagem ** o campo ** para transações automáticas ** na página. Para transações de compra com códigos de tributação que têm a ** 1. em crédito/débito ** valor fiscal, ou grupos de impostos de itens para o quais ** sem crédito fiscal ** a opção não for selecionada, o valor real do imposto sobre vendas é lançado ou principal para impostos que ** ** é selecionado ** tipo de postagem ** o campo ** para transações automáticas ** na página.

## <a name="additional-resources"></a>Recursos adicionais
-   [Atributos brasileiros] de imposto (latam-bra-tax-attributes.md)
-   [Pagamentos de impostos brasileiros] (latam-bra-tax-payments.md)


