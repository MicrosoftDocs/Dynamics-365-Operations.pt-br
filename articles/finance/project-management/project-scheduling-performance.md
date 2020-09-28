---
title: Desempenho de agendamento de recursos de projeto
description: Este tópico fornece informações sobre como melhorar o desempenho do planejamento de recursos para um grande número de projetos.
author: Yowelle
manager: AnnBe
ms.date: 08/31/2020
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
ms.dyn365.ops.version: 10.0.14
ms.search.validFrom: 2020-09-01
ms.openlocfilehash: 988fc83230f08a6534caa7c37784757d73c1cc12
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760479"
---
# <a name="project-resource-scheduling-performance"></a>Desempenho de agendamento de recursos de projeto

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]


Os problemas de desempenho relacionados ao planejamento de recursos podem ocorrer quando o número de projetos chega a milhares. Para melhorar o desempenho do planejamento de recursos, está disponível um recurso que permite aos usuários reduzir o tempo necessário para iniciar o formulário disponibilidade de recursos. Especificamente, isso remove o processo de sincronização de acúmulo de capacidade de recursos e usa a tabela **ResProjectResource** para acelerar a pesquisa de recursos. Observe que a tabela **ResRollup** não será mais usada.

> [!IMPORTANT]
> Se houver uma dependência no processo de sincronização de acúmulo de capacidade de recursos na tabela **ResProjectResource**, não use esse recurso.

## <a name="enable-resource-scheduling-performance-enhancement"></a>Habilitar o aperfeiçoamento de desempenho de planejamento de recursos
Para habilitar a melhoria do desempenho do agendamento de recursos, conclua as etapas a seguir.

1. Vá para **Gerenciamento de recursos** > **Tudo** e, na lista de recursos, localize **Habilitar recurso de aperfeiçoamento de desempenho do agendamento de recursos do projeto**.
2. Selecione **Habilitar agora**.

> [!NOTE]
> Se você não conseguir encontrar o recurso na lista, selecione **Verificar se há atualizações** para atualizar a lista.

3. Atualize o navegador e vá para **Gerenciamento e contabilidade de projeto** > **Periódico** > **Recursos do projeto** > **Sincronizar capacidade de calendários de recursos em todas as empresas**.
4. Defina **Remover registros de capacidade existentes** como **Sim** para remover os dados anteriores. Se desejar gerar dados incrementais, defina a opção como **Não**.
5. No campo **Código do período**, selecione o período no qual os dados devem ser gerados. Se você selecionar um código de período, não será necessário definir datas de início e término.
6. Se você deixar o campo **Código do período** em branco, selecione datas de início e término específicas para gerar dados.
7. Selecione **OK**.

 > [!NOTE]
 > Isso distribuirá dados gerais para a tabela **ResCalendarCapacity** em todas as empresas do seu ambiente, de forma que o trabalho em lotes só precise ser executado em uma entidade legal. Os dados nesse trabalho em lotes são necessários para calcular a capacidade de recursos por meio do calendário associado.

8. Vá para **Gerenciamento e contabilidade de projeto** > **Periódico** > **Recursos de projeto** > **Popular recursos de projeto em todas as empresas** e selecione **OK**. Este é o script de atualização de dados para dados gerais nas tabelas **ResProjectResource**, **ResCalendarDateTimeRange** e **ResEffectiveDateTimeRange**. Os valores do campo **PSAPRojSchedRole.RootActivity** também são atualizados. Se isso não for executado, você receberá um aviso quando tentar executar operações de agendamento de recursos.
 
## <a name="turn-off-resource-scheduling-performance-enhancement"></a>Ativar o aperfeiçoamento de desempenho de agendamento de recursos

1. Vá para **Gerenciamento de recursos** > **Tudo** e procure por **Habilitar recurso de aperfeiçoamento de desempenho do agendamento de recursos do projeto**.
2. Selecione o recurso e o botão **Desabilitar**.
3. Atualize seu navegador.
4. Vá para **Gerenciamento e contabilidade de projeto** > **Periódico** > **Sincronização de capacidade** > **Sincronizar acúmulos de capacidade de recursos**.
5. Na página **Organização de acúmulo de capacidade**, defina **Remover registros de capacidade existentes** como **Sim** para remover dados anteriores. Se desejar gerar dados incrementais, defina a opção como **Não**.
6. No campo **Código do período**, selecione o período no qual os dados devem ser gerados. Se você selecionar um código de período, não será necessário definir datas de início e término.
7. Se você deixar o campo **Código do período** em branco, selecione datas de início e término específicas para gerar dados.
8. Selecione **OK**.

> [!NOTE]
> Isso distribuirá dados gerais para a tabela **ResRollup** em todas as empresas do seu ambiente, de forma que o trabalho em lotes só precise ser executado em uma entidade legal. Esse trabalho em lotes é necessário para todas as exibições **Disponibilidade de recursos**. Se esse trabalho em lotes não for executado, os dados **ResRollup** serão gerados rapidamente, o que pode levar tempo.
