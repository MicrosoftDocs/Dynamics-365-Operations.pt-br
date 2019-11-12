---
title: Novidades ou alterações no Dynamics 365 Talent - Core HR (27 de novembro de 2018)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 11/27/2018
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
ms.search.validFrom: 2018-11-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: aa50b2ec688a97a1aeeb9621ad6fa3600cd06318
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550173"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-november-27-2018"></a>Novidades ou alterações no Dynamics 365 Talent - Core HR (27 de novembro de 2018)

[!include [banner](includes/banner.md)]

**Compilação 8.1.2064**

Este tópico descreve os recursos novos ou alterados no Core HR.


## <a name="changes"></a>Alterações

### <a name="unable-to-create-a-note-in-case-management"></a>Incapaz de criar uma nota no Gerenciamento de caso

Uma alteração foi feita para um problema ao tentar editar ou criar uma nota no cenário de gerenciamento de caso.

### <a name="misspelled-word-on-the-analytics-tab-in-the-compensation-workspace"></a>Palavra escrita errado na guia de análise no espaço de trabalho de compensação 

Uma alteração foi feita para corrigir a soletração de 'Origem Étnica' no gráfico de análise de compensação no espaço de trabalho de compensação.

### <a name="employee-self-service-workspace-not-displaying-when-a-user-isnt-assigned-to-a-worker"></a>O espaço de trabalho de auto-atendimento para funcionário que não exibe quando um usuário não está atribuído a um trabalhador 

Uma alteração foi feita quando o espaço de trabalho **Auto-atendimento para funcionários** é selecionado como a página inicial na inicialização de um usuário que não foi atribuído a um trabalhador. Nessa situação, o painel padrão será exibido.

### <a name="leave-and-absence-error-object-reference-not-set-to-an-instance-of-an-object"></a>Erro de licença e ausência: Referência de objeto não definida para uma instância de um objeto

As alterações foram feitas para Erro de licença e ausência para corrigir esse erro após a aprovação de registros e licença de ausência na lista **Itens de trabalho atribuídos a mim**.

### <a name="unable-to-recall-an-image-workflow"></a>Não foi possível de cancelar um fluxo de trabalho de imagem

Após cancelar um fluxo de trabalho de imagem, o fluxo de trabalho será definido como "cancelado" e a solicitação existente pode ser excluída no espaço de trabalho do auto-serviço de funcionário.

### <a name="rehired-employees-or-contractors-show-up-multiple-times-after-termination"></a>Os funcionários ou prestadores de serviço recontratados aparecem várias vezes após o término 

Com essa atualização, os funcionários demitidos que são recontratados são exibidos apenas uma vez na saída. 

## <a name="known-issue"></a>Problema conhecido

- **Erro**: Ao adicionar um novo anexo a um trabalhador, os botões **Novo** e **Editar** são esmaecidos. 
- **Solução alternativa:** Antes de abrir a página do anexo, garante que os caixas de dados na página **Trabalhador** estejam fechadas. Se os Quadros de Fatos estiverem fechados quando a página **Trabalhador** for carregada, os botões Anexos serão habilitados. (Esse problema será corrigido na próxima atualização de plataforma.)
