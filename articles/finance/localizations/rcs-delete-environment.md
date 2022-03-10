---
title: Regulatory Configuration Service (RCS) - Excluir um ambiente do RCS
description: Este tópico explica como um administrador do sistema RCS (Regulatory Configuration Service, serviço de configuração regulatória) pode excluir um ambiente do RCS e dados relacionados.
author: JaneA07
ms.date: 06/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Global
audience: Application User, System Admin
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: f9073a14143423676f23f9bf8dc9c17dbae18a6c3ad0d2f6d1e33919fd9162bf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6759810"
---
# <a name="regulatory-configuration-service-rcs---delete-an-rcs-environment"></a>Regulatory Configuration Service (RCS) - Excluir um ambiente do RCS

[!include [banner](../includes/banner.md)]

Este tópico explica como um administrador do sistema RCS (Regulatory Configuration Service, serviço de configuração regulatória) pode excluir um ambiente do RCS e dados relacionados.

Antes de poder concluir o procedimento neste tópico, é preciso atender aos seguintes pré-requisitos:

- Você deve ter a função de **Administrador do sistema** atribuída a você para o ambiente do RCS.
- A função **Administrador do sistema** deve ter a função **RCSDeleteEnvironmentDuty** atribuída a ela.

## <a name="delete-an-rcs-environment"></a>Excluir um ambiente do RCS

1. Abra o RCS e selecione o bloco de espaço de trabalho **Relatório eletrônico**.
2. Na seção **Links relacionados**, selecione **Excluir ambiente do RCS**.

    ![Excluir ambiente do RCS na seção Links relacionados.](media/01_RCS-Delete-Environ-Related-Link.PNG)

3. Na caixa de diálogo que aparece, revise as mensagens sobre o escopo da exclusão do ambiente.

    ![Mensagens na caixa de diálogo Excluir ambiente do RCS.](media/01_RCS-Delete-Environ-Msg_noGUID.PNG)

    > [!IMPORTANT]
    > A exclusão de um ambiente do RCS não pode ser revertida.
    >
    > A operação exclui o ambiente do RCS selecionado e quaisquer dados relacionados, incluindo recursos e configurações armazenadas no repositório global. Os recursos e configurações que são compartilhados com outras organizações não serão compartilhados e excluídos se não tiverem dependências. Os recursos e configurações que possuírem dependências serão marcados como descontinuados.

4. No campo fornecido, insira o identificador global exclusivo (GUID) do ambiente do RCS para confirmar se deseja excluí-lo. O GUID do ambiente está incluído na mensagem de exclusão.
5. Selecione **Excluir ambiente**.
    
Seu ambiente do RCS e quaisquer dados relacionados são excluídos.

> [!IMPORTANT]
> Depois de excluir um ambiente do RCS, não é possível recuperar os dados. Um novo ambiente do RCS pode ser criado em qualquer região disponível do RCS.
