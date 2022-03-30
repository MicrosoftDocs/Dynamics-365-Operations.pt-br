---
title: Diferença inesperada entre os dados de solicitação e sessão durante os testes
description: Ocorre uma diferença inesperada entre os dados da solicitação e da sessão em resultados da validação da tarefa do aplicativo de depósito.
author: mamuszal
ms.date: 03/11/2022
ms.topic: troubleshooting
ms.search.form: WHSValidatorRunInstance_executeRun
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mamuszal
ms.search.validFrom: 2022-03-11
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: da8f0506a76b0d0cc02bfc2e1bff01b4ddccb578
ms.sourcegitcommit: 941119133be1765f653d5d5270dfdf58466e1d07
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2022
ms.locfileid: "8456930"
---
# <a name="unexpected-difference-between-request-and-session-data-during-testing"></a>Diferença inesperada entre os dados de solicitação e sessão durante os testes

Código de erro: WarehouseMobileDeviceRequestInputValidationError

## <a name="symptoms"></a>Sintomas

Quando você usa a [estrutura de validação da tarefa do aplicativo de depósito](/dynamics365-release-plan/2019wave2/dynamics365-supply-chain-management/warehouse-app-task-validation-rsat), o validador retorna a seguinte mensagem de erro:

> Diferença inesperada entre os dados de solicitação e sessão. O protocolo XML de de dispositivos móveis de depósito foi violado.REQUEST_XML_TAMPERING

## <a name="cause"></a>Causa

O erro ocorre quando a saída da última etapa que foi executada com êxito na execução de teste não corresponde à entrada registrada para a próxima etapa. Essa situação pode surgir porque o validador de tarefas não usa a saída de uma etapa anterior como entrada para uma etapa sucessiva. Em vez disso, ele usa XML gravado como entrada para cada etapa.

Na maioria dos casos, o erro ocorre quando você executa novamente uma tarefa, mas o teste requer alguns registros que foram modificados ou removidos por uma execução anterior da mesma tarefa.

## <a name="resolution"></a>Resolução

A execução de teste de validação da tarefa do aplicativo de depósito não é uma operação idempotente, mas modifica os dados subjacentes. Portanto, antes de executar uma tarefa novamente, talvez seja necessário redefinir os dados relevantes.

1. Revise o XML de saída da última etapa de teste bem-sucedida para determinar onde sua execução de teste parou.
1. Inspecione seu teste e verifique se todas as ordens de venda, ordens de transferência, cabeçalhos de trabalho e outros registros necessários ainda estão presentes e no estado esperado.
1. Crie ou edite novamente os registros ausentes ou modificados. Como alternativa, crie uma nova configuração de teste e projete o teste para usar registros existentes válidos.
