---
title: Novidades ou alterações no Dynamics 365 Talent (7 de janeiro de 2020)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 01/07/2020
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
ms.search.validFrom: 2020-01-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e227c614fdbfe6f3dd410f1a533c593979abf1ec
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4460336"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-7-2020"></a>Novidades ou alterações no Dynamics 365 Talent (7 de janeiro de 2020)

Este artigo descreve os recursos novos ou alterados no Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Alterações de Integração

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR

As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2697. Os números em parênteses em alguns cabeçalhos referem-se aos números de suporte no Microsoft Dynamics Lifecycle Services (LCS).

 
### <a name="cant-delete-workers-that-dont-have-employment-records---386157"></a>Não é possível excluir trabalhadores que não têm registros de emprego - (386157)

Esta alteração adiciona uma opção de exclusão no formulário **Trabalhadores sem emprego**. Os trabalhadores aparecerão neste formulário quando não houver empregos futuros, ativos ou históricos para o trabalhador. Nesta versão, a exclusão só é habilitada para Administradores do sistema. No entanto, no lançamento da próxima semana, a segurança será atualizada para permitir que todos os usuários com a função de Assistente de RH possam remover funcionários sem emprego. Também é possível fazer essas alterações manualmente seguindo as etapas a seguir.

1. Vá para **Configuração de segurança**.
2. Na guia **Privilégios**, filtre a lista **Privilégios** para **Manter trabalhadores**.
3. Na coluna **Referências**, selecione **Exibir itens do menu**.
4. Em **Exibir itens do menu**, selecione **HcmWOrkersWithoutEmployment**.
5. Defina a permissão **Excluir** para Conceder.
6. Selecione a guia **Objetos não publicados**.
7. Selecione **Publicar tudo**.
