---
title: Sincronizar sob demanda com o mecanismo de preços do Supply Chain Management
description: Este tópico descreve como usar o mecanismo de preços no Microsoft Dynamics 365 Supply Chain Management do Dynamics 365 Sales.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 45a9de18a3ff9c50eba8b316171b492605d683d4
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5130644"
---
# <a name="sync-on-demand-with-the-supply-chain-management-pricing-engine"></a>Sincronizar sob demanda com o mecanismo de preços do Supply Chain Management

[!include [banner](../../includes/banner.md)]



O Microsoft Dynamics 365 Supply Chain Management inclui um mecanismo de preços que lida com acordos comerciais, listas de preços, programas de fidelidade do cliente, promoções e descontos. O mecanismo de preços usa regras complexas para determinar o melhor preço para uma determinada cotação ou ordem. Ao usar a gravação dupla, você usa os preços estáticos ou o mecanismo de preços do Dynamics 365 Supply Chain Management nas páginas Cotação e Ordem no Dynamics 365 Sales.

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a>Usar o mecanismo de preços do Supply Chain Management no Sales

1. No Sales, acesse **Vendas \> Ordens**.
2. Selecione **Novo** para criar uma ordem ou selecione uma ordem existente na lista **Minhas ordens**.
3. Adicione uma nova linha de ordem.
4. Se você estiver criando uma ordem, selecione **Ordem de preço** no Painel de Ação. Se você estiver atualizando uma ordem existente, selecione **Recalcular** no Painel de Ação.

    As seguintes colunas são preenchidas automaticamente:

    + Valor Detalhado
    + % de desconto
    + Desconto
    + Valor sem Frete
    + Valor do Frete
    + Total de Impostos
    + Valor total do CF -e-SAT
    
5. Para garantir que o sistema considera os contratos comerciais e de venda para calcular o preço:
    1. Navegue até o ambiente Supply Chain Management.
    2. Navegue até **Contas a receber \> Configuração \> Parâmetros de contas a receber**.
    3. Selecione a guia **Preços** na barra de navegação lateral.
    4. Na Guia Rápida **Avaliação de contrato comercial**, desmarque a opção **Entrada manual**.

## <a name="how-it-works"></a>Como funciona

Ao selecionar **Ordem de preço** no Sales, a função **Totais** na guia **Ordem de venda \> Exibir** no Supply Chain Management é chamada para a ordem de venda associada. Os valores no total da ordem no Sales são usados para preencher as colunas correspondentes no Supply Chain Management.

Quando o total das ordens do cliente é calculado no Supply Chain Management, o cálculo avalia os acordos comerciais e contratos de vendas existentes para o cliente e os produtos listados na ordem de venda. Essas informações são usadas para calcular os totais. Quando a **Ordem de preço** é selecionada, o Sales reflete automaticamente toda a configuração que foi feita no Supply Chain Management.

## <a name="limitations"></a>Limitações

Quando as colunas no Sales são preenchidas, as seguintes limitações se aplicam:

+ A configuração de encargos e alocações de encargos no Supply Chain Management não é replicada no Sales.
+ Os preços não consideram os preços especiais de varejo especificados na coluna **Canal de Varejo** na página da linha de ordem de venda no Supply Chain Management.
+ Os descontos definidos na seção **Gerenciamento de bonificação comercial** do Supply Chain Management não são considerados.
