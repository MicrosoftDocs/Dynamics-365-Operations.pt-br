---
title: Adicionar informações de gerenciamento de crédito de clientes
description: Este tópico explica como adicionar informações de gerenciamento de crédito de um cliente.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 919aa50136f02a44eb69146589496ad1284721f2
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976634"
---
# <a name="add-credit-management-information-for-customers"></a>Adicionar informações de gerenciamento de crédito de clientes

[!include [banner](../includes/banner.md)]

Depois de configurar os parâmetros que controlam o gerenciamento de crédito, você pode adicionar mais detalhes de cada cliente. Esses detalhes controlam os processos de gerenciamento de crédito e fornecem informações adicionais que ajudam os membros da equipe de cobrança a gerenciar os clientes.

## <a name="customer-information"></a>Informações sobre cliente

Você pode adicionar os detalhes do cliente na FastTab **Crédito e cobranças** da página **Todos os clientes** (**Contas a receber \> Clientes \> Todos os clientes**).

1. Defina a opção **Limite de crédito ilimitado** como **Sim** se o cliente não tiver de ser limitado por nenhum teste de limite de crédito.
2. Defina a opção **Excluir do gerenciamento de crédito** como **Sim** para excluir o cliente das as ações que geralmente ocorrem durante os processos de gerenciamento de crédito.
3. Selecione o grupo de gerenciamento de crédito para o cliente.
4. Para calcular o limite de crédito na moeda do cliente, no campo **Limite de crédito na moeda do cliente**, insira o limite de crédito. O limite de crédito na moeda da empresa será convertido usando as taxas de câmbio definidas pelo tipo de taxa de câmbio de limite de crédito selecionado nos parâmetros de gerenciamento de crédito.
5. No campo **Data da última revisão**, insira a data em que o limite de crédito do cliente foi revisto pela última vez por um gerente de crédito.
6. No campo **Data da próxima revisão programada**, insira a data em que o cliente está programado para revisão e atualização de crédito.
7. No campo **Limite de crédito qualificado**, insira o limite de crédito mais alto que pode ser atribuído ao cliente com base na revisão de seu histórico de crédito. O limite de crédito qualificado pode ser diferente do limite de crédito mostrado na FastTab **Crédito e cobranças**.
8. No campo **Moeda de limite de crédito qualificado**, insira a moeda do limite de crédito qualificado.
9. No campo **Data do limite de crédito qualificado**, insira a data em que o limite de crédito qualificado foi criado.
10. No campo **Status da conta de crédito**, insira o status da conta de crédito do cliente.
11. No campo **Razão do status**, insira o motivo associado ao status da conta.
12. Defina a opção **Com agência** como **Sim** para indicar que no momento o cliente está atribuído a uma agência de crédito. Este valor é meramente informativo. Ele não é usado em nenhum processo de gerenciamento de crédito.
13. Defina a opção **Título retido** como **Sim** para indicar que há um título retido para a empresa. Este valor é meramente informativo. Ele não é usado em nenhum processo de gerenciamento de crédito.
14. No campo **Data de início do negócio**, insira a data em que o cliente começou a fazer negócios. Essas informações são usadas quando são criadas pontuações de risco.
15. No campo **Cliente desde**, insira a data em que as primeiras transações do cliente foram processadas. Essas informações são usadas quando são criadas pontuações de risco.
16. Insira notas que a equipe de crédito possa usar para avaliar ainda mais a confiabilidade de crédito do cliente.

Observe que algumas das informações mostradas na página **Cliente** são criadas por outro processo:

- O campo **Data de vencimento de limite de crédito** mostra a data em que o limite de crédito vai vencer. Se você não definir este campo, o limite de crédito do cliente não vencerá.
- O campo **Data de limite de crédito** mostra a data em que o limite de crédito foi criado. Este campo é atualizado sempre que o limite de crédito é ajustado.
- Os limites de crédito temporários substituem o limite de crédito do cliente por um período. Eles são usados no lugar do limite de crédito para calcular o limite de crédito total. Essas informações somente serão mostradas se houver um limite de crédito ativo. Você pode adicionar limites de crédito temporários por meio de ajustes de limite de crédito.
- O campo **Seguro e garantias** mostra o valor total de seguro e garantias que podem aumentar o limite de crédito do cliente.
- O campo **Total de limite de crédito** mostra o limite de crédito final do cliente. O total de limite de crédito inclui seguro e garantias e limites de crédito temporários.

## <a name="temporary-credit-limits"></a>Limites de crédito temporários

Os limites de crédito temporários substituem os limites de crédito do cliente por um período definido. Você pode adicionar limites de crédito temporários usando ajustes de limite de crédito. Os ajustes de limite de crédito permitem que os gerentes de crédito atualizem os limites de crédito e as datas de vencimento de um único cliente, de um grupo de clientes ou de todos os clientes por meio de um processo de lançamento.

Você pode criar entradas de ajuste de limite de crédito na página **Ajustes de limite de crédito** (**Gerenciamento de crédito \> Ajustes de limite de crédito \> Ajustes de limite de crédito**).

## <a name="create-insurance-policies-and-guarantees"></a>Criar apólices de seguro e garantias

Você pode criar uma ou mais apólices de seguro e garantias para cada cliente. Você pode usá-las para calcular a exposição da empresa quando ela oferece crédito a um cliente. As apólices de seguro e as garantias também podem ser incluídas no limite de crédito de um cliente.

Você pode criar apólices de seguro e garantias na página **Todos os clientes** (**Contas a receber \> Clientes \> Todos os clientes**). Selecione um cliente e, no Painel de Ação, na guia **Gerenciamento de crédito**, selecione **Seguro e garantias**.

> [!NOTE]
> No procedimento a seguir, selecione uma seguradora ou um fiador no catálogo de endereços global. Por isso, antes de iniciar este procedimento, você deve se certificar de que as seguradoras e os fiadores foram adicionados ao catálogo de endereços global.

1. No campo **Identificador**, digite **Garantia** ou **Seguro**.
2. No campo **Tipo de seguro ou garantia**, selecione um dos tipos de seguro ou de garantia configurados anteriormente.
3. No campo **Seguradora/Fiador**, selecione a seguradora ou o fiador no catálogo de endereços global. 
4. Se você selecionou **Seguro** no campo **Identificador**, no campo **Tipo de cobertura da apólice**, selecione um dos tipos de cobertura configurados anteriormente. Não é possível selecionar um tipo de cobertura de apólice para uma garantia.
5. No campo **Identificação**, digite a ID da apólice. Geralmente a ID é um número de apólice.
6. No campo **Efetivação**, digite a data de início da apólice de seguro ou da garantia.
7. No campo **Vencimento**, digite a data em que a apólice de seguro ou a garantia vence.
8. No campo **Valor**, digite o valor da apólice de seguro ou da garantia. Esse é o valor total da apólice.
9. No campo **Moeda**, selecione a moeda do valor da apólice. 
10. No campo **Atualizar limite de crédito**, especifique uma porcentagem entre **0** e **100**. Essa porcentagem será aplicada ao valor da apólice, e o valor resultante será usado para aumentar o limite de crédito utilizado nos cálculos de limite de crédito. O valor calculado é mostrado em **Total de limite de crédito, Seguro e Garantias** na FastTab **Crédito e cobranças** da página **Clientes**.

    Este é um exemplo:

    - O limite de crédito (A) é 100.000.
    - O valor da apólice (B) é 50.000.
    - A porcentagem de **Atualizar limite de crédito** (C) é 50,00.
    
    Nesse caso, o limite de crédito efetivo é 125.000 (= A + \[B × C\]).

11. Marque a caixa de seleção **Incluído na exposição** para reduzir o limite de crédito usado nos cálculos de limite de crédito pelo valor total da apólice. Se essa caixa de seleção estiver marcada, o valor calculado quando a porcentagem de **Atualizar limite de crédito** for especificada não será usado nos cálculos de limite de crédito.

    Este é um exemplo:

    - O limite de crédito (A) é 100.000.
    - O valor da apólice (B) é 50.000.
    - A porcentagem de **Atualizar limite de crédito** (C) é 50,00.

    Nesse caso, o limite de crédito efetivo é 125.000 (= A + \[B × C\]).
    
    No entanto, se você marcar a caixa de seleção **Incluído na exposição**, o valor de **Atualizar limite de crédito** de 50.000 (= 50,00 por cento de 100.000) será removido e o valor da exposição será 75.000 (= A + \[B x C\] – B).
