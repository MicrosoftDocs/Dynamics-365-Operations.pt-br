---
title: Criar e aplicar condições de retenção de pagamento de fornecedor
description: Este tópico fornece informações sobre como configurar e manter condições de retenção para pagamentos de fornecedores.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 0e14050a79220b5d02763a025040edb934489d00
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410193"
---
# <a name="create-and-apply-vendor-payment-retention-terms"></a>Criar e aplicar condições de retenção de pagamento de fornecedor

[!include [banner](../includes/banner.md)] 

A configuração de condições de retenção de pagamento de fornecedor para um projeto é útil quando sua organização deseja reter parte dos pagamentos feitos a um fornecedor. Por exemplo, quando você deseja reter o pagamento a um fornecedor até que os produtos entregues atendam às suas expectativas. As condições de retenção de pagamento ao fornecedor podem ser especificadas quando você negocia um contrato com o fornecedor.

## <a name="create-vendor-payment-retention-terms"></a>Criar condições de retenção de pagamento ao fornecedor

Você pode inserir a porcentagem do pagamento do fornecedor para retenção e a porcentagem dos valores retidos anteriormente a serem liberados. Os valores serão retidos automaticamente nas faturas de fornecedor até que o contrato atinja o estado de conclusão específico. Depois de configurar as condições de retenção, você pode aplicá-las a qualquer projeto para esse fornecedor.

Use as etapas a seguir para configurar e manter condições de retenção para pagamentos de fornecedores. 

1. Vá para **Gerenciamento e contabilidade do projeto** > **Retenção** > **Condições de retenção de pagamento de fornecedor**.
2. Selecione **Novo** para adicionar uma nova condição de retenção do fornecedor. O valor da **ID da regra** da nova condição é inserida automaticamente. 
3. Insira uma breve descrição no campo **Descrição** e, na FastTab **Condições**, selecione **Adicionar linha** para inserir valores de condições para:

   - **Porcentagem de unidades entregues**: insira uma porcentagem de conclusão da condição. Os valores serão retidos automaticamente nas faturas do fornecedor até que o estágio de projeto da conclusão seja igual à porcentagem especificada. Por exemplo, se você inserir 50,00, os valores serão retidos até que o projeto esteja 50% concluído.
   - **Porcentagem a reter**: insira uma porcentagem do valor da fatura do fornecedor a ser retido. Por exemplo, se você digitar 10,00 nesse campo, 10% do valor em uma fatura de fornecedor serão retidos até que o projeto atinja a porcentagem de conclusão definida no campo **Porcentagem de unidades entregues**.
   - **Porcentagem a liberar**: selecione **Adicionar linha** para inserir uma porcentagem dos valores retidos anteriormente a serem liberados para o nível de conclusão do projeto selecionado.

> [!NOTE]
> Se houver mais de uma etapa para diferentes níveis de conclusão de projeto, insira uma linha separada de condição de retenção do fornecedor para cada regra de retenção. Cada linha pode especificar uma porcentagem de retenção diferente e uma porcentagem de liberação diferente para cada nível designado de conclusão do projeto.

Depois de criar condições de retenção de fornecedor para um fornecedor, você poderá as condições a um projeto.

## <a name="apply-vendor-retention-terms-to-a-project"></a>Aplique condições de retenção de fornecedor a um projeto

1. Vá para **Gerenciamento e contabilidade do projeto** > **Projetos** > **Todos os projetos** e abra um projeto na página de listagem de projetos.
2. Na guia rápida **Contratos de fornecedor**, selecione **Adicionar linha**.
3. No campo **Código da conta**, selecione uma das seguintes opções: 

   - **Tabela**: as condições de retenção de fornecedor se aplicam a um único fornecedor.
   - **Grupo**: as condições de retenção de fornecedor se aplicam a todos os fornecedores em um grupo de fornecedores.
   - **Todos**: as condições de retenção de fornecedor se aplicam a todos os fornecedores.

4. No campo **Fornecedor/grupo de fornecedores**, selecione o fornecedor ou grupo de fornecedores aos quais as condições de retenção de fornecedor se aplicam. Se você selecionar **Todos** na etapa anterior, esse campo não estará disponível.
5. No campo **Condições de retenção do fornecedor**, selecione as condições de retenção que você criou no no procedimento anterior.
6. Se o projeto também tiver as condições de pagamento quando pago (PWP) configuradas para o fornecedor, insira a porcentagem de limite do projeto no campo **Porcentagem de limite PWP**.

As condições da retenção do fornecedor também são exibidas nas ordens de compra criadas para o fornecedor.
