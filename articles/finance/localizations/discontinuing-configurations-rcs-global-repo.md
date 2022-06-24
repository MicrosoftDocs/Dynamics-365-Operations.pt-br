---
title: Descontinuar configurações no repositório Global do RCS
description: Este artigo descreve como descontinuar as configurações no repositório global RCS.
author: JaneA07
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-02-02
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 4121f45a95e1712f21390c317af532662846a0fc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894801"
---
# <a name="discontinue-configurations-in-the-rcs-global-repository"></a>Descontinuar configurações no repositório Global do RCS

[!include [banner](../includes/banner.md)]

Este artigo descreve como descontinuar configurações no repositório global RCS. Anteriormente, só foi possível excluir as configurações que não eram mais necessárias. No entanto, agora você pode marcar uma configuração liberada como **Descontinuada** no repositório Global do RCS. Com essa funcionalidade, você também pode fazer o seguinte: 
 
 - Fornecer notificações antecipadas quando uma configuração for planejada para ser descontinuada.
 - Inclua detalhes aplicáveis sobre a configuração de substituição.
 - Defina uma data **Com suporte até** para a configuração específica para informar ao usuário quando ele será descontinuado.

Ao interromper uma versão de configuração, você poderá especificar as seguintes informações opcionais:

  - **Configuração de substituição**
  - **Versão de configuração de substituição**
  - **Nota de texto livre**: use esse campo para fornecer links ou referências de documentação
  - **Com suporte até**: esse campo fornece a data proposta até quando a configuração/versão atual terá suporte. Essa data deve ser atualizada manualmente.
  
Para descontinuar a configuração, conclua as etapas a seguir. 

1. Selecione se deseja descontinuar uma única versão ou todas as versões com as mesmas configurações em uma operação definindo **Todas as versões** como **Sim**. 
2. Defina o parâmetro **Descontinuar** como **Sim**.
3. Selecione **OK** para descontinuar as configurações. O campo **Data da descontinuação** será preenchido quando você salvar as alterações.

![Descontinuar informações de configuração.](media/Discontinue-details-2.png)
  
Você pode reverter a configuração para **Compartilhada** ou ajustar as informações de descontinuação a qualquer momento. Se você compartilhar uma configuração, especifique a data **Com suporte até** e todas as outras informações relacionadas à descontinuação para indicar seus planos para uma descontinuação futura.

Se desejar compartilhar informações sobre uma descontinuação planejada, antes de realmente interromper a configuração, o usuário poderá preencher todos os campos relacionados à substituição, mas deixar o parâmetro **Descontinuar** definido como **Não**.

> [!NOTE]
> A descontinuação não limita as operações com configurações. Você pode continuar a importar, executar ou derivar as configurações, esses campos são informativos.

## <a name="finance-supports-displaying-this-information-starting-in-version-10014"></a>O Finance dá suporte à exibição dessas informações desde a versão 10.0.14

A partir da versão 10.0.14, o Dynamics 365 Finance dá suporte à exibição de informações de descontinuação. Na página **Repositório global**, você pode exibir informações atualizadas relacionadas à descontinuação. Por padrão, as configurações descontinuadas são filtradas.
  
A página **Configurações importadas** (ERSolutionTable) mostra configurações que já foram descontinuadas quando foram importadas. Para as configurações que foram interrompidas após a importação, as informações de descontinuação podem ser sincronizadas executando o trabalho **Importar atualizações de configurações**.


