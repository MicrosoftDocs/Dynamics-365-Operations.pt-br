---
title: Ordens de serviço criadas automaticamente
description: Você pode gerar ordens de serviço com base em um contrato de serviço para o período de vigência do contrato de serviço.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7b38a0049c9d8c845aa02780fe8de0e20d6ea56a8425fa9f10fbb53d55a6265a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6764755"
---
# <a name="automatically-create-service-orders"></a>Ordens de serviço criadas automaticamente 

[!include [banner](../includes/banner.md)]


Você pode gerar ordens de serviço com base em um contrato de serviço para o período de vigência do contrato de serviço.

As ordens de serviço geradas a partir de um contrato de serviço são todas anexadas ao contrato de serviço.

As ordens de serviço são geradas automaticamente a partir destas configurações:

  - O intervalo do contrato de serviço que é definido nas linhas do contrato. Esse intervalo indica a frequência com que são criadas linhas de ordem de serviço. Para obter mais informações, consulte [Intervalos de serviço](service-intervals.md).

  - O período especificado para definir o período de serviço nos campos **Data de início** e **Data de término** no formulário **Criar ordens de serviço**. Para obter mais informações, consulte [Criar ordens de serviço automaticamente](create-service-orders-automatically.md).

  - A opção **Combinar ordens de serviço** no cabeçalho do contrato de serviço. Essa opção define se as linhas de ordem de serviço geradas a partir de um contrato de serviço incluem ordens de serviço de acordo com funcionário, tarefa de serviço, objeto de serviço ou contrato de serviço. Para obter mais informações, consulte [Combinar ordens de serviço](combine-service-orders.md).

  - A opção **Janela de tempo** na linha de contrato de serviço. A janela de tempo define até que ponto uma linha de ordem de serviço pode se mover em relação à data de cálculo. Para obter mais informações, consulte [Janelas de horas](time-windows.md).


> [!NOTE]
> <P>Se o dia especificado para uma ordem de serviço não estiver aberto no calendário selecionado no formulário <STRONG>Parâmetros de gerenciamento de serviços</STRONG>, uma mensagem indicará que há um conflito de calendário. Você pode ignorar essa mensagem com segurança; a ordem de serviço será criada mesmo que o dia esteja fechado no calendário.</P>

## <a name="example-1"></a>Exemplo 1

O contrato de serviço vigora desde de 1º de janeiro de 2012 até 31 de dezembro de 2012. Se o período de serviço especificado no formulário **Criar ordens de serviço** é de 1º de novembro de 2012 até 1º de fevereiro de 2013, ordens de serviço serão criadas desde 1º de novembro de 2012 até 31 de dezembro de 2012.

## <a name="example-2"></a>Exemplo 2

O contrato de serviço vigora desde de 1º de janeiro de 2012 até 31 de dezembro de 2012. Duas linhas de contrato de serviço são anexadas ao contrato. A primeira linha de contrato de serviço tem uma data inicial de 2 de janeiro de 2012 e final de 1º de março de 2012. A segunda linha de contrato de serviço tem uma data inicial de 1º de abril de 2012 e final de 31 de dezembro de 2012. Especifique um período no formulário **Criar ordens de serviço** que é de 1º de outubro de 2012 a 31 de dezembro de 2012. Portanto, as ordens de serviço serão geradas somente para a segunda linha de contrato de serviço porque as datas de início e fim da primeira linha são anteriores ao período especificado para a ordem de serviço.

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]