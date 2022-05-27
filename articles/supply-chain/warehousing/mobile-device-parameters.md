---
title: Parâmetros de dispositivo móvel global
description: Este tópico explica como definir configurações de dispositivo móvel na página Parâmetros do gerenciamento de depósito.
author: Mirzaab
ms.date: 08/13/2021
ms.topic: article
ms.search.form: WHS
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-13
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 0ae04c86ff1eafb649fcef7c34ace66bdc3e5cb8
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8679155"
---
# <a name="global-mobile-device-parameters"></a>Parâmetros de dispositivo móvel global

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar parâmetros globais do gerenciamento de depósito que afetam a forma como o sistema interage com dispositivos móveis.

Para obter mais informações sobre como configurar trabalhadores de depósito, consulte [Gerenciar trabalhador de depósito](manage-warehouse-workers.md). Para obter mais informações sobre o tratamento da placa de licença em dispositivos móveis, consulte [Recebimento da placa de licença por meio do aplicativo móvel Warehouse Management](warehousing-mobile-device-app-license-plate-receiving.md). Para obter mais informações sobre os processos de contagem de ciclo, consulte [Contagem de ciclos](cycle-counting.md) e [Cenários de exemplo de contagem de ciclos](cycle-counting-scenarios.md).

## <a name="open-the-warehouse-management-parameters-page"></a>Abra a página Parâmetros do gerenciamento de depósito

Para abrir a página **Parâmetros do gerenciamento de depósito**, acesse **Gerenciamento de depósito \> Configuração \> Parâmetros do gerenciamento de depósito**. Em seguida, você pode definir os campos relacionados ao trabalho do dispositivo móvel, conforme descrito na próxima seção deste tópico.

## <a name="mobile-device-fasttab-on-the-general-tab"></a>Guia Rápida de dispositivo móvel na guia Geral

As configurações globais do dispositivo móvel se encontram na Guia Rápida **Dispositivo móvel** na guia **Geral** da página **Parâmetros do gerenciamento de depósito**. Os campos a seguir estão disponíveis.

| Campo | descrição |
|---|---|
| Tipo de nota do dispositivo móvel | Selecione o tipo de informação que é mostrada para trabalhadores durante a separação de ordem de venda. |
| Limite de quantidade verificada | Insira a quantidade máxima de itens que um trabalhador pode examinar durante cada sessão, usando um item de menu de dispositivo móvel que tenha um valor **Processo de criação de trabalho** de *Ajuste de entrada*. Este campo não afeta as verificações feitas usando qualquer outro tipo de item de menu. |
| Usar log de sessão de dispositivo móvel | Defina esta opção como *Sim* para manter um log do histórico de entradas do trabalhador. Para exibir o registro, acesse **Sessões de usuários de trabalho \> Consultas e relatórios \> Logs do dispositivo móvel \> Sessões do usuário de trabalho**. |
| Número de erros armazenados | Insira o número máximo de registros de erro que o sistema deve armazenar. Para exibir o log de erros, acesse **Sessões de usuários de trabalho \> Consultas e relatórios \> Logs do dispositivo móvel \> Sessões do usuário de trabalho**. |
| Diário de transferência de depósito padrão | Selecione o diário que é usado quando os trabalhadores usam um dispositivo móvel para mover produtos de um depósito para outro. |
| Permitir o registro da linha da ordem de compra na revisão externa | Defina esta opção como *Sim* se os trabalhadores puderem usar um dispositivo móvel para registrar linhas de ordem para ordens de compra com um valor **Status de aprovação** de *Em revisão externa*. Defina esta opção como *Não* para impedir que trabalhadores registrem linhas para ordens de compra que estão na revisão externa. |
| Habilitar suporte a RSAT | O campo habilita o validador da tarefa do aplicativo móvel Warehouse Management, que registra e valida cada etapa que o aplicativo executa. Como esse processo pode reduzir significativamente o desempenho do sistema, você deve habilitar o validador somente durante os testes. Você nunca deve habilitá-lo em um ambiente de produção. |
