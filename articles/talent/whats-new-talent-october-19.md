---
title: "Novidades ou alterações no Dynamics 365 for Talent Core HR (16 de outubro de 2018)"
description: "Este tópico descreve os recursos novos ou alterados na versão atual do Core HR do Microsoft Dynamics 365 for Talent."
author: Darinkramer
manager: AnnBe
ms.date: 10/22/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-22
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: 2eb46f436305a4c81ea99553e4dc07288ee74008
ms.openlocfilehash: 7da597a682006cddb44ff9354813b07c15c1a449
ms.contentlocale: pt-br
ms.lasthandoff: 10/22/2018

---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-19-2018"></a>Novidades ou alterações no Dynamics 365 for Talent Core HR (19 de outubro de 2018)

[!include[banner](includes/banner.md)]

**Compilação 8.1.1067**

Este tópico descreve os recursos novos ou alterados no Core HR.

## <a name="allow-managers-to-update-time-off-requests"></a>Permite que os gerentes atualizem tempo das solicitações

As solicitações de licença dos funcionários precisam ser atualizadas após aprovação por meio do fluxo de trabalho. Em muitos casos, o gerente faz essas atualizações em nome do funcionário. Este novo recurso fornece a capacidade dos gerentes atualizar o tempo ausente ou cancelar as solicitações de licença em nome de seus funcionários. Este recurso é controlado pelo parâmetro **Trabalho em nome** que pode ser definido na página **Parâmetros de recursos humanos**. 
 
## <a name="allow-hr-to-update-time-off-requests"></a>Permite que o RH atualize as solicitações de licença

Semelhante ao recurso acima, as solicitações de licença do funcionário precisam ser atualizadas pelo RH após terem sido aprovadas anteriormente por meio do fluxo de trabalho. Este recurso fornece a capacidade para usuários de RH de atualizar as solicitações de licença. A funcionalidade está habilidade no fluxo de trabalho **Pessoas** e na página **Trabalhador**, usando uma nova opção chamada **Exibir tempo fora**. Nessas páginas, os usuários do RH podem ver as solicitações e atualizar as transações de tempo de licença, semelhante a como os gerentes podem realizar essas ações.

A obrigação de segurança que controla acesso a essa funcionalidade é:
- Obrigação: Manter processos de licença e ausência específicos ao trabalhador.
- Privilégio: Manter solicitações de licença e ausência para todos os trabalhadores.

## <a name="other-changes"></a>Outras alterações
As atualizações a seguir foram feitas nesta versão:
- Alterações a ações de contratação de trabalhador para que eles não fiquem mais "presos" no estado **Fluxo de trabalho completo**.
- O registro de emprego agora pode ser criado sem uma data de início do trabalho.
- A data de registro do Dynamics 365 Talent para um curso exibido no auto-atendimento do funcionário agora aplica o deslocamento de fuso horário à data.
- Os arquivos excel podem ser importados várias vezes sem quaisquer erros usando **Entidade do funcionário**.

## <a name="known-issue"></a>Problema conhecido

- **Erro**: Ao adicionar um novo anexo a um trabalhador, os botões **Novo** e **Editar** são esmaecidos. 
- **Solução alternativa:** Antes de abrir a página do anexo, garante que os caixas de dados na página **Trabalhador** estejam fechadas. Se os Quadros de Fatos estiverem fechados quando a página **Trabalhador** for carregada, os botões Anexos serão habilitados. (Esse problema será corrigido na próxima atualização de plataforma.)
