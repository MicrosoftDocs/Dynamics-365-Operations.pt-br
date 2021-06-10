---
title: Novidades ou alterações no Dynamics 365 Human Resources (06 de agosto 2020)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 06 de agosto de 2020.
author: andreabichsel
ms.date: 08/06/2020
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
ms.search.validFrom: 2020-08-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e49da122785e13c1896b35097849abf7a4b3feda
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054491"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-06-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources (06 de agosto 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Human Resources. As alterações se aplicam ao número da compilação 8.1.3444. Os números entre parênteses em alguns títulos referem-se aos números de suporte do LCS para referência.

## <a name="platform-update-1001236-is-now-available"></a>A atualização de plataforma 10.0.12(36) agora está disponível

Para obter mais informações, consulte [Atualizações de plataforma para a versão 10.0.12 dos aplicativos do Finance and Operations (agosto de 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-10-0-12.md).

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Entidades da estrutura de gerenciamento de dados (DMF) para gerenciamento de benefícios
 
Entidades de gerenciamento de benefícios estão sendo liberadas. As entidades DMF permitem que você importe e exporte dados para configurar facilmente o gerenciamento de benefícios. Um modelo de gerenciamento de benefícios estará disponível para mover dados. O modelo exporta e importa os dados sequencialmente para respeitar as dependências de dados. Para obter mais informações, consulte:

- [Suporte da entidade DMF](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/dmf-entity-support) no plano do Dynamics 365 versão 2020 onda 1
- [Visão geral do gerenciamento de dados](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md)


## <a name="claire-creates-a-workflow-for-buying-and-selling-leave-requests-446557"></a>O Claire cria um fluxo de trabalho para compras e solicitações de venda (446557)

Para obter mais informações, consulte:

- [Permitir que os funcionários comprem e vendam licenças](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/allow-employees-buy-sell-leave) no plano do Dynamics 365 versão 2020 onda 2
- [Gerenciar políticas de compra e venda de licenças](./hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Comprar e vender licenças](./hr-employee-self-service-buy-sell-leave.md)


## <a name="worker-postal-addresses-v2-entity-has-access-across-legal-entities-with-restricted-access-459126"></a>A entidade Endereços postais do trabalhador V2 tem acesso a entidades legais com acesso restrito (459126)

Com essa alteração, a entidade **Endereço postal do trabalhador V2** será restringida com base no acesso da entidade legal fornecido ao usuário.

## <a name="workflow-email-hyperlink-fails-to-open-relevant-reviews-437398"></a>Falha do hiperlink de email do fluxo de trabalho ao abrir revisões relevantes (437398)

Quando você usa o espaço reservado para abrir uma revisão de desempenho no fluxo de trabalho de revisão, o hiperlink gerado no email agora abre o registro selecionado.

## <a name="new-entities-for-buying-and-selling-leave-473180"></a>Novas entidades para compra e venda de licenças (473180)

As entidades da estrutura de gerenciamento de dados agora estão disponíveis para compra e venda de licenças. Para obter mais informações, consulte [Visão geral do Gerenciamento de dados](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

## <a name="when-viewing-record-information-and-using-advanced-filters-a-user-could-gain-access-to-other-employees-records-472490"></a>Ao exibir informações de registro e usar filtros avançados, um usuário pode obter acesso a registros de outros funcionários (472490)

Com essa alteração, os usuários de autoatendimento para funcionários só podem acessar seus próprios registros usando o autoatendimento para funcionários. Exibição de informações de registro ao alterar a opção de filtragem não expõe mais dados adicionais.

## <a name="personnel-management-analytics-include-exited-worker-records-382893"></a>Análises de gerenciamento de pessoal incluem registros de trabalho encerrados (382893)

Nesta versão, a análise de gerenciamento de pessoal agora inclui somente trabalhadores ativos. 
 
## <a name="unable-to-process-a-merit-increase-for-an-employee-473125"></a>Não é possível processar um aumento de mérito para um funcionário (473125)

Essa alteração permite inserir aumentos de mérito ao alterar a data de efetivação para o novo aumento de mérito.

## <a name="review-workflow-can-be-started-more-than-once-467541"></a>O fluxo de trabalho de revisão pode ser iniciado mais de uma vez (467541)

Com essa alteração, você só pode iniciar o fluxo de trabalho de revisão de desempenho uma vez. O status do gerenciador não exibe mais a opção de início da revisão.

## <a name="leave-request-work-flow-ends-in-error-when-canceling-an-approved-leave-request-472063"></a>O fluxo de trabalho de solicitação de licença termina em erro ao cancelar uma solicitação de licença aprovada (472063)

Nesta versão, quando você cancela uma solicitação de licença aprovada, o estado da solicitação não permanece mais aprovado e o fluxo de trabalho continua.

## <a name="system-suggests-exited-workers-when-creating-a-new-review-form-the-template-460624"></a>O sistema sugere trabalhadores que saíram ao criar uma nova revisão a partir do modelo (460624)

Com essa alteração, os trabalhadores que saíram estão mais disponíveis ao criar novas revisões a partir de um modelo. Não é possível criar revisões para funcionários que estão fora das datas de emprego.

## <a name="position-hierarchy-circular-reference-detection-415879"></a>Detecção de referência circular de hierarquia de posição (415879)

Com essa alteração, a detecção de referência circular da hierarquia de posição é limitada a um único ponto no tempo. Você pode executar a detecção de referência circular para datas diferentes para verificar se a estrutura de relatórios não tem referências circulares.

## <a name="buy-and-sell-leave"></a>Comprar e vender licenças 

Algumas organizações fornecem um benefício que permite que os funcionários comprem ou vendam licenças. Esse processo costuma ser gerenciado manualmente. Esse recurso automatiza o gerenciamento de políticas e solicitações para o departamento de RH. Ele simplifica o processo de gerenciamento de licenças e ajuda a eliminar erros. Para obter mais informações, consulte:

- [Permitir que os funcionários comprem e vendam licenças](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/allow-employees-buy-sell-leave) no plano do Dynamics 365 versão 2020 onda 2
- [Gerenciar políticas de compra e venda de licenças](./hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Comprar e vender licenças](./hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>Deixar o acúmulo para uma única empresa ou um plano

Os clientes podem processar acúmulos para uma única empresa ou um único plano de licença e de ausência. Essa capacidade esclarece sobre o processo de competência para clientes com diferentes políticas de anos de licença ou acúmulo de licenças. Para obter mais informações, consulte [Acumular licenças por empresa ou por plano de licença](hr-leave-and-absence-accrue.md).

## <a name="add-attachments-to-time-off-requests"></a>Adicionar anexos a solicitações de folga

A capacidade de adicionar anexos a solicitações de licença aprovadas é crítica no ambiente de COVID-19 atual. Os funcionários agora podem adicionar esses anexos. Eles também estão mais informados sobre como as atualizações são feitas para deixar solicitações. Para obter mais informações, consulte [Adicionar um anexo a uma solicitação existente](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).

## <a name="add-reason-code-to-accrual-suspensions"></a>Adicionar código de motivo a suspensões de acúmulos 

Os códigos de motivo foram adicionados à suspensão de acúmulos.

## <a name="carry-forward-rules"></a>Regras de postergação 

Você pode especificar um tipo de licença postergada para saldos postergados nos quais ajustes postergados são transferidos. Por exemplo, se um funcionário adianta 10 dias, você pode escolher um tipo de licença diferente para esses 10 dias. Para obter mais informações, consulte [Configurar tipos de licença e ausência](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types"></a>Suspender a acumulação de licenças para tipos de licença especificados

Você pode criar uma regra para suspender os acúmulos de licença para funcionários com solicitações de licença inseridas para licenças não pagas. A licença não remunerada pode ser um tipo, mas não precisa ser. Você pode suspender qualquer licença com base em outro tipo de licença.

## <a name="in-preview"></a>Em visualização

### <a name="mandatory-fields"></a>Campos obrigatórios

Você pode tornar campos obrigatórios usando recursos de personalização de Recursos Humanos. Este recurso exige **Exibições salvas**. Para obter mais informações sobre exibições salvas, consulte:

- [Exibições salvas - disponibilidade geral](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) no plano do Dynamics 365 versão 2020 onda 2
- [Criar formulários que utilizam totalmente as exibições salvas](../fin-ops-core/dev-itpro/user-interface/understanding-saved-views.md)

### <a name="human-resources-application-in-teams"></a>Aplicativo Human Resources no Teams

Os funcionários podem exibir e solicitar tempo fora do trabalho no Microsoft Teams. Eles podem interagir com um bot para criar solicitações de licença. Para obter mais informações, consulte:

- [Licença e ausência do funcionário no Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) no plano do Dynamics 365 versão 2020 onda 1
- [Aplicativo Human Resources no Teams](./hr-admin-teams-leave-app.md)

### <a name="dmf-entity-available-for-accrual-suspensions"></a>Entidade DMF disponível para suspensões de acúmulos

Uma entidade DMF disponível para suspensões de acúmulos.

## <a name="coming-soon"></a>Em breve

## <a name="checklist-entities-included-in-dataverse"></a>Entidades de lista de verificação incluídas no Dataverse

Entidades de lista de verificação relativas a Integração, Remoção, Transferências e Processos empresariais estarão disponíveis em breve no Dataverse.

## <a name="known-issues"></a>Problemas conhecidos

O espaço de trabalho **Gerenciamento de recursos** pode estar exibindo recursos que estão desabilitados como recursos de visualização quando estão geralmente disponíveis. A seguir, é exibida uma lista de recursos geralmente disponíveis que mostram um status incorreto. 

1.  Gerenciamento de benefícios
2.  Gerenciamento de casos
3.  Log de banco de dados (auditoria)
4.  Acúmulo de licenças para uma única empresa ou um único plano
5.  Suspensão de acúmulo de licença e ausência
6.  Código de motivo de ajuste de saldo e comentário
7.  Comprar e vender licenças
8.  Calendário de licenças e ausências
9.  Regras de postergação de licença
10. Auditoria de acúmulo de licenças
11. Exclusão de acúmulo de licenças
12. Arredondamento do acúmulo de licenças
13. Configurar vários tipos de licença em um único plano de licença
14. Atualizar aprimoramentos de folgas
15. Usar o FTE de um funcionário para acúmulos
16. Exibição da remuneração interempresarial
17. Imprima avaliações de desempenho
18. Correções de feriados do acúmulo de licenças

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]