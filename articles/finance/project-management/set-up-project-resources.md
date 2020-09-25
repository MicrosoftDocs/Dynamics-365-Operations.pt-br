---
title: Configurar recursos do projeto
description: Este tópico fornece informações sobre como configurar ou solicitar recursos de projeto.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c882e23794e3937f85b3e73774b36deaf28ac3ed
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760478"
---
# <a name="set-up-project-resources"></a>Configurar recursos do projeto

[!include [banner](../includes/banner.md)]

Você deve configurar um calendário e associá-lo a um funcionário ou a um trabalhador. O calendário é usado para agendar o projeto e o horário de trabalho dos recursos reservados para o projeto. Durante a configuração de calendário, os gerentes de projeto podem fazer o nivelamento de recursos como parte da otimização de recursos. Com base na agenda de calendário, as restrições podem ser colocadas nos recursos. Você pode configurar um calendário na página **Calendários**.

Quando você configura um trabalhador como um recurso de projeto, você pode selecionar os trabalhadores que trabalham na empresa para a qual você está configurando recursos. Se preferir, você pode selecionar trabalhadores de outras empresas de sua organização. Esses trabalhadores são conhecidos como recursos intercompanhia.

Os procedimentos a seguir explicam como configurar um trabalhador como um recurso de projeto em sua empresa e como configurar um recurso intercompanhia do projeto.

## <a name="set-up-a-worker-as-a-project-resource"></a>Configurar um trabalhador como um recurso do projeto

1. Na página **Trabalhadores**, na lista **Trabalhadores**, selecione o trabalhador que você está adicionando como um recurso de projeto e abra o registro do trabalhador.
2. No Painel de Ação, selecione **Projeto** &gt; **Configuração** &gt; **Configuração do projeto**.
3. Selecione um calendário e feche a página.

Você também pode especificar projetos padrão para um recurso como um tipo de atribuição prévia. As atribuições prévias podem ser usadas quando o gerente de recurso ou o gerente de projeto sabem com antecedência em quais projetos o recurso trabalhará. As atribuições prévias também podem ser baseadas na solicitação de um patrocinador ou de um cliente do projeto. Para atribuir um projeto previamente, na página **Atribuir projetos**, na guia **Projetos**, na lista **Projetos restantes**, selecione o projeto apropriado.

## <a name="set-up-an-intercompany-resource"></a>Configurar um recurso intercompanhia

Quando configurar um trabalhador como um recurso intercompanhia, você deve concluir a instalação na empresa de crédito e na empresa de empréstimo.

### <a name="in-the-lending-company"></a>Na empresa de crédito

1. No Finance, verifique se a empresa de crédito está selecionada e conclua o procedimento da seção anterior, "Configurar um trabalhador como um recurso de projeto."
2. Na página **Contabilização intercompanhia** , selecione **Novo**.
3. No campo **ID de entidade legal**, selecione a empresa de crédito. Preencha os campos restantes conforme apropriado e selecione **Salvar**.
4. Na página **Transferir preço** , selecione **Novo**.
5. No campo **Entidade legal que toma o empréstimo**, selecione a empresa apropriada.
6. Para emprestar à empresa de empréstimo somente o recurso que você criou no início desta seção , no campo **Recurso**, selecione o nome do recurso criado. Para tornar todos os recursos na empresa de crédito disponíveis para a empresa de empréstimo, deixe o campo **Recurso** em branco.
7. Na página **Parâmetros de gerenciamento e contabilidade de projetos.**, na guia **Intercompanhia**, defina a opção **Habilitar quadro de horários e agendamento de recursos intercompanhia** como **Sim**.

### <a name="in-the-borrowing-company"></a>Na empresa de empréstimo

- Na página **Lista de recursos**, no filtro de pesquisas, insira o nome do recurso que você criou para a empresa de crédito para verificar se o nome está incluído na lista de recurso da empresa de empréstimo.

## <a name="request-project-resources"></a>Solicitar recursos de projeto
A funcionalidade de agendamento do recurso de projeto permite apenas gerentes de recurso para distribuir recursos recrutados em compromissos ou projetos. Para habilitar essa funcionalidade, conclua as seguintes tarefas ou verifique se elas foram preenchidas:

- Configure as sequências numéricas.
- Configurar fluxos de trabalho para gerenciamento e contabilidade de projetos.
- Habilitar fluxos de trabalho de solicitação de recurso.

Depois que as tarefas precedentes forem concluídas, você pode completar estas tarefas quando necessário:

- Criar uma solicitação de um recurso recrutado de modo flexível
- Monitorar solicitações de recurso.
- Preencher solicitações de recurso.
- Solicitar um recurso recrutado de uma WBS.
- Inscrever recursos a um projeto sem ter uma solicitação de um recurso recrutado.
