---
title: Processar qualificação da inscrição
description: Este artigo explica como executar o processo de qualificação da inscrição.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 69ea23e4051a6975a5892cd027777c5a88472509
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5111513"
---
# <a name="process-enrollment-eligibility"></a>Processar qualificação da inscrição

Este artigo explica como executar o processo de qualificação da inscrição.

1. No espaço de trabalho **Gerenciamento de benefícios**, em **Processando**, selecione **Processamento da qualificação da inscrição**.

2. No caixa de diálogo **Executar o processamento da qualificação de inscrição no benefício**, especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **Período de inscrição** | O período de inscrição para processar a qualificação da inscrição. |
   | **Pessoa jurídica em geral** | A entidade legal para processar a qualificação da inscrição. |
   | **Trabalhador** | O trabalhador para processar a qualificação da inscrição. Se você deixar esse campo em branco, a qualificação da inscrição será processada para todos os trabalhadores. |
   | **Plano de benefícios** | O plano de benefícios para processar a qualificação da inscrição.

3. Se você deseja executar o processo em segundo plano, selecione **Executar em segundo plano** e execute as seguintes tarefas:

   1. Insira informações para o processo.

   2. Para configurar um trabalho recorrente, selecione **Recorrência**, insira as informações de recorrência e selecione **OK**.

   3. Para configurar um alerta de trabalho, selecione **Alertas**, selecione os alertas a receber e, em seguida, selecione **OK**.

   4. Selecione **OK**. O processo será executado com os parâmetros definidos por você.

4. Selecione **OK**.

## <a name="view-process-results"></a>Exibir resultados do processo

Este artigo explica como exibir os resultados de processo de qualificação.

1.  No espaço de trabalho **Gerenciamento de benefícios**, em **Processando**, selecione **Resultados do processo**.

2.  No formulário **Resultados do processo**, os seguintes campos são especificados:

   | Campo | descrição |
   | --- | --- |
   | **ID de processo** | A identificação exclusiva da combinação de trabalhador, entidade legal e execução do processo. |
   | **Tipo de processo** | Isso identifica o processo que foi executado. Por exemplo: Inscrição. |
   | **Carimbo de data/hora** | A hora em que o processo de qualificação foi executado. |
   | **Pessoa jurídica em geral** | A entidade legal especificada durante o processo de inscrição. |
   | **Trabalhador** | O trabalhador que foi processado. |
   | **Plano | O plano de benefícios para o qual o registro foi tentado. |
   | **Regra de qualificação** | A regra de qualificação que foi processada. Se um erro tiver sido encontrado antes da qualificação ser executada, ele ficará em branco. Por exemplo: se a compensação não foi definida para um trabalhador, o processo de qualificação não será executado e este campo será deixado em branco. |
   | **Status do resultado** | Ele será Qualificado ou Não qualificado. O status do resultado será inelegível se o trabalhador não atender aos critérios da regra de qualificação, se o trabalhador estiver sem informações necessárias, como uma frequência de pagamento ou uma remuneração fixa, ou se houver informações ausentes no plano de benefícios que impedem que os trabalhadores sejam inscritos. |
   | **Mensagem de resultado** | Indica por que um trabalhador não é elegível para um plano de benefícios ou se a regra de qualificação foi aprovada. |

