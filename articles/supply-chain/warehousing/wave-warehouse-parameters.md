---
title: Parâmetros de depósito para o processamento do ciclo
description: Este artigo descreve como configurar parâmetros de depósito para o processamento do ciclo. Você pode usar o processamento do ciclo para agrupar o trabalho de separação para várias ordens de serviço em um único ciclo.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2a64cba837faf84f3e8470a9831d1641213a5cc4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909602"
---
# <a name="warehouse-parameters-for-wave-processing"></a>Parâmetros de depósito para o processamento do ciclo

[!include [banner](../includes/banner.md)]

Este artigo descreve como configurar parâmetros de depósito para o processamento do ciclo. Você pode usar o processamento do ciclo para agrupar o trabalho de separação para várias ordens de serviço em um único ciclo.

Para usar o processamento do ciclo, especifique o seguinte na página **Parâmetros de gerenciamento de depósito**:

- Se você pode processar ciclos usando um trabalho em lotes.
- Se você coleta informações em um arquivo de log quando os ciclos são processados.

## <a name="set-up-warehouse-management-parameters-for-wave-processing"></a>Configurar parâmetros de gerenciamento de depósito para o processamento do ciclo

Para configurar parâmetros de depósito para o processamento do ciclo, siga estas etapas:

1. Acesse **Gerenciamento de depósito** \> **Configuração** \> **Parâmetros de gerenciamento de depósito**.

1. Na Guia Rápida **Processamento do ciclo**, faça as seguintes configurações:

    - **Grupo de lotes de processamento do ciclo** – selecione o grupo de lotes a ser usado ao processar ciclos usando trabalhos em lotes. O grupo de lotes especifica o servidor no qual o trabalho em lotes será executado.
    - **Processar ciclos em lotes** – escolha se os ciclos devem ser habilitados para serem processados automaticamente por um trabalho em lotes. Você deve definir isso como *Sim* para usar o processamento paralelo. Você configura o trabalho em lotes na página **Processar ciclos**. (Consulte também a observação no final desta lista).
    - **Criar log de progresso do ciclo** – escolha se o sistema deverá gerar um registro de log sempre que a alocação de um item e suas dimensões começarem e terminarem. Você só deverá habilitar esse log quando precisar dele, por exemplo, durante o teste inicial ou para solução de problemas. Para obter mais informações, consulte [Alocação do ciclo](wave-allocation-method.md).
    - **Criar log de histórico de processamento do ciclo** – escolha se deseja salvar automaticamente as informações sobre um ciclo em um arquivo de log após o processamento do ciclo, incluindo durante o processamento paralelo de alocações pendentes. Normalmente, você deverá habilitá-lo apenas durante a solução de problemas, pois ele adiciona sobrecarga extra. Para exibir o log, Acesse **Gerenciamento de depósito \> Ciclos de saída \> Log de histórico de processamento do ciclo**. Para obter mais informações, consulte [Criação e processamento do ciclo](wave-processing.md).
    - **Criar log de histórico de transporte em contêineres** – escolha se deseja salvar automaticamente as informações sobre o transporte em contêineres para um ciclo em um arquivo de log depois que o ciclo for processada. Para exibir o log, Acesse **Gerenciamento de depósito \> Embalagem e transporte em contêineres \> Histórico de transporte em contêineres**.
    - **Aguardar bloqueio (ms)** – insira o tempo, em milissegundos, que uma etapa de alocação aguardará um recurso do sistema que está bloqueado por outra etapa de alocação. Quando esse tempo é excedido, a onda não é processada e uma mensagem de erro é exibida.

1. Na Guia Rápida **Liberação para depósito**, faça a seguinte configuração:

    - **Erro na falha de lote** – escolha se deseja gerar um erro quando um trabalho em lotes de liberação para depósito falhar. Se isso for habilitado, os trabalhos com falha terminarão com um status *Erro*. Se isso for desabilitado, os trabalhos com falha terminarão com um status *Encerrado*.

> [!NOTE]
> No modelo de onda usado para processar a onda, você pode especificar as configurações que automatizam o processamento de onda. Se você configurar um plano para o trabalho em lotes, deverá coordenar o tempo com as configurações para a automação no modelo de onda. Para obter mais informações, consulte [Criar um modelo do ciclo](wave-templates.md).
>
> Se estiver usando *Gerenciamento de transporte* e *Gerenciamento de depósito avançado*, você poderá especificar se haverá a consolidação de cargas no processamento de um ciclo. Por exemplo, isso será útil quando várias cargas pequenas puderem ser enviadas ao mesmo tempo. Para consolidar cargas ao processar um ciclo, na guia **Cargas**, marque a caixa de seleção **Consolidar cargas durante o processamento do ciclo**.</P>

## <a name="set-up-full-or-partial-reservation-for-production-waves"></a>Configurar a reserva total ou parcial de ciclos de produção

Para ordens de venda e ordens de kanban, o estoque será reservado antes de a ordem ser liberada para o depósito. Caso contrário, os itens ou as linhas de alocação não poderão ser processadas em uma onda. Entretanto, as ordens de produção são ligeiramente mais flexíveis. Para ordens de produção, você pode especificar o seguinte:

- Permita que ordens de produção sejam liberadas para o depósito, embora não seja possível reservar todo o material. Se você selecionar esta opção, repita manualmente a liberação para o processo de armazém quando o material adicional for disponibilizado. Por exemplo, isso será útil se você tiver o material necessário para iniciar uma produção, e puder aguardar até que o material adicional seja disponibilizado.
- Exija que todo o material seja reservado antes que uma ordem possa ser liberada para o depósito.

Para exigir a reserva total ou permitir a reserva parcial, siga estas etapas:

1. Acesse **Controle de produção** \> **Configuração** \> **Parâmetros de controle de produção**.
1. Na guia **Geral**, no campo **Liberar para depósito**, selecione a configuração padrão.
