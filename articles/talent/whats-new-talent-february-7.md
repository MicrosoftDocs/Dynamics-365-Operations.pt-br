---
title: Novidades ou alterações no Dynamics 365 Talent (7 de fevereiro de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/07/2019
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
ms.search.validFrom: 2019-02-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: c4005a8745e46a23fe16b94cab7b7aeb20f84035
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009753"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-february-7-2019"></a>Novidades ou alterações no Dynamics 365 Talent (7 de fevereiro de 2019)

[!include [banner](includes/banner.md)]

Este tópico descreve os recursos novos ou alterados no Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

### <a name="interview-scheduling-enhancements"></a>Aprimoramentos de agendamento de entrevista
Melhorias foram feitas para a experiência de agendamento da entrevista de ponta a ponta. Agora você pode ver a disponibilidade do calendário de um candidato interno e usar o calendário do candidato interno para agendar recomendações. Para obter mais informações, consulte [Agendamento de entrevistas e comentários](interview-scheduling-feedback.md).

### <a name="job-posting-to-linkedin--company-mismatch-issue-fixed"></a>Postagem de vagas no LinkedIn – erro de incompatibilidade de empresa corrigido
Um problema foi corrigido onde trabalhos postados no LinkedIn do Attract estavam aparecendo no nome de empresa errado. Para obter mais informações, consulte [Criar, aprovar e postar trabalhos no Attract](creating-jobs-attract.md).

### <a name="career-site-url-displayed-in-admin-settings"></a>URL do site de carreira exibida nas configurações do administrador
A URL da página inicial do site de carreira agora é exibida nas **Configurações do administrados** em **gerenciamento de sites de carreira**.

## <a name="changes-in-core-hr"></a>Alterações no Core HR

**Compilação 8.1.2134**

### <a name="multiple-compensation-levels-supported-on-jobs"></a>Vários níveis de remuneração suportados em trabalhos
Esta alteração permite que mais de um nível de compensação seja definido em um trabalho, habilitando as variações de remuneração fixa de funcionário, que podem ser diferentes entre planos usando o mesmo trabalho. 

Por exemplo:    
*Trabalho* - Gerente de conta *Níveis de compensação associados:* B1 e B2 - Cada nível tem uma variação definida de valores. B1 = Mín 50.000, Méd 60.000, Máx 75.000 e B2 = Mín 65.000, Méd 74.000, Máx 85.000. Ao criar remuneração fixa para funcionários, com base nas regras de elegibilidade definidas, cada plano fixo agora aponta para o mesmo trabalho e para níveis diferentes no trabalho. Isso permite que planos sejam definidos em regiões/empresas diferentes e apontem para o mesmo trabalho, mas em variações diferentes sem duplicar trabalhos que tenham essas diferenças.

### <a name="compensation-level-field-has-been-added-to-the-employee-fixed-compensation-entity"></a>O campo de nível de compensação foi adicionado à entidade de remuneração fixa de funcionário 
Com essa atualização, a entidade de remuneração fixa de funcionários foi atualizada para incluir o campo **Nível de remuneração**. Essa adição facilita a atualização de planos de remuneração fixa de funcionário. 

### <a name="update-job-family-when-updating-and-creating-new-positions"></a>Atualize a família de trabalho ao atualizar e criar novas posições
Ao alterar o trabalho em uma posição, **Família de trabalho** agora será padrão com base no trabalho selecionado.

### <a name="performance-improvements-when-rendering-workspaces"></a>Melhorias de desempenho ao renderizar espaços de trabalho
Guias de análise em espaços de trabalho agora carregarão ao acessar essas páginas. Um indicador será exibido durante a renderização inicial da página no canto superior esquerdo da página.
