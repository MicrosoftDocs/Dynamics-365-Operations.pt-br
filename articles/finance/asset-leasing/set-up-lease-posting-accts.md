---
title: Configurar contas de lançamento de arrendamento
description: Este tópico lista as contas de lançamento necessárias Transações de arrendamento de ativo e explica como definir contas de lançamento na página Parâmetros de lançamento de arrendamento.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 8ca1c6eea854577e5aa34b1a9b9d1731b209527b
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4440540"
---
# <a name="set-up-lease-posting-accounts"></a>Configurar contas de lançamento de arrendamento

[!include [banner](../includes/banner.md)]

Este tópico lista as contas de lançamento necessárias Transações de arrendamento de ativo e explica como definir contas de lançamento na página **Parâmetros de lançamento de arrendamento**.

Para obedecer ao Tópico 842 da Codificação de Padrões Contábeis (ASC 842) e ao Padrão Internacional de Relatórios Financeiros 16 (IFRS 16), talvez você precise criar contas no seu plano de contas. No entanto, as contas que você cria para atender aos padrões ASC e IFRS não são contas de ativos fixos. Sob o ASC 842, um ativo de direito de uso (DDU) é registrado para arrendamentos mercantis e operacionais. Esses arrendamentos são separados dos ativos fixos. (Ainda é possível manter um ativo DDU usando Ativos fixos).

Para obter mais informações sobre como criar estruturas de conta, consulte [Criar estruturas de conta](../general-ledger/tasks/create-account-structures.md). Para obter mais informações sobre como criar uma conta principal, consulte [Criar uma conta principal](../general-ledger/tasks/create-main-account.md).

A tabela a seguir mostra exemplos de contas que devem ser criadas para transações de ativos arrendados, caso ainda não tenham sido criadas. Sob o IFRS 16, as relações de arrendamento operacional ainda são usadas para arrendamentos de baixo valor e de curto prazo.

| Nº de conta contábil | Tipo de conta  | Nome da conta                                          |
|-----------------------|---------------|-------------------------------------------------------|
| 180150                | Ativo         | Ativo DDU de veículo                                     |
| 180160                | Ativo         | Ativo DDU de imóvel                                    |
| 180250                | Ativo         | Depreciação acumulada - veículos                   |
| 180260                | Ativo         | Depreciação acumulada - imóvel                  |
| 222300                | Passivo     | Obrigações financeiras de curto prazo - arrendamentos mercantis                |
| 222310                | Balanço | Obrigação de curto prazo - Arrendamentos operacionais              |
| 250200                | Passivo     | Notas a Pagar                                         |
| 250601                | Balanço | Obrigação de longo prazo - arrendamentos mercantis                 |
| 250602                | Balanço | Obrigação de longo prazo - arrendamentos operacionais               |
| 250606                | Balanço | Arrendamento diferido                                         |
| 300160                | Balanço | Lucros Retidos                                     |
| 604500                | Expense       | Despesa de arrendamento                                         |
| 604501                | Expense       | Despesa de arrendamento operacional de veículo - acréscimo de juros  |
| 604502                | Expense       | Despesa de arrendamento operacional de veículo - amortização        |
| 605200                | Expense       | Despesa de arrendamento operacional de imóvel - acréscimo de juros |
| 605201                | Expense       | Despesa de arrendamento operacional de imóvel - amortização       |
| 607101                | Expense       | Despesa de amortização de arrendamento de veículo                    |
| 607102                | Expense       | Despesa de amortização de arrendamento de imóvel                   |
| 607103                | Expense       | Despesa de redução ao valor recuperável - arrendamentos mercantis                   |
| 607104                | Expense       | Despesa de redução ao valor recuperável - Arrendamentos operacionais                 |
| 618910                | Expense       | Despesa de arrendamento- arrendamentos mercantis                        |
| 618920                | Expense       | Pagamentos variáveis - arrendamentos mercantis                    |
| 618930                | Expense       | Pagamentos variáveis - arrendamentos operacionais                  |
| 800600                | Expense       | Despesa de juros de arrendamento de veículo                        |
| 800601                | Expense       | Despesa de juros de arrendamento de imóvel                       |
| 801201                | Balanço | Ganhos e perdas - modificação de arrendamento                      |

## <a name="configure-posting-accounts"></a>Configurar contas de lançamento

Para atribuir contas aos registros e grupos de arrendamentos que foram criados, você deverá configurar parâmetros para Arrendamento de ativos.

1. Acesse **Gerenciamento de ativos \> Configuração \> Parâmetros de lançamento de arrendamento**.
2. Na guia **contas**, abra a Guia Rápida **Contas de arrendamento**. Determine as contas principais para arrendamentos mercantis e operacionais ao **Tipo de lançamento** correspondente. A tabela anterior mostra as contas relacionadas a arrendamentos operacionais e mercantis.

    > [!NOTE]
    > Esta etapa requer que você configure contas separadas para arrendamentos operacionais e mercantis para cada tipo de lançamento, exceto **Compensação de despesas de arrendamento** e **Aumento/diminuição de arrendamento**. As empresas que aderem à estrutura de contabilidade do IFRS 16 devem adicionar uma conta principal ao arrendamento operacional. No entanto, o sistema não usará essa conta, embora seja um campo obrigatório, pois todas as concessões no IFRS 16 são classificadas como arrendamentos mercantis.
    >[!NOTE]
    > **Aumento/redução de arrendamento** será usado como tipo de lançamento para considerações adicionais sobre ativos, incluindo **Custo direto inicial, Incentivos de arrendamento, Pré-pagamentos de arrendamento e Custos de desmontagem**, mas lance na conta principal do Ativo de direito de uso, que tem como padrão **Ativo de arrendamento**.        
    
3. Para selecionar um grupo de arrendamentos específico correspondente à conta principal, no campo **Código da Conta**, selecione **Grupo**. Em seguida, no campo **Número da Conta/Grupo**, selecione o grupo de arrendamentos a ser atribuído à conta principal.
4. Para atribuir códigos de conta aos custos administrativos que foram configurados no sistema, na Guia Rápida **Custos de execução**, no campo **Tipo de despesa**, selecione uma despesa. Em seguida, atribua as contas mercantis e operacionais a serem usadas para cada registro.

    > [!NOTE]
    > A conta mercantil ou operacional selecionada será debitada quando a fatura da despesa agendada for lançada.
    > **Contrapartida de despesa de arrendamento** será usado como tipo de lançamento para transações de custos de execução, mas lance na **Contrapartida** definida nas **Linhas da agenda de pagamento de custos de execução** no formulário de detalhes do arrendamento ou de registro do arrendamento.   


[!INCLUDE[footer-include](../../includes/footer-banner.md)]