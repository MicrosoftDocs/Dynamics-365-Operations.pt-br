---
title: Sincronizar com o mecanismo de preços sob demanda do Dynamics 365 Supply Chain Management
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 5ffc0358ff58b2a05aa84b4467a27d88b5e1ec42
ms.sourcegitcommit: 984604fd651d74aa49a2d7513f096faaf49f9f27
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2020
ms.locfileid: "3270327"
---
# <a name="sync-with-the-dynamics-365-supply-chain-management-pricing-engine-on-demand"></a>Sincronizar com o mecanismo de preços sob demanda do Dynamics 365 Supply Chain Management

[!include [banner](../../includes/banner.md)]



O Microsoft Dynamics 365 Supply Chain Management inclui um mecanismo de preços que lida com acordos comerciais, listas de preços, programas de fidelidade do cliente, promoções e descontos. O mecanismo de preços usa regras complexas para determinar o melhor preço para uma determinada cotação ou ordem. Ao usar a gravação dupla, você usa os preços estáticos ou o mecanismo de preços do Dynamics 365 Supply Chain Management nas páginas Cotação e Ordem no Dynamics 365 Sales.

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a>Usar o mecanismo de preços do Supply Chain Management no Sales

1. No Sales, acesse **Vendas \> Ordens**.
2. Selecione **Novo** para criar uma ordem ou selecione uma ordem existente na lista **Minhas ordens**.
3. Adicione uma nova linha de ordem.
4. Se você estiver criando uma ordem, selecione **Ordem de preço** no Painel de Ação. Se você estiver atualizando uma ordem existente, selecione **Recalcular** no Painel de Ação.

    Os seguintes campos são preenchidos automaticamente:

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

Ao selecionar **Ordem de preço** no Sales, a função **Totais** na guia **Ordem de venda \> Exibir** no Supply Chain Management é chamada para a ordem de venda associada. Os valores no total da ordens no Sales são usados para preencher os campos correspondentes no Supply Chain Management.

Quando o total das ordens do cliente é calculado no Supply Chain Management, o cálculo avalia os acordos comerciais e contratos de vendas existentes para o cliente e os produtos listados na ordem de venda. Essas informações são usadas para calcular os totais. Quando a **Ordem de preço** é selecionada, o Sales reflete automaticamente toda a configuração que foi feita no Supply Chain Management.

## <a name="limitations"></a>Limitações

Quando os campos no Sales são preenchidos, as seguintes limitações se aplicam:

+ A configuração de encargos e alocações de encargos no Supply Chain Management não é replicada no Sales.
+ Os preços não consideram os preços especiais de varejo especificados no campo **Canal de Varejo** na página da linha da ordem do cliente no Supply Chain Management.
+ Os descontos definidos na seção **Gerenciamento de bonificação comercial** do Supply Chain Management não são considerados.
