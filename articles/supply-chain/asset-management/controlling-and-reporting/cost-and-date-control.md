---
title: Controle de custo e data
description: Este tópico explica o controle de custo e data no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2bcd1584f6a858f7589387fbfe96267b7c16176a
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918386"
---
# <a name="cost-and-date-control"></a>Controle de custo e data

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

No Gerenciamento de ativos, é possível calcular os custos para obter uma visão geral dos custos reais em comparação com os custos de orçamento em ativos, locais funcionais e ordens de serviço. Os custos reais são baseados em transações lançadas. Você também pode fazer um cálculo de data para comparar datas inicial e final agendadas com datas de início e término reais em ordens de serviço.

## <a name="cost-control-for-assets-functional-locations-and-work-orders"></a>Controle de custos para ativos, locais funcionais e ordens de serviço

Os cálculos efetuados para ativos, locais funcionais e ordens de trabalho são quase idênticos. A única diferença é que para ativos e locais funcionais, você também podem incluir subativos e sub-locais em seu cálculo. A data é a data da transação quando o registro foi feito.

1. Clique em **Gerenciamento de ativos** > **Consultas** > **Ativos** > **Controle de custos de ativos** ou **Controle de custos do local funcional**, ou **Gerenciamento de ativos** > **Consultas** > **Ordens de serviço** > **Controle de custos da ordem de serviço**.

2. Na caixa de diálogo **Controle de custos de ativos** / **Controle de custos do local funcional** / **Controle de custos da ordem de serviço**, selecione um período a ser calculado.

3. Se necessário, selecione um conjunto de dimensões financeiras para ser incluído no cálculo.

4. Selecione "Sim" no botão de alternância **Ignorar zero** se não desejar exibir resultados com custo zero.

5. Você pode usar o campo **Nível** para indicar o nível de detalhamento desejado das linhas de controle de custo em relação aos locais funcionais. Por exemplo, se você inserir o número "1" no campo e tiver uma hierarquia de localização funcional em vários níveis, todas as linhas de controles de custos para um local funcional serão mostradas no nível superior e, portanto, as horas em uma linha poderão ser adicionadas em locais funcionais localizados em um nível inferior. Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas de controle de custos em todo o nível do local funcional ao qual elas estão relacionadas.

6. Selecione "Sim" no botão de alternância **Mostrar custo comprometido aberto** se quiser incluir essa coluna no cálculo.

7. Selecione "Sim" no botão de alternância **incluir subativos** para exibir custos relacionados a subativos como linhas separadas.

8. Para limitar a pesquisa, você poderá selecionar ativos específicos/locais funcionais/ordens de trabalho na Guia Rápida **Registros a serem incluídos**.

9. Clique em **OK**para iniciar o cálculo.

A figura abaixo mostra um exemplo da caixa de diálogo **Controle de custos de ativos**.

![Figura 1](media/01-controlling-and-reporting.png)

10. Nos grupos do Painel de Ações **Agrupar por...** na página **Controle de custos de ativos**, clique nos botões relevantes para mostrar o nível de detalhe necessário do cálculo. Os botões do painel de ações selecionados são destacados. Clique em um botão para ativá-los ou desativá-los.

A figura abaixo mostra um exemplo de resultados de cálculo em **Controle de custos de ativos**.

![Figura 2](media/02-controlling-and-reporting.png)

Outra maneira de fazer um cálculo de custo é selecionar vários ativos em **Todos os ativos** ou **Ativos ativos**. Depois, você clica no botão **Controle de custo** na guia **Geral**. Na caixa de diálogo **Controle de custos de ativos**, os ativos selecionados são inseridos automaticamente no campo **Ativo** na Guia Rápida **Registros a serem incluídos**. Após clicar em **OK**, um cálculo de custo dos ativos selecionados será mostrado. O mesmo procedimento pode ser feito para locais funcionais em **Todos os locais funcionais** ou **Locais funcionais ativos**, e para ordens de serviço **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

>[!NOTE]
>O campo **Orçamento original** mostra os custos do orçamento da previsão da ordem de serviço. O campo **Custo comprometido** mostra o valor total das despesas que uma entidade legal se comprometeu a pagar. O campo **Custo comprometido aberto** mostra compromissos de pagamento por itens, horários e serviços que você solicitou ou recebeu, mas ainda não pagou. Após o lançamento de todos os registros de consumo, os custos relacionados serão incluídos no campo **Custo real**.

## <a name="work-order-date-control"></a>Controle de data da ordem de serviço

Use esta página para obter uma visão geral das datas inicial e final esperadas em comparação com as datas inicial e final reais nas ordens de serviço.

1. Clique em **Gerenciamento de ativos** > **Consultas** > **Ordens de trabalho** > **Controle de data da ordem de serviço**.

2. Clique em **Calcular**.

3. Selecione um local funcional no campo **Local funcional**.

4. Insira o período para o qual você deseja fazer o cálculo nos campos **Data inicial** e **Data final**. Todas as ordens de serviço com início esperado dentro do período serão incluídas.

5. Clique em **OK**.

6. Nos grupos do Painel de Ações **Agrupar por...**, clique nos botões relevantes para mostrar o nível de detalhe necessário do cálculo. Os botões do painel de ações selecionados são destacados. Clique em um botão para ativá-los ou desativá-los.

A figura abaixo mostra um exemplo de resultados de cálculo em **Controle de data da ordem de serviço**.

![Figura 3](media/03-controlling-and-reporting.png)

- O campo **Atraso inicial médio** mostra a diferença de dias entre a data inicial agendada de uma ordem de serviço e a data inicial real. Se, por exemplo, a data inicial real for dois dias antes da data inicial agendada, "-2" será exibido neste campo.  
- O campo **Atraso final médio** mostra a diferença de dias entre a data final agendada de uma ordem de serviço e a data final real. Se, por exemplo, a data final real foi três dias após a data final programada, "3" será exibido neste campo.  
- Os campos **Ocorrências** mostram o número de vezes em que ocorrem desvios em relação à data inicial agendada e real e a data final agendada e real na ordem de serviço.
