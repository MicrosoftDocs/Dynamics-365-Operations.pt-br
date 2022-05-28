---
title: Configurar parâmetros para a automação do processo de cobranças
description: Este tópico descreve os parâmetros que afetam os processos de cobrança automatizados e fornece orientação para defini-los, de forma que o processo automatizado reflita suas intenções e expectativas.
author: JodiChristiansen
ms.date: 08/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: e7a7e048a371fc90456368206b91c29c4b1264d5
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734386"
---
# <a name="configure-parameters-for-collection-process-automation"></a>Configurar parâmetros para a automação do processo de cobranças

[!include [banner](../includes/banner.md)]

Este tópico descreve os parâmetros que afetam os processos de cobrança automatizados e fornece orientação para defini-los, de forma que o processo automatizado reflita suas intenções e expectativas. Para obter informações sobre como automatizar processos de cobrança, consulte [Automação do processo de cobranças](collections-process-automate.md).

## <a name="general"></a>Geral
Insira um número na **Porcentagem de clientes por tarefa em lotes** para determinar o número de tarefas de lote por processo de automação. Defina **Lançar Cartas de cobrança automaticamente** como **Sim**, dessa forma, o tipo de ação de carta de cobrança lançará a carta durante a automação. Defina **Criar atividades para automação** como **Sim** para criar e fechar atividades para tipos de ação não atividades a fim de exibir todas as etapas automatizadas feitas em uma conta. Defina o número de dias que o histórico de cobrança é armazenado no **histórico Dias para manter a automação do processo de cobranças**. Quando uma fatura alcançar a última etapa do processo de cobrança, ela não será usada para criar futuros tipos de ação de automação do processo, se **a etapa Excluir fatura depois de ativar o último processo** estiver definida como **Sim**. A próxima fatura mais antiga determina a próxima etapa de automação do processo para garantir que as ações de automação do processo de cobrança continuem. 

## <a name="payment-predictions"></a>Previsões de pagamento
A partir da versão 10.0.21, as previsões de pagamento do Cliente, encontradas no Finance insights, projeta se uma fatura será paga no prazo, atrasada ou muito atrasada. Você pode configurar cada uma dessas categorias no Finance insights. Se as faturas forem previstas para pagamento atrasado, é importante iniciar o processo de cobrança antes que a fatura vença. Essas previsões podem ser usadas para criar atividades de cobrança quando são executadas automações do processo de Cobranças. Defina **Habilitar previsões de pagamento** como **Sim** para usar previsões de pagamento de cliente para criar atividades de cobranças com base na probabilidade de que a fatura seja paga com atraso. 

Para obter mais informações sobre Previsões de pagamento do cliente e Finance insights, consulte [Previsões de pagamento do cliente](payment-insights-overview.md).

Quando o modelo de previsão de pagamento do cliente é executado, ele atribui uma porcentagem à previsão da fatura que está sendo paga no prazo, atrasada ou muito atrasada. Você pode usar essas informações para iniciar automaticamente as atividades de cobrança usando a Automação do processo de cobranças nos casos em que o pagamento atrasado é esperado. Você pode exibir essas porcentagens nas páginas de **Previsões de pagamento por cliente** ou **Previsões de pagamento por transação** em **Crédito e cobranças > Cobranças**. 

Se a previsão de pagamento média para uma fatura do cliente for menor do que a porcentagem de avaliação comparativa, nenhuma atividade será criada. Se a previsão da fatura for maior ou igual à porcentagem de avaliação comparativa, uma atividade será criada por cliente. Para **Previsão: Atraso**, informe a **Porcentagem de avaliação comparativa** de quando a automação do processo de cobrança deve criar atividades de cobrança. Esse é um valor agregado tanto atrasado quanto muito atrasado. Selecione um **Modelo de documento comercial** a ser usado para a atividade criada ou crie um novo. Isso identifica o **Tipo**, **Finalidade** e **Dias até a atividade ser fechada**. Insira **Observações** que serão padrão como a descrição quando a atividade for criada. Para **Previsão: Muito Atrasado**, informe a **Porcentagem de avaliação comparativa** de quando a automação do processo de cobrança deve criar atividades de cobrança para um cliente previsto para pagar faturas muito tarde. Selecione um **Modelo de documento comercial** a ser usado para a atividade criada. Isso identifica o **Tipo**, **Finalidade** e **Dias até a atividade ser fechada**. Insira **Observações** que serão padrão como a descrição quando a atividade for criada. 

### <a name="example"></a>Exemplo
Se a porcentagem de benchmark atrasada for definida para 60%. Quando as previsões de pagamento do cliente são executadas para cada fatura, o sistema atribui uma porcentagem à previsão da fatura que está sendo paga no prazo, atrasada ou muito atrasada. Se a previsão de pagamento na qual a fatura for paga em atraso for 59% ou menos, nenhuma atividade de cobrança será criada para a fatura pelo processo de coleta automatizado. Se a previsão de pagamento do cliente para uma fatura for maior ou igual a 60%, uma atividade de coleta será criada durante a automação do processo de cobranças. 

> [!NOTE]
> A previsão de muito atrasada é avaliada antes da previsão de atraso porque o atraso inclui faturas que estão previstas para pagamento atrasado. O processo de cobranças só gera uma atividade, se a fatura estiver em avaliações comparativas atrasadas ou muito atrasadas. Nesse caso, o sistema usará a atividade muito atrasada e o documento comercial, pois muito atrasado é a prioridade mais alta. Quaisquer outras ações que já tenham sido geradas não serão geradas uma segunda vez.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
