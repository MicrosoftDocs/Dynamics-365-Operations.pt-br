---
title: Listas de verificação de manutenção
description: Este tópico descreve listas de verificação de manutenção no Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderChecklist, EntAssetMobileWorkOrderLineChecklistDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 135887e4ca8dfc6cae9aa73b316815ed3a7041a9
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6347083"
---
# <a name="maintenance-checklists"></a>Listas de verificação de manutenção

[!include [banner](../../includes/banner.md)]



As listas de verificação de manutenção são configuradas em tipos de trabalho de manutenção. O preenchimento de listas de verificação de manutenção faz parte do processo de conclusão da ordem de serviço. Para obter mais informações sobre como configurar listas de verificação de manutenção em tipos de trabalho de manutenção na página **Padrões do tipo de trabalho de manutenção**, consulte [Categorias do tipo de trabalho e tipos de trabalho de manutenção, grades do tipo de trabalho de manutenção, ofício do trabalho de manutenção e listas de verificação de manutenção](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).

Quando você trabalha com listas de verificação de manutenção em uma ordem de serviço, você pode preencher as listas de verificação de manutenção predefinidas relacionadas aos tipos de trabalho de manutenção. Você também pode adicionar mais listas de verificação de manutenção.


## <a name="fill-in-a-maintenance-checklist"></a>Preencher uma lista de verificação de manutenção

1. Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Selecione a ordem de serviço e, no Painel de Ação, na guia **Ordem de serviço**, no grupo **Linhas**, selecione **Lista de verificação de manutenção**.

3. A **Lista de verificação do trabalho de manutenção da ordem de serviço** exibe as listas de verificação de todos os trabalhos da ordem de serviço. Se os trabalhos da ordem de serviço tiverem tipos de trabalho de manutenção diferentes, as listas de verificação de manutenção poderão ser diferentes para cada trabalho da ordem de serviço. Selecione um trabalho da ordem de serviço para trabalhar com lista de verificação de manutenção. Os detalhes da linha selecionada da lista de verificação de manutenção são mostrados na Guia Rápida **Detalhes da linha**.

4. Complete todas as linhas da lista de verificação de manutenção, uma de cada vez, na ordem em que aparecem. Você completa uma linha da lista de verificação de manutenção preenchendo os campos da Guia Rápida **Detalhes da linha**. As informações necessárias para completar uma linha podem variar, dependendo do tipo de linha. Por exemplo, em uma linha do tipo **Texto**, você adiciona uma observação explicando qual foi o resultado da sua verificação. Em uma linha do tipo **Medida**, você deve inserir o valor do contador lido no equipamento e também pode adicionar uma observação, se necessário. Uma linha da lista de verificação de manutenção do tipo **Cabeçalho** é usada como um título para agrupar as linhas da lista de verificação de manutenção exibidas abaixo dela. Você não precisa preencher um cabeçalho. Assim como para todos os outros tipos de linhas da lista de verificação de manutenção, você pode adicionar uma observação em uma linha do tipo **Cabeçalho**.

5. Se as instruções estiverem relacionadas a uma linha da lista de verificação de manutenção, a caixa de seleção **Instruções** será marcada. Leia as instruções para a linha selecionada da lista de verificação de manutenção no campo **Instruções** da Guia Rápida **Detalhes da linha**.

6. Quando tiver preenchido uma linha da lista de verificação de manutenção, marque a caixa de seleção **Verificado** na linha para marcá-la como concluída. Para descartar uma linha da lista de verificação de manutenção porque ela não é relevante para o trabalho da ordem de serviço, marque a caixa de seleção **N/D** na linha. Se a caixa de seleção **Obrigatório** estiver marcada em uma linha da lista de verificação de manutenção, você deverá marcar a caixa de seleção **Verificado** ou **N/D**.

>[!NOTE]
>Você só pode atualizar os registros da lista de verificação de manutenção se a ordem de serviço estiver em um estado do ciclo de vida [Ativo](../setup-for-work-orders/work-order-lifecycle-states.md).  


## <a name="add-a-maintenance-checklist-line"></a>Adicionar uma linha da lista de verificação de manutenção

As listas de verificação de manutenção são criadas com base na definição no padrão de tipo de trabalho de manutenção e transferidas para um trabalho da ordem de serviço. Se necessitar, você poderá adicionar linhas da lista de verificação de manutenção em um trabalho da ordem de serviço. As linhas da lista de verificação de manutenção adicionadas manualmente obtêm a referência **Manual**.

1. Na página **Lista de verificação do trabalho de manutenção da ordem de serviço**, selecione o trabalho da ordem de serviço para o qual você deseja adicionar uma lista de verificação de manutenção.

2. Na Guia Rápida **Linhas da lista de verificação de manutenção**, selecione uma linha da lista de verificação de manutenção. Em seguida, para inserir uma nova linha depois da linha selecionada, pressione a tecla **Seta para baixo**. O próximo número da sequência é inserido automaticamente no campo **Número da linha**. Para inserir uma nova linha antes da linha selecionada, selecione **Adicionar linha**. 

3. No campo **Nome**, insira um nome para a linha da lista de verificação de manutenção.

4. No campo **Tipo**, selecione um tipo de linha da lista de verificação de manutenção. A Guia Rápida **Detalhes da linha** contém campos relacionados para cada tipo de lista de verificação de manutenção.
    - **Texto** - Use este tipo para adicionar uma linha da lista de verificação de manutenção com o texto que descreve o que deve ser feito. Por exemplo, você pode usar este tipo se quiser que um trabalhador verifique ou inspecione algo, mas sem esperar um resultado específico (mensurável). Depois de selecionar este tipo, na Guia Rápida **Detalhes das linhas**, no campo **Instruções** , insira o texto que descreve o que deve ser feito.
    - **Cabeçalho** - Uma linha da lista de verificação de manutenção deste tipo é usada como um título para agrupar as linhas da lista de verificação de manutenção exibidas abaixo dela. Este tipo é útil se você tiver diversas linhas da lista de verificação de manutenção que podem ser divididas em áreas específicas. Após selecionar este tipo, insira um nome descritivo no campo **Nome**.
    - **Modelo** - Este tipo não é aplicável quando você adiciona manualmente uma linha da lista de verificação de manutenção em um trabalho da ordem de serviço.  
    - **Variável** - Use este tipo para definir um resultado possível em um intervalo em uma linha da lista de verificação de manutenção. Para obter informações sobre como configurar variáveis da lista de verificação de manutenção, consulte [Categorias do tipo de trabalho e tipos de trabalho de manutenção, grades do tipo de trabalho de manutenção, ofício do trabalho de manutenção e listas de verificação de manutenção](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md). Após selecionar este tipo, insira um nome descritivo para a variável no campo **Nome**. Na Guia Rápida **Detalhes da linha**, no campo **Variável**, selecione a variável. No campo **Instruções**, insira um texto que descreva o que deve ser feito.
    - **Medida** - Use este tipo para registrar uma medida específica na linha da lista de verificação de manutenção. Após selecionar este tipo, insira um nome para a medida no campo **Nome**. Na Guia Rápida **Detalhes da linha**, nos campos **Contador** e **Unidade**, selecione valores apropriados. No campo **Instruções**, insira um texto que descreva o que deve ser feito.

5. Quando terminar de adicionar manualmente as linhas da lista de verificação de manutenção, preencha as linhas conforme descrito na seção **Preencher uma lista de verificação de manutenção** acima.

>[!NOTE]
>Na página **Lista de verificação do trabalho de manutenção da ordem de serviço**, não é possível excluir linhas da lista de verificação de manutenção com a referência **Tipo de trabalho**. Só é possível excluir linhas da lista de verificação de manutenção que você ou outros funcionários de manutenção tenham criado manualmente e que tenham a referência **Manual**.

A ilustração a seguir mostra um exemplo de uma lista de verificação de manutenção.

![Figura 1.](media/14-work-orders.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]