---
title: Listas de verificação de manutenção
description: Este tópico descreve listas de verificação de manutenção no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 325ff1fa0811d6aac5189cc69f21483fce6b3e8f
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875510"
---
# <a name="maintenance-checklists"></a>Listas de verificação de manutenção


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

As listas de verificação de manutenção são configuradas em tipos de trabalho de manutenção e usadas quando você trabalha em uma ordem de serviço. O preenchimento de listas de verificação de manutenção faz parte da conclusão da ordem de serviço. Consulte a seção [Categorias do tipo de trabalho e tipos de trabalho de manutenção, grades do tipo de trabalho de manutenção, comércios de trabalho de manutenção e listas de verificação de manutenção](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md) para obter mais informações sobre como configurar listas de verificação de manutenção nos tipos de trabalho de manutenção no formulário **Padrões do tipo de trabalho de manutenção**.

Quando você trabalha com listas de verificação de manutenção em uma ordem de serviço, você pode preencher as listas de verificação de manutenção predefinidas relacionadas aos tipos de trabalho de manutenção. Também é possível incluir listas de verificação de manutenção adicionais.

## <a name="fill-out-a-maintenance-checklist"></a>Preencha uma lista de verificação de manutenção

1. Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Selecione a ordem de serviço e clique em **Lista de verificação de manutenção**.

3. Na **Lista de verificação do trabalho de manutenção da ordem de serviço**, você verá listas de verificação de manutenção para todos os trabalhos da ordem de serviço. Se os trabalhos da ordem de serviço tiverem tipos de trabalho de manutenção diferentes, as listas de verificação de manutenção podem ser diferentes em cada trabalho da ordem de serviço. Selecione um trabalho da ordem de serviço para trabalhar com lista de verificação de manutenção. Os detalhes de uma linha selecionada da lista de verificação de manutenção são mostrados na Guia Rápida **Detalhes da linha**.

4. Conclua todas as linhas de lista de verificação de manutenção, uma de cada vez, na ordem sequencial em que são mostradas. Uma linha da lista de verificação de manutenção tipo "Cabeçalho" será usada como um título para agrupar as linhas da lista de verificação de manutenção abaixo. Não é necessário preencher um cabeçalho, mas, como em todos os tipos de linhas da lista de verificação de manutenção, é possível adicionar **Observação** ao cabeçalho.

5. Se as instruções estiverem relacionadas a uma linha da lista de verificação de manutenção, a caixa de seleção **Instruções** será marcada. Leia as instruções para a linha da lista de verificação de manutenção selecionada na seção **Detalhes da linha** Guia rápida > **Instruções**.

6. As informações necessárias para concluir uma linha de lista de verificação de manutenção pode variar, dependendo do tipo da lista de verificação de manutenção. Você completa uma linha da lista de verificação de manutenção preenchendo os campos da Guia Rápida **Detalhes da linha**. Por exemplo, em uma linha do tipo "Texto", você adiciona uma **Observação** explicando qual foi o resultado dessa linha da lista de verificação. Em uma linha do tipo "Medida", você adiciona o **Valor do contador** que você lê no equipamento e também pode adicionar uma **Observação**, se necessário.

- Quando tiver preenchido uma linha da lista de verificação de manutenção, marque a caixa de seleção **Marcada** na linha para marcá-la como concluída. Se quiser descartar uma linha da lista de verificação de manutenção porque ela não é relevante para o trabalho da ordem de serviço, marque a caixa de seleção **N/A** na linha. Se uma linha de lista de verificação de manutenção for marcada como **Obrigatória**, você deverá marcá-la como "Marcada" ou "N/A".  
- Você só pode atualizar os registros da lista de verificação de manutenção se a ordem de serviço estiver em um estado do ciclo de vida [Ativo](../setup-for-work-orders/work-order-lifecycle-states.md).  


## <a name="add-a-maintenance-checklist-line"></a>Adicionar uma linha da lista de verificação de manutenção

As listas de verificação de manutenção são criadas do padrão de definição de tipo de trabalho de manutenção e transferidas para um trabalho de ordem de serviço. Se necessário, você pode adicionar linhas da lista de verificação de manutenção para um trabalho da ordem de serviço. As linhas da lista de verificação de manutenção adicionadas manualmente obtêm a referência "Manual".

1. Na **Lista de verificação do trabalho de manutenção da ordem de serviço**, selecione o trabalho da ordem de serviço para o qual você deseja adicionar uma lista de verificação de manutenção.

2. Na Guia Rápida **Linhas da lista de verificação de manutenção**, selecione uma linha da lista de verificação de manutenção e pressione o botão de seta para baixo de seu teclado, se quiser inserir uma nova linha após a linha da lista de verificação de manutenção selecionada. O próximo número da sequência é inserido automaticamente no campo **Número da linha**. Você também pode selecionar uma linha de lista de verificação de manutenção e clicar no botão **Adicionar linha** se quiser inserir uma nova linha acima da linha de lista de verificação de manutenção selecionada.

3. Insira um nome para a linha da lista de verificação de manutenção no campo **Nome**.

4. No campo **Tipo**, selecione um tipo de linha da lista de verificação de manutenção. Para cada tipo de lista de verificação de manutenção, os campos relacionados são mostrados na Guia Rápida **Detalhes da linha**.  
  a. O “texto” é usado para adicionar uma linha da lista de verificação de manutenção com uma descrição de texto sobre o que fazer. Este tipo de lista de verificação de manutenção pode ser usado se você quiser que um trabalhador verifique ou inspecione algo, sem esperar um resultado específico (mensurável). Insira uma descrição do que fazer na seção **Instruções** na Guia Rápida **Detalhes da linha**. b. "Cabeçalho" é usado como um título para agrupar as linhas da lista de verificação de manutenção mostradas abaixo do cabeçalho. Isso é útil se você tem diversas linhas da lista de verificação de manutenção que podem ser divididas em áreas específicas. Insira um nome descritivo no campo **Nome**.  
  c. O "modelo" não é aplicável quando você adiciona uma linha da lista de verificação de manutenção manualmente em um trabalho da ordem de serviço.  
  d. "Variável” é usada para definir um resultado possível em um intervalo em uma linha da lista de verificação de manutenção. A configuração de variáveis da lista de verificação de manutenção é descrita em [Categorias do tipo de trabalho e tipos de trabalho de manutenção, grades do tipo de trabalho de manutenção, comércios de trabalho de manutenção e listas de verificação de manutenção](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md). Insira um nome para descreve a variável no campo **Nome**. Selecione a variável no campo **Variável**. Insira uma descrição do que fazer na seção **Instruções** na Guia Rápida **Detalhes da linha**.  
  e. "Medição" é usada para registrar uma medição específica. Insira um nome para a medição no campo **Nome**. Na Guia Rápida **Detalhes da linha**, selecione **Contador** e **Unidade**. Insira uma descrição do que fazer na seção **Instruções**.  

5. Quando concluir a adição de linhas da lista de verificação de manutenção manualmente, preencha as linhas, conforme descrito na seção acima.

>[!NOTE]
>Na **Lista de verificação do trabalho de manutenção da ordem de serviço**, você não pode excluir linhas da lista de verificação de manutenção com o "tipo de cargo" de referência. Você só pode excluir linhas da lista de verificação de manutenção com a referência "Manual" que você ou outros funcionários de manutenção criaram manualmente.


![Figura 1](media/14-work-orders.png)

