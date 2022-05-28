---
title: Visão geral de perfis de lançamentos
description: Este tópico explica como perfis de lançamentos são usados em aplicativos do Microsoft Dynamics 365.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemSetup, CustPosting, VendPosting, InventPosting, AssetPosting, ProjPosting, AssetLeasePostingAccounts, ProjCategory, ITMCostTypeTable, ProdGroup, WrkCtrTable, WrkCtrResourceGroup
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4c29597155e525638e7c2ded7d641017f2189c49
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734566"
---
# <a name="posting-profiles-overview"></a>Visão geral de perfis de lançamentos

Em aplicativos Finance and Operations, o termo *perfis de lançamentos* é usado para descrever as configurações que controlam como contas contábeis são convertidas em contas principais para que possam ser usadas em transações lançadas na contabilidade. Por exemplo, eles controlam como o cliente é convertido em uma conta principal de contas a receber quando uma fatura é lançada.

Alguns módulos e recursos têm uma página que inclui as palavras "perfil de lançamentos" no nome (por exemplo, **Perfil de lançamentos do cliente** ou **Perfil de lançamentos de fornecedores**). Além disso, alguns módulos têm várias opções para configurar o lançamento contábil para transações geradas pelo razão auxiliar. Por exemplo, no módulo **Controle de produção**, você pode configurar o lançamento por grupo de produção, recurso ou grupo de recursos.

Observe que, para vários tipos de transações, há uma alternativa ao lançamento de perfis: definições de lançamento. Para documentos com suporte, você pode usar definições de lançamento em vez de perfis de lançamentos para classificar as contas principais e as dimensões financeiras para entradas contábeis. Se você planeja usar ônus ou pré-ônus, será necessária uma definição de lançamento para definir as contas para as entradas contábeis.

Antes de configurar os perfis de lançamentos, as definições de lançamento ou a página **Contas para transações automáticas**, você deve configurar o plano de contas na página **Razão** na entidade legal que deseja configurar.

## <a name="posting-types"></a>Tipos de lançamentos

Em aplicativos Finance and Operations, um tipo de lançamento é usado para definir uma categoria geral para um débito ou um crédito. Esta categoria é independente da conta principal na contabilidade. Há tipos de lançamentos para cada débito ou crédito na contabilidade.

Um único comprovante pode ter um ou mais tipos de lançamentos. Por exemplo, uma transação lançada por meio de um diário geral em que a conta e a contrapartida são definidas como **razão** terão um lançamento do tipo **Diário-razão** para o débito e o crédito. Por outro lado, uma fatura de fornecedor terá vários tipos de lançamentos. Esses tipos de lançamento incluirão uma linha para o saldo do fornecedor e linhas adicionais para a entrada de compensação, como **Diário-razão**.

Você pode exibir o tipo de lançamento no campo **Tipo de lançamento** na guia **Geral** da página **Transações de comprovante**.

> [!TIP]
> Você pode usar a barra de ferramentas **Personalização** para adicionar o campo **Tipo de lançamento** à grade na guia **Visão geral** ou para movê-lo. Dessa forma, você pode facilitar a exibição ou o acesso a esse campo ao exibir comprovantes.

## <a name="detail-settings-for-a-posting-profile"></a>Configurações de detalhes para um perfil de lançamento 

Quando você configura perfis de lançamentos, o campo **Código da conta** define o nível da configuração. Estas opções estão disponíveis: **Tabela**, **Grupo** e **Tudo**. A correspondência é interrompida após a primeira correspondência, e a ordem é do nível mais específico para o nível menos específico. Embora o campo **Código da conta** possa ter um nome um pouco diferente em alguns casos, o comportamento e a função do campo permanecem os mesmos. Por exemplo, o perfil de lançamento de estoque inclui um campo **Código do item** e um campo **Código da conta**. Os dois campos têm valores **Tabela**, **Grupo** e **Tudo**.

Se o campo **Conta principal** for deixado em branco para um perfil de lançamentos e você não tiver configurado uma conta principal na página **Contas para transação automática** ou em uma página específica do módulo ou recurso, você receberá uma mensagem de erro ao lançar uma transação que usa o tipo de lançamento. Normalmente, a mensagem será "Não foi possível encontrar a conta para o \[Tipo de lançamento\]".

### <a name="table-value"></a>Valor de Tabela

O valor de **Tabela** se refere ao registro mestre associado ao perfil de lançamento. Cada registro de tabela é específico de um valor. Especifique o valor no campo exibido após o campo **Código da conta**. Normalmente, este campo é denominado **Conta** ou **Número de conta/grupo**. O nome exato varia, dependendo da página em que ele aparece.

Por exemplo, se você estiver trabalhando com um perfil de lançamento de cliente, o valor de **Tabela** representará um cliente específico. Portanto, se você selecionar **Tabela** no campo **Código da conta**, precisará selecionar o número do cliente no campo **Número da conta/grupo**.

O valor de **Tabela** representa o tipo mais específico de registro. O sistema sempre usa esse valor, mesmo que você tenha configurado outro registro em que o valor de **Grupo** ou **Tudo** for selecionado. Esse valor também substitui valores que você criou como valores padrão na página **Contas para transações automáticas**.

Não é recomendável usar o valor de **Tabela** como o mecanismo principal para gerenciar os perfis de lançamentos, pois poderão haver problemas de qualidade de dados se um perfil de lançamento separado for mantido para cada registro de dados mestre. Também é difícil manter e reconciliar um perfil de lançamento separado para cada registro de dados mestre. Em vez disso, esse valor deve ser usado para gerenciar exceções nos perfis de lançamentos.

### <a name="group-value"></a>Valor de Grupo

O valor de **Grupo** se refere ao registro de agrupamento com suporte do registro mestre que está associado ao perfil de lançamento. Cada registro de grupo é específico de um valor. Especifique o valor no campo exibido após o campo **Código da conta**. Normalmente, este campo é denominado **Conta** ou **Número de conta/grupo**. O nome exato varia, dependendo da página em que ele aparece.

O valor de **Grupo** exige que você primeiro configure um grupo e vincule-o a um ou mais registros da conta. O valor de **Grupo** é menos específico do que o valor de **Tabela**; porém, mais específico do que o valor de **Tudo**. Se nenhum registro tiver sido configurado para uma tabela, o sistema tentará encontrar um registro para o grupo ao qual o registro pertence.

Por exemplo, se você estiver trabalhando com um perfil de lançamento de cliente e selecionar **Grupo** no campo **Código da conta**, deverá selecionar um grupo de clientes no campo **Número de conta/grupo**. Você deve predefinir os grupos de clientes na página **Grupo de clientes** e deve especificar um grupo de clientes ao criar um cliente.

Se for necessário rastrear várias contas principais para determinado tipo de lançamento, é recomendável usar o valor de **Grupo**. Por exemplo, você tem três contas principais de comércio de Contas a receber: uma para clientes regulares, uma para os funcionários e outra para a venda intercompanhia. Nesse caso, é recomendável criar três grupos de clientes para segmentar os clientes. Mapeie cada grupo de clientes para a conta principal correta no perfil de lançamentos de clientes. A tabela a seguir mostra os três grupos de clientes para este exemplo.

| Grupo de clientes | Nome | Descrição |
|----------------|------|-------------|
| EXT | Cliente externo | Esse grupo é usado para todos os clientes externos padrão. |
| EMP | Funcionários | Esse grupo é usado para todos os funcionários que fazem compras da sua organização. |
| INT | Vendas intercompanhia | Esse grupo é usado para todas as contas de cliente intercompanhia que são usadas com a integração de vendas e ordens de compra. |

No perfil de lançamento, você configurará três linhas. Em cada linha, você seleciona o valor de **Grupo** e a conta principal relacionada.

### <a name="all-value"></a>Valor Tudo

O valor **Tudo** indica que as configurações se aplicam a todos os registros. Se você selecionar o valor **Tudo** no campo **Código da conta**, o campo **Número da conta/grupo** ficará indisponível e não será possível selecionar um registro específico para aplicar a configuração.

O valor **Tudo** é o valor menos específico. Ele será usado apenas se o sistema não conseguir encontrar uma correspondência para valor de **Tabela** ou de **Grupo**. Você deverá selecionar o valor **Tudo** quando tiver somente uma conta principal para um tipo de lançamento específico.

Por exemplo, quando você está trabalhando com um perfil de lançamento de cliente, as contas principais que você especifica aplicam-se a todos os outros clientes e grupos de clientes que não têm um registro para uma tabela específica (cliente) ou grupo (grupo de clientes).

### <a name="category"></a>Categoria

Os perfis de lançamento de estoque têm um valor adicional específico da categoria de vendas ou da categoria de compras. Esse valor é semelhante ao valor **Tabela**, em que se aplica somente a uma categoria de venda ou compras específica.

### <a name="default-value"></a>Valor padrão

Se você não criar um registro para um tipo de lançamento em um perfil de lançamento em que o campo **Código de conta** esteja definido como **Tudo**, e o sistema não conseguir encontrar um registro de perfil de lançamento correspondente para o valor **Grupo** ou **Tabela**, o sistema reverterá ao valor padrão que pode ser especificado na página **Contas para transação automática**. Para obter mais informações, consulte [Contas para transações automáticas](accounts-for-auto-transactions.md).

## <a name="clearing-accounts"></a>Contas de compensação

O termo *conta de compensação* costuma ser usado na contabilidade. Alguns tipos de lançamentos em aplicativos Microsoft Dynamics 365 são contas de compensação. Em outras palavras, o saldo na conta é limpo ou revertido quando outra transação é lançada. Por exemplo, quando você lança um recebimento de produtos de ordem de compra, a soma de custos estimados dos produtos, mais o imposto e os encargos nas linhas da ordem de compra, são lançados no tipo de lançamento de acúmulo de compra como um passivo. Posteriormente, quando você fatura a ordem de compra, o saldo é revertido do tipo de lançamento de acúmulo de compra e movido para a conta de comércio Contas a pagar.

## <a name="additional-resources"></a>Recursos adicionais

Muitos módulos no Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce e Dynamics 365 Project Operations têm um perfil de lançamento ou configurações adicionais que controlam como funciona o lançamento na contabilidade. Use os seguintes tópicos para saber mais sobre os perfis de lançamentos e as configurações de lançamento em cada módulo:

- [Contas para transações automáticas](accounts-for-auto-transactions.md)
- [Lançamento de Contas a pagar](accts-payble-posting.md)
- [Lançamento de Contas a receber](accts-recvble-posting.md)
- [Lançamento de arrendamento de ativos](../asset-leasing/set-up-lease-posting-accts.md)
- Lançamento de gerenciamento de ativos (em breve)
- Gerenciamento de caixa e bancos (em breve)
- Contas de lançamento da reavaliação de moeda (em breve)
- Lançamento de gerenciamento de despesas (em breve)
- [Perfil de lançamentos de ativos fixos](../fixed-assets/tasks/set-up-fixed-asset-posting-profiles.md)
- Lançamento contábil intercompanhia (em breve)
- Perfil de lançamento de estoque (em breve)
- [Lançamento de custo de entrega](../../supply-chain/landed-cost/costing-parameters-setup.md)
- [Visão geral de definições de lançamento](posting-definitions.md)
- Lançamento de controle de produção (em breve)
- Lançamento de gerenciamento e contabilidade de projetos (em breve)
- Lançamento de gerenciamento de serviços (em breve)
- Lançamento de impostos (em breve)
- Lançamento de tempo e presença (em breve)
- Lançamento de gerenciamento de transporte (em breve)
- Perfis de lançamento de gerenciamento de reembolsos (em breve)
