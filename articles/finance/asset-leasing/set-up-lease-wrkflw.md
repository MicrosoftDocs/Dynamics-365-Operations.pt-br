---
title: Configurar fluxos de trabalho de aprovação de arrendamento
description: O artigo explica como configurar um fluxo de trabalho de aprovação que será executado quando um novo arrendamento for criado.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0162e559f8aaec248cfb9042b0152788536c9fc9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870268"
---
# <a name="set-up-lease-approval-workflows"></a>Configurar fluxos de trabalho de aprovação de arrendamento

[!include [banner](../includes/banner.md)]

O artigo explica como configurar um fluxo de trabalho de aprovação que será executado quando um novo arrendamento for criado. Para obter informações sobre como usar o fluxo de trabalho, consulte [Usar fluxos de trabalho de aprovação de arrendamento](use-create-lease-wrkflw.md). 

1. Acesse **Arrendamento de ativo \> Configuração \> Fluxo de trabalho de arrendamento**.
2. Na página **Fluxo de trabalho de arrendamento**, selecione **Novo**.
3. Na caixa de diálogo exibida, em **Tipo do fluxo de trabalho**, selecione o link **Fluxo de trabalho de arrendamento**.

    O aplicativo é aberto. Após a execução, entre no Azure Active Directory (Azure AD) para ser redirecionado para o aplicativo de fluxo de trabalho.

4. Arraste o elemento **Aprovação do fluxo de trabalho de arrendamento** para o fluxo de trabalho.
5. Conecte um nó de **Início** para **Aprovação do fluxo de trabalho de arrendamento**. Em seguida, conecte **Aprovação do fluxo de trabalho de arrendamento** a **Final**.
6. Clique duas vezes em **Aprovação do fluxo de trabalho de arrendamento**.
7. Selecione **Propriedades** e, em **Configurações básicas**, digite um nome para o fluxo de trabalho.

    Nesta página, você também pode definir mais parâmetros para o fluxo de trabalho. Se você tiver ativado **Ações automáticas**, o sistema executará automaticamente uma ação específica. As notificações poderão ser enviadas se forem especificadas na guia **Notificações**. Na guia **Configurações avançadas**, você pode especificar um aprovador final, definir um limite de tempo e designar ações específicas que devem ser concluídas.

8. Ao terminar de definir os parâmetros do fluxo de trabalho, selecione **Fechar**.
9. Selecione **Etapa 1** e **Propriedades**.
10. Em **Configurações básicas**, digite um nome para a etapa, crie uma linha de assunto para a aprovação e especifique instruções para a aprovação.
11. Na página **Atribuição**, selecione o tipo de atribuição.
12. Para atribuir usuários específicos à aprovação, selecione **Usuário**, selecione os usuários que aprovam arrendamentos e selecione **Fechar**.
13. Selecione **Salvar e fechar** para criar o fluxo de trabalho. Depois, quando for solicitado, selecione **OK**.
14. Na página **Criar fluxo de trabalho**, selecione **Fechar**.
14. Selecione o novo fluxo de trabalho e depois **Versões**. Em seguida, selecione **Tornar ativo** para garantir que o fluxo de trabalho esteja ativo.
15. Selecione **Fechar**. A nova versão ativa será exibida.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
