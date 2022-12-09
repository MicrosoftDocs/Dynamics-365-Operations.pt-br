---
title: Solicitar uma licença
description: Enviar uma solicitação de licença.
author: twheeloc
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveofAbsenceRequestEntry, EssWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e6c98246e94670dd5f882fcbbd1f269e57f66faf
ms.sourcegitcommit: e88ecaccd82afa3a915e41df1d4287d99da6a48a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/29/2022
ms.locfileid: "9805278"
---
# <a name="request-a-leave-of-absence"></a>Solicitar uma licença

>[!Important]
>A funcionalidade mencionada neste artigo está disponível atualmente para clientes individuais de Dynamics 365 Human Resources. Algumas ou todas as funcionalidades estarão disponíveis como parte de uma versão futura na infraestrutura do Finance após a versão Finance 10.0.26.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Você pode enviar uma solicitação de licença e ver o status das solicitações de licença no Dynamics 365 Human Resources.

## <a name="request-a-leave-of-absence"></a>Solicitar uma licença

1. No espaço de trabalho **Autoatendimento para funcionários**, selecione **Mais** (...) no grupo **Saldos de folgas**.

2. Para enviar uma solicitação de licença, selecione **Solicitar licença**.

3. Insira informações para **Tipo de licença**, **Data inicial** e **Data final**.

4. Se você precisar enviar qualquer documentação de suporte, selecione **Carregar** em **Anexos**.

5. Insira informações em **Comentário**, se necessário.

6. Selecione **Enviar** quando estiver pronto para enviar sua solicitação. Caso contrário, selecione **Salvar rascunho**.


## <a name="view-leave-of-absence-request-status"></a>Exibir status da solicitação de licença

1. No espaço de trabalho **Autoatendimento para funcionários**, selecione **Mais** (...) no grupo **Saldos de folgas**.

2. Para exibir suas solicitações de licença, selecione **Exibir licença**.

## <a name="update-a-leave-of-absence-request"></a>Atualizar uma solicitação de licença

1. No espaço de trabalho **Autoatendimento para funcionários**, no bloco **Licença**, selecione **Mais (...)**.
2. Selecione a solicitação de licença a ser atualizada e, depois, selecione **Atualizar licença**.
3. No campo **Data de término**, atualize o valor, conforme apropriado, para estender ou encurtar a licença.
4. Se a data final for confirmada, defina a opção **Confirmar data de término** como **Sim**.
5. Depois que a opção **Confirmar data de término** for definida como **Sim**, você poderá carregar um aviso de retorno ao trabalho. Depois, marque a caixa de seleção para confirmar que um aviso de retorno ao trabalho foi carregado.
6. Selecione **Enviar** para atualizar a solicitação de licença.

## <a name="cancel-a-leave-of-absence-request"></a>Cancelar uma solicitação de licença

1. No espaço de trabalho **Autoatendimento para funcionários**, no bloco **Licença**, selecione **Mais (...)**.
2. Selecione a solicitação de licença a ser cancelada e, depois, selecione **Atualizar licença**.
3. Defina a opção **Cancelar licença** como **Sim**.
4. Selecione **Enviar** para cancelar a solicitação de licença.

## <a name="importing-leave-requests-from-other-systems-or-older-systems"></a>Importando solicitações de licença de outros sistemas ou sistemas mais antigos

Para importar solicitações de licença de outro sistema, é necessário passar pelo fluxo de trabalho regular para criar as transações de licença apropriadas. Como alternativa, é possível importar as transações bancárias de licença e as solicitações de licença em um estado concluído. Observe que as transações bancárias de licença não são criadas automaticamente se você importa somente as solicitações de licença.

## <a name="see-also"></a>Consulte também

[Suspender licença](hr-leave-and-absence-suspend-leave.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
