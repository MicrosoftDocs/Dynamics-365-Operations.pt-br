---
title: Intervalos de serviço
description: O intervalo de serviço indica a frequência com a qual as linhas de ordem de serviço são criadas para linhas de contrato de serviço quando você cria ordens de serviço.
author: ShylaThompson
manager: AnnBe
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 10078cbd02209126e9655b823fcf844b692a4794
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562640"
---
# <a name="service-intervals"></a>Intervalos de serviço

[!include [banner](../includes/banner.md)]

O intervalo do contrato de serviço indica a frequência com a qual as linhas de ordem de serviço são criadas para linhas de contrato de serviço quando você cria ordens de serviço automaticamente.

Quando você cria ordens de serviço de maneira automática, as linhas da ordem de serviço são criadas de acordo com o intervalo especificado para a linha de contrato de serviço a partir da data de início da linha do contrato.

Se o campo **Intervalo** de uma linha de contrato de serviço na página **Contratos de serviço** estiver em branco, a linha será um evento ocasional e não será usada para criar ordens de serviço repetidamente.

## <a name="example"></a>exemplo

Este exemplo ilustra como um intervalo de serviço afetará as linhas de contrato de serviço e linhas de ordem de serviço em uma ordem de serviço.

### <a name="create-a-service-agreement"></a>Criar um contrato de serviço

Primeiro, crie um contrato de serviço e defina a opção **Combinar ordens de serviço** como **Por contrato de serviço**.

1. Clique em **Contratos de serviço**
2. No **Painel de Ação**, na guia **Contrato de serviço**, no grupo **Novo**, clique em **Contrato de serviço** para criar um novo contrato de serviço.
3. Insira uma descrição, selecione um projeto no campo **ID do projeto** e insira uma data no campo **Data de início**.
4. No campo **Combinar ordens de serviço**, selecione **Por contrato de serviço**.

Você criou o seguinte contrato de serviço:

| Project      | Data inicial                                                                         |
|--------------|------------------------------------------------------------------------------------|
| Seu projeto | A data especificada para o projeto. Neste exemplo, a data atual é usada. |

### <a name="create-a-service-agreement-line"></a>Criar uma linha de contrato de serviço

Em seguida, crie uma linha de contrato de serviço que tenha o tipo de transação **Hora**.

Para concluir essa parte do exemplo, crie um intervalo de serviço de 10 dias na página **Intervalos de serviço**. 

1. Selecione o contrato de serviço que você acabou de criar. 
2. Na Guia Rápida **Linhas**, clique no botão **Adicionar** para criar uma nova linha no painel inferior da página **Contratos de serviço**.
3. No campo **Tipo de transação**, selecione **Hora**.
4. No campo **Trabalhador**, selecione o trabalhador que fornecerá o serviço.
5. No campo **Intervalo de serviço**, selecione o intervalo de 10 dias.

Você acabou de criar uma linha de contrato de serviço com as seguintes informações:

| Tipo de transação | Data de início                               | Intervalo de serviços |
|------------------|------------------------------------------|------------------|
| Hora             | A data atual.                        | A cada 10 dias    |
| Trabalhador           | O trabalhador que realizará o serviço. |                  |

Nenhuma janela de tempo especificada para a linha. 

### <a name="create-planned-service-orders"></a>Criar ordens de serviço planejadas

Agora você pode criar ordens de serviço e linhas de ordem de serviço planejadas para o mês seguinte.

1. Na página **Contratos de serviço**, no **Painel de Ação**, na guia **Entregar**, clique em **Ordens de serviço planejadas**.
2. Na página **Criar ordens de serviço**, insira a data atual no campo **A partir da data** e uma data que seja a um mês da data atual no campo **Até a data**.
3. Defina o controle deslizante **Hora** como **Sim**. 
4. Clique em **OK**.

Como não há agrupamento na ordem de serviço (definido pela opção **Por contrato de serviço** no campo **Combinar ordens de serviço**), uma linha de ordem de serviço é criada por ordem de serviço.

### <a name="service-orders-created"></a>Ordens de serviço criadas

Três linhas de ordem de serviço foram criadas nesse intervalo de tempo que você especificou na caixa de diálogo **Criar ordens de serviço**. Você pode visualizar as linhas da ordem de serviço na página **Contratos de serviço** (**Painel de Ação** \> guia **Entregar** \>botão**Exibir** ).

## <a name="related-topics"></a>Tópicos relacionados

[Configurar intervalos de serviço](set-up-service-intervals.md)  

