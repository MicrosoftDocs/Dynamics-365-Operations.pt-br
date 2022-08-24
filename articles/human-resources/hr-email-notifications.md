---
title: Notificação de benefícios por e-mail
description: Este artigo fornece uma visão geral do recurso de notificação por e-mail de gerenciamento de benefícios para o Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/01/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d550cbb2f639535dbb43765c9fb0632a514fbe8c
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2022
ms.locfileid: "9229888"
---
# <a name="benefits-email-notification"></a>Notificação de benefícios por e-mail

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [banner](../includes/preview-banner.md)]

O recurso de notificação por email permite que lembretes e notificações de email sejam enviados aos funcionários nas seguintes situações:

- Registro de novas contratações
- Inscrição aberta
- Eventos da vida habilitados

Você pode criar e definir vários modelos de email e enviar as notificações usando o espaço de trabalho **Gerenciamento de benefícios** e a página **Benefícios do trabalhador**. Você também pode rastrear as notificações/histórico de lembretes.

## <a name="set-up-human-resources-shared-parameters"></a>Configurar parâmetros de recursos humanos compartilhados

Na página **Parâmetros compartilhados de recursos humanos**, você pode criar modelos de email de benefícios para tipos diferentes de comunicação que são enviados para funcionários ou grupos de funcionários.

## <a name="create-a-new-email-id-template"></a>Criar um novo modelo de ID de email

Para criar um novo modelo de ID de email, siga estas etapas.

1. Acesse **Modelos de email do sistema**.
2. Selecione **Novo**.
3. No campo **ID do email** insira um nome.
4. Configure outros campos, conforme necessário.
5. Selecione **Editar mensagem** para carregar o modelo.
6. Na página **Parâmetros compartilhados de recursos humanos**, selecione o novo modelo em **Modelos do sistema** e mova-o em **Modelos para obter benefícios**.

## <a name="send-email-to-employees"></a>Envie email para funcionários

Para enviar um email para uma nova contratação que ainda não foi iniciada, siga estas etapas.

1. Abra o espaço de trabalho **Gerenciamento de benefícios**.
2. Selecione o bloco para o grupo de funcionários para o qual você deseja enviar o email.
3. Selecione **Enviar email**.
4. Selecione os funcionários para os quais deseja enviar o email.
5. Selecione **Enviar email**.
6. Selecione o modelo que você deseja utilizar.
7. Selecione **OK** para enviar o email.

    Você pode revisar a mensagem de email e o status da página de benefícios do **espaço de trabalho** ou selecionar **Histórico de email de benefícios** na seção **Links** do espaço de trabalho **Gerenciamento de benefícios**. Você também pode enviar o email na página do **plano de benefícios trabalhador**.

8. Para exibir o histórico de email de benefícios, no espaço de trabalho **Gerenciamento de benefícios**, na seção **Links**, selecione **Histórico de email de benefícios**.
9. Exiba o histórico de email completo para os emails de benefícios que foram enviados. Para revisar o conteúdo do email, selecione **Exibir mensagem**.
10. Selecione **Trabalhador**.
11. Na página **Plano de benefícios do trabalhador**, você pode enviar email e exibir o histórico de email de benefícios.

O espaço de trabalho **Gerenciamento de benefícios** inclui blocos diferentes. Você pode enviar emails selecionando o modelo relacionado. Se os novos emails de registro de contratação tiverem sido enviados, selecione o bloco **Nova contratação não iniciada** e, em seguida, selecione o link **Enviar lembrete**. Você pode selecionar um modelo de lembrete e definir o título da notificação como um primeiro, segundo ou terceiro lembrete.
