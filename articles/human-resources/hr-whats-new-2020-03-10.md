---
title: Novidades ou alterações no Dynamics 365 Human Resources (10 de março de 2020)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 10 de março de 2020.
author: andreabichsel
ms.date: 03/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-03-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 296e11befb0dc916faab2eb0388188852bc3ceb6
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051104"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-10-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources (10 de março de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artigo descreve os recursos novos ou alterados no Dynamics 365 Human Resources. As alterações se aplicam ao número da compilação 8.1.2985. Os números entre parênteses em alguns títulos referem-se aos números de suporte do LCS para referência.

## <a name="cant-access-skill-gap-analysis-report-394460"></a>Não é possível acessar o relatório de análise de lacuna de habilidades (394460)

Este relatório não tem suporte no Dynamics 365 Human Resources. O item de menu para imprimir o relatório SSRS é removido.

## <a name="incorrect-message-accessing-the-getting-started-page-417950"></a>Mensagem incorreta acessando a página Introdução (417950)

Com essa alteração, a segurança oculta esse item de menu se você não tiver acesso ao formulário.

## <a name="streamlined-task-maintenance-for-employees-380538"></a>Manutenção de tarefas simplificada para funcionários (380538)

O formulário de manutenção de tarefas do trabalhador lista todas as tarefas de um funcionário no integrado, na remoção, nas transições e nos processos comerciais. Você pode excluir, reatribuir ou atualizar o status das tarefas.

Exemplo: Benjamin Martins é um administrador de benefícios. Durante a integração do funcionário, as tarefas são criadas para Benjamin a fim de revisar a seleção de benefícios do novo funcionário. Benjamin tem tarefas passadas concluiu e tarefas futuras que ele precisa concluir. Benjamin decide deixar a empresa, portanto, suas tarefas precisam ser reatribuídas ou removidas. O formulário manutenção de tarefas (no painel de ações do formulário **Trabalhador**) permite que todas as tarefas de Benjamin sejam atribuídas novamente a outro trabalhador ou removidas.  

## <a name="dataverse-solution-is-now-available-with-the-following-changes"></a>A solução do Dataverse agora está disponível com as seguintes alterações:

| descrição | Troco |
| --- | --- |
| Alterações de entidade do **Trabalho/Posição** | <ul><li>**Região de remuneração** adicionado</li>|
| Entidade **Dimensão da posição do trabalho** adicionada | <ul><li>**Dimensões financeiras** adicionado</li>
| Alterações de entidade do **Trabalhador** | <ul><li>**Sequência do nome** adicionado</li><li>**Trabalha de casa** adicionado</li><li>**Idioma** adicionado</li><li>**Aniversário de tempo de serviço** adicionado</li><li>**Data de aniversário** adicionado</li><li>**Data original de contratação** adicionado</li></ul> |
| Alterações de entidade do **Emprego** | <ul><li>**Dimensões financeiras** adicionado</li><li>**Motivo da demissão** adicionado</li><li>**Data da demissão** renomeada de **Data de transição**</li><li>**Data de experiência** adicionado</li></ul> |
| Alterações de entidade do **Endereço do trabalhador** | <ul><li>**Endereço** adicionado</li><li>**Linha de endereço 1**, **Linha de endereço 2** e **Linha de endereço 3** marcadas para depreciação</li></ul> |
| Novas entidades de configuração de remuneração variável | <ul><li>**Tipo de plano de remuneração variável**</li><li>**Plano de remuneração variável**</li><li>**Regras de benefício proporcional diferido**</li><li>**Nível do plano de remuneração variável**</li></ul> |
| Nova entidade **Emprego do calendário do trabalhador** | <ul><li>**Entidade do calendário de trabalho** adicionada</li></ul> |
| Nova entidade **Detalhe da posição de folha de pagamento** | <ul><li>**Detalhe da posição de folha de pagamento** adicionado</li></ul> |
| Nova entidade **Bloco** | <ul><li>**Bloco** adicionado</li></ul> A nova entidade **Título** é incluída no Dataverse, mas não é referenciada nas entidades **Posição de trabalho** ou **Trabalho** no momento. |

> [!NOTE]
> As dimensões financeiras para as posições e o trabalho fornecem integração unidirecional para atualizações de recursos humanos para Dataverse. As atualizações de dimensões financeiras não são sincronizadas atualmente de Dataverse a Recursos Humanos.

Nas próximas semanas, essas alterações de entidade estarão disponíveis em todos os ambientes. Para instalar manualmente a solução Dataverse mais recente para recursos humanos:

1.  Vá para [Centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).

2.  Selecione **Ambientes**.

3.  Localize o ambiente que você deseja atualizar. O ambiente deve corresponder ao **Nome do ambiente** na seção **informações do Dataverse** no formulário **Sobre** em Recursos Humanos.

4.  Selecione o ambiente para exibir os detalhes do ambiente.

5.  Na barra de ação na parte superior, selecione **Gerenciar soluções**. Uma nova janela do navegador irá abrir e navegar até o **Centro de Administração do Dynamics 365** no contexto do seu ambiente.

6.  Na lista **Solução**, selecione **Ancoragem de Dynamics 365 Human Resources**.

7.  Selecione **Atualizar** para aplicar a solução mais recente.

## <a name="in-preview"></a>Em visualização

Os seguintes recursos de visualização foram disponibilizados em 3 de fevereiro de 2020:

- **Recursos de exibição de licenças e ausências** - para obter mais informações, consulte [Recursos de exibição de licenças e ausências](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Recurso de visualização de gerenciamento de benefícios** - para obter mais informações, incluindo problemas conhecidos, consulte [Visão geral do gerenciamento de benefícios](hr-benefits-management-overview.md).

## <a name="coming-soon"></a>Em breve

### <a name="platform-update-33"></a>Update 33 para plataforma

- Aplicativos de página completa (Visualização) - Esse recurso de visualização, que requer que você habilite o recurso de Exibições salvas, permite que Power Apps e aplicativos de terceiros sejam adicionados como experiências de página completa por meio do painel.

- Exibições salvas (Visualização) - Este recurso de visualização habilita exibições salvas, que é um aperfeiçoamento significativo do subsistema de personalização. Esse recurso permite que os usuários tenham vários conjuntos nomeados de personalizações por página. Você também pode publicar exibições para direitos de acesso.

- Otimizado "é uma das" experiências de filtragem - este recurso permite que uma experiência de filtragem otimizada como "é uma das" que facilita inserir vários valores de filtro, tem um mecanismo mais simples para remover valores individuais ou de todos os filtros, e tem uma visualização mais compacta e intuitiva de valores de filtro.

- Campos recomendados - Geralmente, os usuários precisam adicionar campos a uma grade ou a uma página. Isso pode ser difícil com tantos campos disponíveis. Em vez de ter de pesquisar uma lista grande, este recurso permite que o sistema alcance um conjunto de campos recomendados com base no que os outros usuários adicionam com mais frequência em cenários semelhantes.

- Ações adesivas padrão em grades-este recurso garante que a ação padrão em uma grade esteja vinculada a uma coluna específica em uma grade, independentemente da coluna ser movida ou ocultada.

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]