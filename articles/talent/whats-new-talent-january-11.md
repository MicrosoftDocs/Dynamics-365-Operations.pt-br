---
title: Novidades ou alterações no Dynamics 365 Talent - Core HR (11 de janeiro de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/11/2019
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
ms.search.validFrom: 2019-01-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d49a4aca368e3de10ae37b56c6d286d78f7f369a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4460348"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-january-11-2019"></a>Novidades ou alterações no Dynamics 365 Talent - Core HR (11 de janeiro de 2019)

**Compilação 8.1.2100**

Este tópico descreve os recursos novos ou alterados no Core HR.

## <a name="changes"></a>Alterações

### <a name="validate-leave-requests-by-forecasting-available-balance"></a>Valide solicitações de licença prevendo o saldo disponível
As alterações feitas nesta versão permitem que o funcionário solicite licenças futuras sem subtrair de seu respectivo saldo atual. Os fluxos de trabalho padrão serão usados para todas as solicitações futuras. Para obter mais informações, leia [Acumular folga com base nas horas trabalhadas](leave-accrue-hours-worked.md).

### <a name="view-forecasted-leave-balance-in-ess-and-people"></a>Exibir o saldo de licença previsto em ESS e Pessoas
Este recurso habilita a exibição dos saldos para períodos futuros de licença pelo RH, gerentes e funcionários. Os funcionários podem exibir os saldos futuros no espaço de trabalho **Autoatendimento para funcionários** e o RH tem acesso às mesmas informações usando o espaço trabalho **Pessoas** .

### <a name="notifications-for-changing-leave-balances"></a>Notificações para alterar saldos da licença
Os saldos de licença exibirão o saldo atual dos funcionários. Os saldos futuros estão disponíveis nos espaços de trabalho **Autoatendimento para funcionários** e **Pessoas** inserindo uma "data de início" para calcular o saldo previsto.

Foi adicionada navegação para exibir os saldos previstos nas seguintes áreas:
  - Cartão **Folga** no espaço de trabalho **Autoatendimento para funcionários** .
  - Cartão **Licença e ausência** no espaço de trabalho **Autoatendimento para gerentes** .
  - Página **Licença e ausência** no espaço de trabalho **Pessoas** .

### <a name="allow-decimals-for-variable-compensation-plans-cash-plans"></a>Permita decimais nos Planos de remuneração variável (planos de caixa)
Os prêmios e planos variáveis em dinheiro têm agora flexibilidade adicional para montantes e substituições de montantes com valores decimais.

### <a name="unable-to-change-the-dates-on-variable-comp-enrollments-after-the-plan-is-saved"></a>Não é possível alterar as datas nas inscrições para remuneração variável depois que o plano é salvo
Esta alteração permite que a data final do plano seja atualizada (ampliada ou expirada) depois que o plano é salvo. Você ainda pode ativar ou desativar planos independentemente das datas de início e fim.

### <a name="payroll-information-available-when-assigned-the-payroll-admin-security-role"></a>Informações disponíveis de folha de pagamento quando atribuídas à função de segurança Administrador de folha de pagamento
A função de Administrador de folha de pagamento foi atualizada para ter acesso a informações de folha de pagamento durante o processo de solicitação.

### <a name="employee-self-service--position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a>Autoatendimento para funcionários | Falha na obtenção do nó pai na busca detalhada de hierarquia de posições a partir do bloco
As alterações foram feitas para eliminar um erro que ocorreu na adição da hierarquia de posições a novos espaços de trabalho e na navegação na estrutura da organização.

### <a name="new-validation-message-when-personnel-number-sequence-is-in-use"></a>Nova mensagem de validação quando a sequência numérica de pessoal está em uso
Uma alteração foi feita para explicar qual o problema quando você contrata um funcionário e o número de pessoal está em uso.

### <a name="employee-self-service-workspace-selected-as-the-initial-startup-page"></a>Espaço de trabalho de autoatendimento para funcionários selecionado como a página inicial
Quando o espaço de trabalho **Autoatendimento para funcionários** é selecionado como a página inicial de um usuário que não está atribuído à função funcionário, o sistema redireciona para o painel padrão.

### <a name="termination-reason-code-updates-position-assignment-record"></a>O código de motivo da demissão atualiza o registro de atribuição de posição
O código de motivo da demissão atualizará agora a atribuição de posição ao demitir um funcionário e ao encerrar a posição. 
