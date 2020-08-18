---
title: Novidades ou alterações no Dynamics 365 Human Resources (23 de julho de 2020)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 07/23/2020
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
ms.author: dkrame
ms.search.validFrom: 2020-07-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dd71ab5c48be1bec5ce2272bbff37ab10a4aed67
ms.sourcegitcommit: 81296c49be9953aa01e15527c34d0ef13b4622a9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "3614401"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-23-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources (23 de julho de 2020)

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Human Resources. As alterações se aplicam ao número da compilação 8.1.3416. Os números entre parênteses em alguns títulos referem-se aos números de suporte do LCS para referência.

## <a name="deleting-financial-dimensions-on-a-position-doesnt-work-as-expected-445476"></a>A exclusão de dimensões financeiras em uma posição não funciona como esperado (445476)

A remoção de dimensões de uma posição agora remove essas mesmas posições do Common Data Service.

## <a name="positions-not-in-hierarchy-show-inactive-positions-397257"></a>Posições que não estão em hierarquias mostram posições inativas (397257)

Posições que estão inativas (têm uma duração expirada), não são mais exibidas na hierarquia de posição como **Posições que não estão na hierarquia**. 

## <a name="validation-occurring-between-leaveenrollmententity-and-hcmworkerentity-on-data-management-framework-dmf-import-causes-slow-data-loads-442324"></a>A validação que ocorre entre LeaveEnrollmentEntity e HcmWorkerEntity na importação do Data Management Framework (DMF) causa cargas de dados lentos (442324)

As alterações nessa versão aumentam o desempenho do **LeaveEnrollmentEntity**.

## <a name="unable-to-personalize-in-organization-administration-447490"></a>Não é possível personalizar na Administração da organização (447490)

Com essa alteração, você agora pode personalizar os links na **Administração da organização**.

## <a name="in-preview"></a>Em visualização

## <a name="mandatory-fields"></a>Campos obrigatórios 

Agora você pode tornar campos obrigatórios usando recursos de personalização do Human Resources. Este recurso exige **Exibições salvas**.

## <a name="human-resources-application-in-teams"></a>Aplicativo Human Resources no Teams

Os funcionários podem exibir e solicitar tempo fora do trabalho no Microsoft Teams. Eles podem interagir com um bot para criar solicitações de licença. Para obter mais informações, consulte [aplicativo Human Resources no Teams](https://go.microsoft.com/fwlink/?linkid=2127841). 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Entidades da estrutura de gerenciamento de dados (DMF) para gerenciamento de benefícios
 
Entidades de gerenciamento de benefícios estão sendo liberadas. As entidades DMF permitem que você importe e exporte dados para configurar facilmente o gerenciamento de benefícios. Um modelo de gerenciamento de benefícios estará disponível para mover dados. O modelo exporta e importa os dados sequencialmente para respeitar as dependências de dados.

## <a name="buy-and-sell-leave"></a>Comprar e vender licenças 

Algumas organizações fornecem um benefício que permite que os funcionários comprem ou vendam licenças. Esse processo costuma ser gerenciado manualmente. Esse recurso automatiza o gerenciamento de políticas e solicitações para o departamento de RH. Ele simplifica o processo de gerenciamento de licenças e ajuda a eliminar erros. Para obter mais informações, consulte:

- [Gerenciar políticas de compra e venda de licenças](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Comprar e vender licenças](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>Deixar o acúmulo para uma única empresa ou um plano

Os clientes podem processar acúmulos para uma única empresa ou um único plano de licença e de ausência. Essa capacidade esclarece sobre o processo de competência para clientes com diferentes políticas de anos de licença ou acúmulo de licenças. Para obter mais informações, consulte [Acumular licenças por empresa ou por plano de licença](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).

## <a name="add-attachments-to-time-off-requests"></a>Adicionar anexos a solicitações de folga

A capacidade de adicionar anexos a solicitações de licença aprovadas é crítica no ambiente de COVID-19 atual. Os funcionários agora podem adicionar esses anexos. Eles também estão mais informados sobre como as atualizações são feitas para deixar solicitações. Para obter mais informações, consulte [Adicionar um anexo a uma solicitação existente](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).

## <a name="add-reason-code-to-accrual-suspensions"></a>Adicionar código de motivo a suspensões de acúmulos 

Os códigos de motivo foram adicionados à suspensão de acúmulos.

## <a name="carry-forward-rules"></a>Regras de postergação 

Você pode especificar um tipo de licença postergada para saldos postergados nos quais ajustes postergados são transferidos. Por exemplo, se um funcionário adianta 10 dias, você pode escolher um tipo de licença diferente para esses 10 dias. Para obter mais informações, consulte [Configurar tipos de licença e ausência](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types"></a>Suspender a acumulação de licenças para tipos de licença especificados

Você pode criar uma regra para suspender os acúmulos de licença para funcionários com solicitações de licença inseridas para licenças não pagas. A licença não remunerada pode ser um tipo, mas não precisa ser. Você pode suspender qualquer licença com base em outro tipo de licença.

## <a name="dmf-entity-available-for-accrual-suspensions"></a>Entidade DMF disponível para suspensões de acúmulos 

Uma entidade DMF disponível para suspensões de acúmulos.

## <a name="coming-soon"></a>Em breve

## <a name="checklist-entities-included-in-common-data-service"></a>Entidades de lista de verificação incluídas no Common Data Service

Entidades de lista de verificação relativas a Integração, Remoção, Transferências e Processos empresariais estarão disponíveis em breve no Common Data Service.

## <a name="platform-changes"></a>Alterações na plataforma

Atualização da plataforma 10.0.12 (36)

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)
