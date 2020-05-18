---
title: Criar modelos de previsão para orçamentos de projeto
description: Este tópico descreve como criar um modelo de previsão para orçamentos restantes.
author: RadhikaRS
manager: AnnBe
ms.date: 04/24/2020
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
ms.openlocfilehash: 07e540f23a668b40a54906a67d87552fe991825a
ms.sourcegitcommit: 5de75c61c33e57c813944f1ab6100aceb020d432
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "3321770"
---
# <a name="create-forecast-models-for-project-budgets"></a>Criar modelos de previsão para orçamentos de projeto 

[!include [banner](../includes/banner.md)]

Este tópico descreve como criar um modelo de previsão para orçamentos restantes. Um projeto que está sujeito ao controle de orçamento usa dois tipos de orçamentos: original e restante. Ao criar um orçamento de projeto, você deve especificar os modelos de previsão de orçamento original e restante que foram criados na página **Modelos de previsão**. Os orçamentos de projeto baseados nos modelos especificados são criados quando você compromete o orçamento do projeto.

> [!NOTE]
> Um modelo de previsão usado para controle de orçamento não pode ter um submodelo ou ser usado como um submodelo.

1. Selecione **Gerenciamento e contabilidade do projeto** > **Configuração** > **Previsões**  > **Modelos de previsão**.
2. Selecione **Novo** para criar um novo modelo de previsão e insira um número de ID de modelo e um nome para o novo modelo. 
3. Defina a opção **Interrompido** como **Sim** para impedir qualquer alteração nas linhas de previsão para o modelo de previsão. 
4. Se as linhas de previsão às quais o modelo está associado devem gerar previsões de fluxo de caixa na contabilidade, defina **Incluir em previsões de fluxo de pagamento à vista** como **Sim**. 
5. Para usar a data do projeto como a data da nota fiscal, defina **Data da previsão da nota fiscal** como **Sim**. 
6. No campo **Tipo de orçamento**, selecione um dos seguintes tipos de modelo:

   - **Orçamento original**: use os valores do orçamento original que são comprometidos quando o orçamento inicial é criado e aprovado.
   - **Orçamento restante**: use os valores do orçamento restante durante a vida útil do projeto. Os saldos neste modelo de previsão são reduzidos por transações reais e aumentados ou reduzidos por revisões de orçamento.
   - **Postergação**: use os valores de orçamento mantido para uso futuro do projeto. Postergar é um processo opcional que pode ser executado para transferir valores de orçamento não utilizados de um ano fiscal para outro.

7. Defina as seguintes opções, conforme necessário:

   - Habilite **Data da previsão da nota fiscal** para usar a data do projeto como a data da nota fiscal.
   - Habilite **Previsão com WIP** para previsão com base no trabalho em andamento (WIP) e selecione o tipo de WIP. 
   - Você pode manter o **Tipo de orçamento** padrão como **Nenhum** ou inserir um novo tipo. O tipo de orçamento não pode ser alterado depois que um registro é alterado.     
    > [!NOTE]
    > Se você alterar o tipo de orçamento padrão, todas as outras opções se tornarão indisponíveis para atualizações e não será possível reutilizar esse modelo de previsão. 
   


 

