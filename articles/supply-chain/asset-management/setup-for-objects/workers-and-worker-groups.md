---
title: Funcionários de manutenção e grupos de trabalhadores
description: Este tópico explica os funcionários de manutenção e os grupos de trabalhadores no Gerenciamento de ativos.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetWorkerGroupCopyFromResourceGroup, EntAssetWorkerGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 553dce8df5e91cce58b64e340d8ff72586d8d46d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838553"
---
# <a name="maintenance-workers-and-worker-groups"></a>Funcionários de manutenção e grupos de trabalhadores

[!include [banner](../../includes/banner.md)]

 

Este tópico explica os funcionários de manutenção e os grupos de trabalhadores no Gerenciamento de ativos. No Gerenciamento de ativos, você pode conectar funcionários de manutenção a locais funcionais. (Para obter mais informações sobre locais funcionais, consulte [Criar locais funcionais](../functional-locations/create-functional-locations.md).) Esta funcionalidade pode ser útil se, por exemplo, você estiver agendando um trabalho de manutenção em um computador que localizado em um local funcional 01 e quiser alocar funcionários de manutenção do mesmo local para executar o trabalho.

Você também pode criar grupos de funcionários de manutenção e associar funcionários de manutenção a eles. Essa funcionalidade será útil quando você fizer o agendamento de ordem de serviço simples e quiser agendar um grupo de funcionários de manutenção em uma ordem de serviço. Você pode usar os funcionários de manutenção e os grupos de funcionários de manutenção para configurar funcionários de manutenção preferenciais e funcionários de manutenção responsáveis. 


## <a name="create-workers"></a>Criar trabalhadores

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Trabalhadores** \> **Trabalhadores**.
2. Selecione **Novo** para adicionar um trabalhador à lista.
3. No campo **Trabalhador**, selecione o trabalhador.
4. Defina a opção **Ativo** como **Sim** para agendar o trabalhador em ordens de serviço.

    Na Guia Rápida **Geral**, os campos **Recurso** e **Descrição** serão preenchidos automaticamente se um determinado recurso foi selecionado para o trabalhador. O campo **Calendário** também será preenchido automaticamente, uma vez que você tenha configurado o trabalhador como um recurso e alocado um calendário para o recurso na página **Recursos** (**Administração da organização** \> **Recursos** \> **Recursos**).

5. Na Guia Rápida **Grupos**, selecione **Adicionar** e selecione um grupo de funcionários de manutenção para o trabalhador. Um trabalhador pode ser afiliado a mais de um grupo.
6. Na configuração padrão, a afiliação de um trabalhador a um grupo é válida a partir da data em que você adiciona o grupo e ela nunca expira. Essa data é exibida no campo **Efetivação**. Para ver o campo **Efetivação**, selecione **Exibir** \> **Tudo**. Se a afiliação do trabalhador a um grupo estiver limitada a um determinado período, use os campos **Efetivação** e **Término** para definir o período.
7. Na Guia Rápida **Locais funcionais**, selecione **Adicionar** e selecione um local funcional para o funcionário de manutenção. Também especifique qual é o local funcional principal para o trabalhador.

    > [!NOTE]
    > Ao adicionar locais funcionais a um trabalhador, todos os ativos em ação relacionados a esses locais funcionais aparecem em vários itens de menu, como **Meus ativos em ação** e **Meus locais funcionais ativos**. Também aparecem nas pesquisas de ativo que são exibidas quando você cria um novo ativo, solicitação de manutenção ou ordem de serviço.

    Os campos na Guia Rápida **Detalhes** mostram o número de grupos de funcionários de manutenção e de locais funcionais aos quais o funcionário de manutenção selecionado está relacionado.

## <a name="create-worker-groups"></a>Criar grupos de trabalhadores

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Trabalhadores** \> **Grupos de funcionários de manutenção**.
2. Selecione **Novo** para adicionar um grupo de trabalhadores à lista.
3. No campo **Grupo de funcionários de manutenção**, insira uma ID de grupo.
4. No campo **Nome**, insira um nome.
5. Na Guia Rápida **Trabalhadores**, selecione **Adicionar** e selecione um funcionário de manutenção para o grupo de trabalhadores. Para obter informações sobre os campos **Efetivação** e **Término**, consulte a etapa 6 no procedimento anterior.
6. Se um grupo de recursos deve estar relacionado ao grupo de funcionários de manutenção selecionado, selecione **Copiar do grupo de recursos**. No campo **Grupo**, selecione o grupo de recursos do qual as configurações de calendário serão copiadas. Em seguida, no campo **Grupo de trabalhadores**, selecione o grupo de trabalhadores para o qual as configurações de calendário do grupo de recursos serão copiadas. Esta etapa é relevante somente se você quiser que os funcionários de manutenção usem o calendário que está relacionado a um recurso (centro de trabalho) durante o agendamento da ordem de serviço.

    O campo na Guia Rápida **Detalhes** mostra o número de funcionários de manutenção que foram definidos no grupo de funcionários de manutenção selecionado.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]