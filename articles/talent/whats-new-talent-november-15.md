---
title: Novidades ou alterações no Dynamics 365 for Talent Core HR (15 de novembro de 2018)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 11/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b90d4230fe1e666aba4075670f6df206e8df7ce9
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517349"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-november-15-2018"></a>Novidades ou alterações no Dynamics 365 for Talent Core HR (15 de novembro de 2018)

[!include [banner](includes/banner.md)]

**Compilação 8.1.2045**

Este tópico descreve os recursos novos ou alterados no Core HR.

## <a name="other-changesfixes"></a>Outras alterações/correções

### <a name="unable-to-change-employees-current-position-to-a-future-open-position"></a>Incapaz de alterar o cargo atual do funcionário para uma posição aberta futura

Uma alteração foi feita para permitir transferências de posição quando a posição só está disponível no futuro. 

### <a name="position-does-not-display-when-creating-a-new-employee"></a>A posição não é exibida ao criar um novo funcionário

Uma alteração foi feita para exibir todas as posições abertas disponíveis para a atribuição ao contratar funcionários novos. em Talent. Isso inclui posições históricas ou se as posições foram datadas no futuro. As posições agora aparecerão corretamente com base na data de início do emprego. 

### <a name="termination-date-is-displaying-based-on-user-settings"></a>A data de demissão é exibida com base nas configurações do usuário

Uma alteração foi feita à lista de funcionários passados para conta para quaisquer compensações de fuso horário para o fuso horário preferido ao exibir a data de demissão.

### <a name="work-items-assigned-to-me-links-not-displaying-the-correct-information"></a>Itens de trabalho atribuídos a mim, links não exibidos com as informações corretas

Com essa alteração, navegação aos detalhes dos itens de trabalho individual na lista exibirão as informações corretas para o item selecionado. O problema ocorreu apenas com opções avançadas de segurança.


## <a name="known-issue"></a>Problema conhecido

- **Erro**: Ao adicionar um novo anexo a um trabalhador, os botões **Novo** e **Editar** são esmaecidos. 
- **Solução alternativa:** Antes de abrir a página do anexo, garante que os caixas de dados na página **Trabalhador** estejam fechadas. Se os Quadros de Fatos estiverem fechados quando a página **Trabalhador** for carregada, os botões Anexos serão habilitados. (Esse problema será corrigido na próxima atualização de plataforma.)
