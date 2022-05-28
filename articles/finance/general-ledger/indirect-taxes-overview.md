---
title: Visão geral de imposto
description: Este tópico fornece uma visão geral do sistema de imposto. Explica os elementos da configuração do imposto sobre vendas e como trabalham em conjunto.
author: kailiang
ms.date: 10/28/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: TaxAuthority, TaxPeriod, TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom:
- "13111"
- intro-internal
ms.assetid: fe5fdc7f-9834-49fb-a611-1dd9c289619d
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 19d235a761ffdfcfb945f7f6213dc8ec44f73aab
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727584"
---
# <a name="sales-tax-overview"></a>Visão geral de imposto

[!include [banner](../includes/banner.md)]

Este tópico fornece uma visão geral do sistema de imposto. Explica os elementos da configuração do imposto sobre vendas e como trabalham em conjunto.

## <a name="overview"></a>Visão Geral

A estrutura de imposto dá suporte a muitos tipos de impostos indiretos, como imposto sobre vendas, imposto sobre valor agregado (VAT), imposto de bens e serviços (GST), taxas com base em unidades e retenção de imposto. Estes impostos são calculados e documentados as transações de compra e vendas. Periodicamente, eles devem ser reportados e pagos às autoridades do imposto. 

O diagrama a seguir mostra as entidades da configuração de imposto e a forma como estão relacionadas.

[![Diagrama mostrando a visão geral de entidades de configuração de impostos.](./media/taxoverview1-300x209.jpg)](./media/taxoverview1.jpg) 

Para cada imposto que uma empresa deve ser responsável, deve ser definido um código de imposto. Um código de imposto sobre vendas armazena as taxas de imposto e as regras de cálculo do imposto sobre vendas. 

Cada código de imposto sobre vendas deve ser vinculado a um período de liquidação de impostos sobre vendas. Os períodos de liquidação de impostos sobre vendas definem os intervalos nos quais o imposto sobre vendas deve ser reportado e pago à autoridade de imposto sobre vendas. Cada período de liquidação de imposto sobre vendas deve ser atribuído a uma autoridade de imposto sobre vendas. Uma autoridade de imposto sobre vendas representa a entidade à qual o imposto sobre vendas é reportado e pago. Ela também define o layout do relatório de imposto sobre vendas. As autoridades de imposto sobre vendas podem estar relacionadas a contas de fornecedor. Para saber mais, consulte [Configurar períodos de liquidação do imposto](tasks/set-up-sales-tax-settlement-periods.md).

Cada código de imposto sobre vendas também deve estar vinculado a um grupo de lançamento contábil. Um grupo de lançamento contável especifica as contas principais nas quais os valores dos códigos de imposto sobre vendas serão lançados. 

Códigos de relatório de imposto sobre vendas opcionais também podem ser definidos. Eles podem ser atribuídos em códigos de imposto sobre vendas para vários tipos do valor que são calculados para o código do imposto sobre vendas. O relatório **Pagamento de imposto sobre vendas por código** mostra os totais por código de relatório de imposto para um determinado período e intervalo de liquidação de imposto sobre vendas. 

Cada transação para qual o imposto sobre vendas precisa ser calculado e lançado deve ter um grupo de impostos sobre vendas e um grupo de impostos sobre vendas de item. Os grupos de impostos sobre vendas estão relacionadas ao participante (por exemplo, cliente ou fornecedor) da transação, enquanto os grupos de impostos sobre vendas de item estão relacionados ao recurso (por exemplo, categoria de item ou aquisição) da transação. Os grupos de impostos contêm uma lista dos códigos de imposto. Os códigos de imposto que estão presentes no grupo de imposto sobre vendas e no grupo de imposto sobre vendas de item para uma transação são os códigos de imposto que se aplicam a essa transação. 

A tabela a seguir descreve as entidades e a sequência para a configuração de imposto.

| Atividade de configuração                                                  | Necessária/Opcional e descrição                                                                                                                                                                                                                                                                                         |
|-----------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Criar contas principais.                                           | Necessário. Antes de configurar a funcionalidade de imposto sobre vendas, as contas principais usadas pela empresa para pagar e registrar impostos deve ser criada.                                                                                                                                                                             |
| Configurar grupos de lançamento contábil do imposto.                     | Necessário. Os grupos de lançamentos contábeis definem as contas principais para registrar e pagar impostos sobre vendas.   Para saber mais, consulte [Configurar grupos de lançamentos do Razão para impostos](tasks/set-up-ledger-posting-groups-sales-tax.md).                                                                                 |
| Configurar autoridades de imposto.                                   | Necessário. As autoridades de impostos sobre vendas são as entidades para as quais o imposto deve ser informado e pago.    Para saber mais, consulte [Configurar autoridades de imposto](tasks/set-up-sales-tax-authorities.md).                                                                                                                                          |
| Configurar períodos de liquidação do imposto.                            | Necessário. Os períodos de liquidação do imposto sobre vendas contêm informações sobre quando e com que frequência os impostos sobre vendas devem ser reportados e pagos. Estão relacionadas a uma autoridade de imposto sobre vendas.                                                                                                                                                       |
| Defina códigos de isenção de imposto sobre vendas.                               | Opcional. Os códigos de relatório de imposto sobre vendas podem ser atribuídos aos códigos de imposto sobre vendas para reportar valores para diversos códigos de imposto sobre vendas sob um código de relatório de imposto sobre vendas. Para saber mais, consulte [Configurar códigos de relatório de imposto](tasks/set-up-sales-tax-reporting-codes.md).                                         |
| Configurar códigos de imposto.                                         | Necessário. Os códigos de imposto sobre vendas contém as taxas de imposto e as regras de cálculo para cada imposto sobre vendas. Os códigos de imposto sobre vendas estão relacionados a um período de liquidação de imposto sobre vendas e um grupo de lançamento contábil. Para saber mais, consulte [Configurar códigos de relatório de imposto](tasks/set-up-sales-tax-codes.md).                                |
| Configurar grupos de impostos.                                        | Necessário. Os grupos de impostos sobre vendas contém uma lista de códigos de venda que se aplicam ao participante (cliente ou fornecedor) de uma transação. Para uma determinada transação, a intersecção dos códigos de imposto sobre vendas no grupo de impostos sobre vendas e o grupo de impostos sobre vendas de item determina os códigos de imposto sobre vendas que se aplicam a essa transação.                  |
| Configurar grupos de impostos do item.                                   | Necessário. Os grupos de impostos sobre vendas de itens contêm uma lista de códigos de vendas que se aplicam ao recurso (produtos, serviços, e assim por diante) de uma transação. Para uma determinada transação, a intersecção dos códigos de imposto sobre vendas no grupo de impostos sobre vendas e o grupo de impostos sobre vendas de item determina os códigos de imposto sobre vendas que se aplicam a essa transação. Para saber mais, consulte [Configurar grupos de impostos e grupos de impostos de item](tasks/set-up-sales-tax-groups-item-sales-tax-groups.md). |
| Configure os parâmetros de imposto sobre vendas nas páginas de parâmetros do aplicativo. | Necessário. As áreas diferentes, como a Contabilidade, Contas a receber, e Contas a pagar, devem configurar parâmetros para o cálculo correto de taxas indiretas. Embora a maioria desses parâmetros tenha valores padrão, eles devem ser alterados de acordo com as necessidades de cada empresa.                                          |

## <a name="sales-tax-on-transactions"></a>Imposto sobre vendas em transações
Em cada transação (linhas de documento de compra/venda, diários, e assim por diante), você deve inserir um grupo de impostos sobre vendas e um grupo de impostos sobre vendas de item para calcular o imposto sobre vendas. Os grupos padrão são especificados nos dados mestre (por exemplo, cliente, fornecedor, item, e categoria de aquisição), mas você pode alterar manualmente os grupos em uma transação, se necessário. Os dois grupos contêm uma lista de códigos de imposto sobre vendas, e a interseção das duas listas de códigos de imposto sobre vendas determina a lista dos códigos de imposto sobre vendas aplicáveis para a transação. 

Em cada transação, você pode pesquisar o imposto sobre vendas calculado abrindo a página **Transação de imposto**. Você pode pesquisar os impostos sobre vendas para uma linha do documento ou para o documento todo. Para certos documentos (por exemplo, faturas de fornecedor e diários gerais), você pode ajustar o imposto sobre vendas calculado se o documento original mostrar os valores de desvio.

## <a name="sales-tax-settlement-and-reporting"></a>Liquidação e relatório de imposto sobre vendas
O imposto sobre vendas deve ser reportado e pago às autoridades fiscais em intervalos regulares (mensal, trimestral, e assim por diante). Você pode liquidar as contas de impostos para o intervalo e compensar os saldos da conta de liquidação de impostos, conforme especificado nos grupos de lançamentos contábeis. Você pode acessar essa funcionalidade na página **Liquidar e lançar imposto**. Especifique o período de liquidação do imposto no qual o imposto deve ser liquidado. 

Após os impostos sobre vendas serem pagos, o saldo na conta de liquidação de impostos sobre vendas deve ser equilibrado em relação à conta bancária. Se a autoridade fiscal que estiver especificada no período de liquidação de imposto estiver relacionada a uma conta de fornecedor, o saldo do imposto será lançado como uma fatura de fornecedor aberta e poderá ser incluído na proposta de pagamento regular.

## <a name="conditional-sales-tax"></a>Imposto condicional
O imposto condicional é um imposto que é pago proporcionalmente ao valor real que é pago em uma fatura. Por outro lado, o imposto padrão é calculados no momento do faturamento. O imposto condicional deve ser pago à autoridade de imposto quando o pagamento é lançado, e não quando a fatura é lançada. Quando a fatura é lançada, a transação deve ser informada no relatório do registro de imposto. No entanto, a transação deve ser excluída do relatório de pagamento de imposto. 

Se você marcar a caixa de seleção Imposto condicional no formulário Parâmetros da Contabilidade, nenhum imposto poderá ser deduzido até que você pague a fatura. Essa é uma exigência legal em alguns países/regiões.

> [!NOTE]
> Quando marcar a caixa de seleção Imposto condicional, você deverá configurar códigos de imposto e grupos de imposto, além de criar grupos de lançamento do razão, para oferecer suporte à funcionalidade. |

###  <a name="example"></a>Exemplo

Você liquida impostos mensalmente. No dia 15 de junho, você cria uma fatura de cliente 10.000, mais o imposto.
-   O imposto é de 25%, ou 2.500.
-   O pagamento da fatura vence em 30 de julho.

Você normalmente tem de liquidar e pagar 2.500 à autoridade fiscal quando a fatura é lançada em junho, mesmo que não tenha recebido o pagamento do cliente. 

Entretanto, usando o imposto condicional, você liquida a dívida com a autoridade fiscal quando recebe o pagamento do cliente em 30 de julho.

### <a name="postdated-check"></a>Cheque pós-datado

Se você usar o cheque pré-datado como forma de pagamento, quando o pagamento for criado, a conta bancária não será apagada. Em alguns países, o IVA se torna um passivo "realizado" quando o pagamento apaga o banco, o que significa que o cheque pré-datado é liquidado. Você pode habilitá-lo selecionando **Realizar o imposto condicional quando cheques pré-datados são sacados** em **Gerenciamento de caixa e bancos > Configurar > Parâmetros de gerenciamento de caixa e bancos > Cheques pré-datados**.

Para saber mais, consulte [Configurar imposto retido na fonte](tasks/set-up-withholding-tax.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
