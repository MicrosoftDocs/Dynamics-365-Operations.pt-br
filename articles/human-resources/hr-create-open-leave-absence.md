---
title: Criar uma licença com data de término aberta
description: Este artigo explica como criar uma licença com data de término aberta no Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 08231d4139209387c3c76923fafdd2061fceb280
ms.sourcegitcommit: e88ecaccd82afa3a915e41df1d4287d99da6a48a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/29/2022
ms.locfileid: "9805333"
---
# <a name="create-an-open-ended-leave-of-absence"></a>Criar uma licença com data de término aberta

> [!IMPORTANT]
> A funcionalidade descrita neste artigo será disponibilizada na infraestrutura do Finance como parte de uma versão futura no Microsoft Dynamics 365 Finance versão 10.0.31.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Você pode enviar solicitações de licença com data de término aberta e exibir o status das solicitações de licença no Dynamics 365 Human Resources.

## <a name="prerequisites"></a>Pré-requisitos

1. Em **Gerenciamento de recursos**, verifique se o recurso **Licença com data de término aberta** está ativado.

    > [!IMPORTANT]
    > Este recurso não pode ser desativado após ter sido ativado.

2. Crie um tipo de licença.
3. Insira os detalhes como o tipo de licença, a descrição e a ID do fluxo de trabalho.
4. No campo **Tipo de solicitação**, selecione **Licença**.
5. Na seção detalhes, para licença com data de término aberta, defina a opção **Com Data de Término Aberta** como **Sim**.
6. Defina a opção **Aviso de retorno ao trabalho** como **Sim** ou **Não**.
7. Um aviso de retorno ao trabalho pode ser opcionalmente necessário para solicitações de licença com data de término aberta.

> [!NOTE]
> Quando este recurso for habilitado , o recurso **Anexo necessário** será habilitado.

## <a name="request-an-open-ended-leave-of-absence"></a>Solicitar uma licença com data de término aberta

1. No espaço de trabalho **Autoatendimento para funcionários**, no bloco **Saldos de folga**, selecione **Mais (...)**.
2. Para enviar uma solicitação de licença, selecione **Solicitar licença**.
3. Insira informações nos campos **Tipo de licença** e **Data inicial**. No campo **Data final**, insira uma data final provisória.
4. Se você precisar enviar documentação de suporte, em **Anexos**, selecione **Carregar**.
5. Se estiver pronto para enviar sua solicitação, selecione **Enviar**. Caso contrário, selecione **Salvar rascunho**.
6. Para atualizar uma solicitação de licença com data de término aberta, selecione a solicitação, insira uma data final no campo **Data final**, defina a opção **Confirmar data de término** como **Sim** e carregue a documentação.
7. Se a opção **Aviso de retorno ao trabalho** estiver definida como **Sim**, selecione **Carregar** e, depois, marque a caixa de seleção para confirmar que um aviso de retorno ao trabalho válido foi carregado.
8. Após inserir todos os detalhes, selecione **Enviar**.
