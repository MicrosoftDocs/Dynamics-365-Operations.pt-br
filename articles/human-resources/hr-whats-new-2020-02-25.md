---
title: Novidades ou alterações no Dynamics 365 Human Resources (25 de fevereiro de 2020)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 25 de fevereiro de 2020.
author: andreabichsel
manager: tfehr
ms.date: 02/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5048c94543d0ee35bbc0f210a86a5d58ae901510
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463757"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-25-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources (25 de fevereiro de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artigo descreve os recursos novos ou alterados no Dynamics 365 Human Resources. As alterações se aplicam ao número da compilação 8.1.2927. Os números entre parênteses em alguns títulos referem-se aos números de suporte do LCS para referência.

## <a name="enable-case-management-navigation-and-data-management-framework-dmf-entity-414754"></a>Habilitar a entidade de navegação de gerenciamento de casos e estrutura de gerenciamento de dados (DMF) (414754)

Este recurso de visualização permite a navegação adicional para casos de gerenciamento de casos. É possível habilitar esse recurso de visualização no espaço de trabalho **Gerenciamento de recursos**. Esses itens de menu são exibidos no espaço de trabalho **Conformidade** de Dynamics 365 Human Resources. Com essa alteração, os recursos humanos podem acessar:

- Todos os casos
- Meus casos
- Meus casos abertos
- Meus casos expirados
- Ocorrências atribuídas a mim por meio do fluxo de trabalho

Juntamente com essas novas exibições nos casos, a entidade DMF **Detalhe de casos** também está disponível.

## <a name="enable-relationship-definitions-in-global-address-bbook-414762"></a>Habilitar definições de relacionamento no e-Book de endereço global (414762)

Agora as relações estão habilitadas no catálogo de endereços global. Antes da liberação desta semana, a caixa de fatos **Relacionamento** exibiu qualquer relacionamento definido pelo sistema. Agora, você pode definir essas relações na página de catálogo de endereços global.

## <a name="a-position-can-be-removed-when-active-compensation-records-exist-for-the-position-414568"></a>Uma posição pode ser removida quando há registros de compensação ativos para a posição (414568)

Com essa alteração, um aviso é exibido quando você tenta excluir uma posição e um trabalhador tem um registro de compensação ativo para aquela mesma posição. Quando isso acontece, você deve atualizar o registro de remuneração fixa do funcionário antes de remover a posição.

## <a name="performance-review-workflow-occasionally-adds-sign-offs-from-people-who-are-not-part-of-the-process-414171"></a>O fluxo de trabalho de avaliação de desempenho adiciona ocasionalmente as aprovações de pessoas que não fazem parte do processo (414171)

Essa alteração corrige um problema em que os participantes de aprovação extras são adicionados à avaliação de desempenho.

## <a name="worker-position-assignment-not-created-in-dataverse-when-selected-on-the-new-worker-dialog-413479"></a>Atribuição de posição de trabalhador no Dataverse não criada quando selecionada na caixa de diálogo Novo trabalhador (413479)

Essa alteração corrige um problema durante a contratação de um novo trabalhador e a atribuição da nova contratação a uma posição por meio da caixa de diálogo **Novo trabalhador**. Agora, a atribuição de posição está refletida em Dataverse.

## <a name="coming-soon"></a>Em breve

### <a name="updated-dataverse-solution"></a>Solução Dataverse atualizada

Uma nova solução de Dataverse estará disponível em breve com as seguintes alterações:

| Descrição | Troco |
| ----------------------------------------- | --- |
| Alterações de entidade do **Trabalho/Posição** | **Região de remuneração** adicionado</br>**Dimensões financeiras** adicionado |
| Alterações de entidade do **Trabalhador** | **Sequência do nome** adicionado</br>**Trabalha de casa** adicionado</br>**Idioma** adicionado</br>**Aniversário de tempo de serviço** adicionado</br>**Data de aniversário** adicionado</br>**Data original de contratação** adicionado |
| Alterações de entidade do **Emprego** | **Dimensões financeiras** adicionado</br>**Motivo da demissão** adicionado</br>**Data da demissão** renomeada de **Data de transição**</br>**Data de experiência** adicionado |
| Alterações de entidade do **Endereço do trabalhador** | **Endereço** adicionado</br>**Linha de endereço 1**, **Linha de endereço 2** e **Linha de endereço 3** marcadas para depreciação |
| Novas entidades de configuração de remuneração variável | **Tipo de plano de remuneração variável**</br>**Plano de remuneração variável**</br>**Regras de benefício proporcional diferido**</br>**Nível do plano de remuneração variável** |
| Nova entidade **Emprego do calendário do trabalhador** | **Entidade do calendário de trabalho** adicionada |
| Nova entidade **Detalhe da posição de folha de pagamento** | **Detalhe da posição de folha de pagamento** adicionado |
| Nova entidade **Bloco** | **Bloco** adicionado. A nova entidade **Título** será incluída no processo de sincronização entre Human Resources e Dataverse. Não será inicialmente referenciada de entidades **Cargo** ou **Trabalho**. |

Nas próximas semanas, essas alterações de entidade estarão disponíveis em todos os ambientes. Para instalar manualmente a solução Dataverse mais recente para recursos humanos:

1.  Vá para [Centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).

2.  Selecione **Ambientes**.

3.  Localize o ambiente que você deseja atualizar. Ele deve corresponder ao **Nome do ambiente** na seção **informações do Common Data Service** no formulário **Sobre** em Recursos Humanos.

4.  Selecione o ambiente para exibir os detalhes do ambiente.

5.  Na barra de ação na parte superior, selecione **Gerenciar soluções**. Uma nova janela do navegador irá abrir e navegar até o **Centro de Administração do Dynamics 365** no contexto do seu ambiente.

6.  Na lista **Solução**, selecione **Ancoragem de Dynamics 365 Human Resources**.

7.  Selecione **Atualizar** para aplicar a solução mais recente.

## <a name="in-preview"></a>Em visualização

Os seguintes recursos de visualização foram disponibilizados em 3 de fevereiro de 2020:

- **Recursos de exibição de licenças e ausências** - para obter mais informações, consulte [Recursos de exibição de licenças e ausências](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Recurso de visualização de gerenciamento de benefícios** - para obter mais informações, incluindo problemas conhecidos, consulte [Visão geral do gerenciamento de benefícios](hr-benefits-management-overview.md).

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]