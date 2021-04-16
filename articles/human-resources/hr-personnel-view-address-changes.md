---
title: Exibir e gerenciar alterações de endereço
description: Este tópico explica como você pode exibir e gerenciar alterações de endereço no Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 08/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-07
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5eca902ee7df7eb6835caf6f64b17f3f004b0776
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802446"
---
# <a name="view-and-manage-address-changes"></a>Exibir e gerenciar alterações de endereço

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico explica como você pode exibir e gerenciar alterações de endereço na página **Editar detalhes pessoais** de autoatendimento para funcionário ou na página de detalhes **Trabalhador** no Dynamics 365 Human Resources.

Muitas organizações desejam que os funcionários gerenciem seus próprios detalhes pessoais por meio de uma experiência de autoatendimento. Você pode permitir que os usuários atualizem endereços no espaço de trabalho **Autoatendimento de funcionários**. É possível monitorar essas alterações no espaço de trabalho **Gerenciamento de pessoal**. Para usar esse recurso, você deve especificar o número de dias que deseja exibir alterações na página **Parâmetros de recursos humanos**.

## <a name="configure-address-change-parameters"></a>Configurar parâmetros de alteração de endereço

Para configurar o número de dias em que você deseja que as alterações de endereço apareçam no espaço de trabalho **Gerenciamento de pessoal**, siga estas etapas:

1. No painel de navegação, selecione **Gerenciamento de pessoal**.

2. Selecione **Links**.

3. Selecione **Parâmetros de recursos humanos**.

4. No campo **Número de dias** em **Alteração de endereço**, insira o número de dias em que você deseja que as alterações de endereço apareçam no espaço de trabalho **Gerenciamento de pessoal**.

5. Feche a página.

## <a name="create-or-change-an-employee-address"></a>Criar ou alterar um endereço de funcionário

Os funcionários podem atualizar seus próprios endereços no espaço de trabalho **Autoatendimento de funcionários**. Siga estas etapas para criar ou alterar um endereço:

1. Selecione o bloco **Autoatendimento para funcionários** na home page.

2. Selecione **Editar detalhes pessoais**.

3. Para adicionar um endereço ,selecione **Adicionar**. Para atualizar um endereço existente, selecione o endereço na lista e selecione **Editar**.

4. Insira o **Nome ou descrição**.

5. Selecione a caixa suspensa **Finalidade** e, em seguida, selecione o tipo de endereço.

6. Insira o **País/região**.

7. Insira o **CEP**.

8. Insira a **Rua**.

9. Insira a **Cidade**, o **Estado** e o **Município**. Normalmente, esses campos são definidos automaticamente com base no campo **CEP**.

10. Opcionalmente, selecione o campo **Principal** para indicar um endereço principal. Somente um endereço pode ser marcado como o principal. Se outro endereço já estiver marcado como o endereço principal, você precisará confirmar se deseja usar esse endereço como o principal.

11. Opcionalmente, selecione o campo **Particular** para indicar que o endereço é particular. Somente os usuários com permissão explícita para exibir informações do endereço particular podem exibir esse endereço.

12. Selecione **OK**.

## <a name="create-or-change-a-worker-address"></a>Criar ou alterar um endereço de trabalhador

Você pode atualizar um endereço no espaço de trabalho **Gerenciamento de pessoal**. Siga estas etapas para criar ou alterar um endereço:

1. No espaço de trabalho **Gerenciamento de pessoal**, selecione **Links** e, depois, **Trabalhadores**.

3. Selecione o trabalhador e, depois, **Endereços**.

3. Para adicionar um endereço ,selecione **Adicionar**. Para atualizar um endereço existente, selecione o endereço na lista e selecione **Editar**.

4. Insira o **Nome ou descrição**.

5. Selecione a caixa suspensa **Finalidade** e, em seguida, selecione o tipo de endereço.

6. Insira o **País/região**.

7. Insira o **CEP**.

8. Insira a **Rua**.

9. Insira a **Cidade**, o **Estado** e o **Município**. Normalmente, esses campos são definidos automaticamente com base no campo **CEP**.

10. Opcionalmente, selecione o campo **Principal** para indicar um endereço principal. Somente um endereço pode ser marcado como o principal. Se outro endereço já estiver marcado como o endereço principal, você precisará confirmar se deseja usar esse endereço como o principal.

11. Opcionalmente, selecione o campo **Particular** para indicar que o endereço é particular. Somente os usuários com permissão explícita para exibir informações do endereço particular podem exibir esse endereço.

12. Selecione **OK**.
 
## <a name="create-a-future-change-for-an-address"></a>Criar uma alteração futura para um endereço

Em alguns casos, talvez você queira atualizar um endereço para alterar no futuro. Por exemplo, isso poderá ser útil se um funcionário estiver se mudando no dia 15 do mês seguinte.

1. Abra a página **Gerenciar endereços** selecionando **Mais opções > Avançadas** em qualquer grade de endereços.

2. Selecione **Novo** para criar um novo endereço.

3. Insira os detalhes do endereço.

4. Selecione a FastTab **Geral**.

5. No campo **Data de efetivação**, selecione a data em que o novo endereço entrará em vigor.

6. No campo **Data de vencimento**, opcionalmente selecione quando o endereço não estará mais em vigor.

7. Feche as páginas.

## <a name="view-and-monitor-address-changes"></a>Exibir e monitorar alterações de endereço

O pessoal de RH pode exibir e monitorar alterações de endereço no espaço de trabalho **Gerenciamento de pessoal**. Para exibir as alterações de endereço, abra o bloco **Gerenciamento de pessoal** na página **Inicial**. As alterações de endereço são exibidas em um bloco no canto superior direito. O número acima de **Alterações de endereço** mostra quantas alterações de endereço ocorreram no número de dias especificado na página **Parâmetros de recursos humanos**. 

Quando você seleciona o bloco **Alterações de endereço**, uma nova página exibe os detalhes das alterações de endereço. Opcionalmente, você pode selecionar **Incluir alterações de endereço futuro** no canto superior direito para exibir alterações de endereço com uma data futura.

> [!NOTE]
> Se desejar receber um alerta ou email sobre essas alterações de endereço, você poderá criar uma nova regra de alerta na guia **Opções** no Painel de Ações. Para obter mais informações sobre regras de alerta, consulte [Criar regras de alerta](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/create-alerts).<br><br>

> Se desejar configurar um fluxo de trabalho para as alterações de endereço, você poderá selecionar a opção **Enviar externamente** na regra de alerta e, em seguida, usar o Power Automate para disparar o evento comercial e configurar um fluxo de trabalho. Para obter mais informações, consulte [Alertas como eventos comerciais](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/create-alerts#alerts-as-business-events).


[!INCLUDE[footer-include](../includes/footer-banner.md)]