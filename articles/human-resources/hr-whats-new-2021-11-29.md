---
title: Novidades ou alterações no Dynamics 365 Human Resources 19 de novembro de 2021
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 19 de novembro de 2021.
author: marcelbf
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3a86c1c24fbc758f4e3d0fd8b052e02078bee41e
ms.sourcegitcommit: 88f8a0369ce66b82314db9639491b695e18a7e5c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2021
ms.locfileid: "7902595"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-november-19-2021"></a>Novidades ou alterações no Dynamics 365 Human Resources 19 de novembro de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve recursos que são novos, alterados ou que em breve serão lançados no Microsoft Dynamics 365 Human Resources.

Para obter mais informações sobre nosso processo de atualização e agenda, consulte [Processo de atualização](hr-admin-setup-update-process.md).

Para obter mais informações sobre novos recursos e suas datas de disponibilidade geral esperadas, consulte [Dynamics 365 Human Resources 2021 ciclo de lançamentos 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Nesta versão

Esta versão inclui as seguintes correções de bug. As alterações se aplicam ao número da compilação 8.1.4591.

### <a name="bug-fixes"></a>Correções de bug

As seguintes correções de bug estão incluídas nessa versão.

> [!NOTE]
> Nosso objetivo é obter essas informações o mais rápido possível. Podemos atualizar este tópico para incluir correções de bugs feitas no build após a publicação inicial deste tópico.

| Número do problema | Problema | Descrição |
|---|---|---|
| 626178 | A navegação está ausente nos blocos do trabalhador em **Autoatendimento para gerentes** | Esse problema está corrigido agora. A navegação está disponível para ver os detalhes de relatório no **Autoatendimento para gerentes**. |
| 632573 | Não há erro de validação ao salvar um **Curso** | Esse problema está corrigido agora. Ao criar um curso com o **Número mínimo de participantes** como mais de 0, ainda foi permitido salvar mesmo quando o **Número máximo de participantes** é 0. |
| 615955 | Erro "O campo **Finalidade** deve ser preenchido" ao criar um novo local de solicitação de recrutamento. | Ao criar um novo endereço para um um novo local de solicitação de recrutamento, você recebe o erro: "O campo 'Finalidade' deve estar preenchido." No entanto, o campo **Finalidade** não está disponível na página. |
| 620797 | O campo **Sexo** em branco não é claro | Quando um sexo não é inserido para um contato pessoal, o relatório exibe "clique ou toque aqui para inserir texto", que não é muito claro, pois nada pode ser inserido no campo. |
| 620800 | O link de demonstrativo de benefícios está oculto | O demonstrativo de benefícios não é visível por padrão no **Autoatendimento para funcionários**.  Um link foi adicionado ao lado direito do **Auto-atendimento para funcionários** na seção **Links** |
| 629778 | Problema de desempenho com a integração de CDS. | A solicitação relacionada à autorização causou um problema de desempenho. |

## <a name="in-preview"></a>Em versão preliminar

Os novos recursos a seguir estão em versão preliminar. Para obter mais informações sobre como ativar ou desativar os recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

| Recurso | Liberar planos | Documentação |
|---|---|---|
| Espaço de trabalho de gerenciamento de benefícios | [Espaço de trabalho de gerenciamento de benefícios (versão preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espaço de trabalho de gerenciamento de benefícios](hr-benefits-management-workspace.md) |


## <a name="coming-soon"></a>Em breve
Para obter uma lista completa de recursos planejados e suas versões agendadas, consulte [Dynamics 365 e nuvens do setor: ciclo de lançamentos 2 de 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
