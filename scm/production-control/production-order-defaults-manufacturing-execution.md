---
title: "Padrões de ordem de produção na execução de fabricação"
description: 
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: JmgProdParameters
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 70073
ms.assetid: 620944ae-3e20-444a-807e-65495f160904
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: cc12a8d75ead1577cf0b31a0dbf3ac072c47dc08
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="production-order-defaults-in-manufacturing-execution"></a>Padrões de ordem de produção na execução de fabricação

[!include[banner](../includes/banner.md)]




É necessário considerar cuidadosamente todas as configurações na página **Padrões de ordem de produção** antes dos trabalhadores começarem a criar registros nos trabalhos de produção. Se sua empresa usar a funcionalidade multissite, você pode desejar configurar padrões diferentes para ordens de produção para cada site. Os padrões de ordem para a integração com Controle de produção são configurados na página **Padrões da ordem de produção**:

-   **Geral** – padrões da ordem geral para trabalhos de produção na execução de Fabricação.
-   **Início** – os padrões da ordem usados quando trabalhos ou operações de produção são iniciados.
-   **Operações** - padrões da ordem aplicados a trabalhos ou a operações de produção e aos comentários sobre as operações durante o processo de produção.
-   **Relatar como concluído** - padrões da ordem aplicados quando itens são relatados como concluídos na última operação de uma ordem de produção.
-   **Validação de quantidade** – padrões da ordem para validação de quantidades inicial e de comentário em ordens de produção.

## <a name="types-of-production-jobs"></a>Tipos de trabalhos de produção
Na guia **Operações**, selecione os tipos de trabalhos de produção que necessitam de registro na página **Registro de trabalho**. Em geral, os funcionários fazem registro dos trabalhos de configuração e dos trabalhos de processo. No entanto, se o agendamento de trabalho for aplicado, será possível selecionar outros tipos de trabalho, como trabalhos de transporte, dos quais os trabalhadores também deverão fazer registros quando uma ordem de produção for processada. **Importante:** verifique se todos os tipos de trabalho relevantes estão selecionados. Caso contrário, os trabalhos podem não estar disponíveis para registro na página **Registro de trabalho**. Alinhe as seleções com as seleções feitas na coluna **Gerenciamento de trabalho** na página **Grupos de roteiros**. Se **Gerenciamento de trabalhos** for selecionado no grupo de roteiros, o tipo de trabalho será relatado como concluído na ordem de produção. Esse relato ocorrerá quando o trabalho for relatado como concluído em Execução de fabricação. Quando todos os tipos de trabalhos para os quais **Gerenciamento de trabalhos** estiver selecionado tiverem sido relatados como concluídos em uma operação, Execução de fabricação também relatará a operação como concluída. **Observação:** alguns tipos de trabalho podem ser relatados manualmente por meio de diários de produção. Nesse caso, selecione **Gerenciamento de trabalhos** como o tipo de trabalho, mas não selecione o tipo de trabalho para registro na guia **Operações** da página **Padrões da ordem de produção**.

## <a name="bom-consumption-and-picking-list-journals"></a>Diários de consumo de BOM e da lista de separação
Os materiais podem ser configurados de forma a serem consumidos de forma automática ou manual durante a produção. O consumo automático é controlado pelo princípio de liberação configurado nas linhas de BOM (lista de materiais) e pela configuração do campo **Consumo automático de BOM** nos padrões da ordem de produção. O consumo automático pode ser configurado para que ocorra quando uma ordem de produção for iniciada ou relatada como concluída. Como alternativa, ela poderá ocorrer no nível do trabalho quando um trabalho for iniciado ou concluído.

### <a name="controlling-material-consumption-when-a-production-order-is-started"></a>Controle de consumo de materiais quando uma ordem de produção é iniciada

O consumo de materiais durante o início de uma ordem de produção é controlado pelo campo **Consumo automático de BOM** na página **Início**. Os valores a seguir estão disponíveis:

-   **Princípio de liberação** – quando uma ordem de produção é iniciada, as quantidades de materiais serão consumidas de acordo com o princípio de liberação definido nas linhas da BOM de produção. Somente as linhas de material em que o princípio de liberação está definido como **Início** serão consumidas durante o início da produção.
-   **Sempre** – as quantidades de materiais proporcionais à quantidade iniciada sempre serão consumidas.
-   **Nunca** – as quantidades de materiais nunca serão consumidas.

### <a name="controlling-material-consumption-when-a-production-job-is-started-or-completed"></a>Controle de consumo de materiais quando um trabalho de produção é iniciado ou concluído

O consumo de materiais durante o início ou a conclusão de um trabalho de produção é controlado pelo campo **Consumo automático de BOM** na guia **Operações**. Os valores a seguir estão disponíveis:

-   **Princípio de liberação** – quando uma quantidade em um trabalho de produção é iniciada ou concluída, as quantidades de materiais serão consumidas de acordo como princípio de liberação definido nas linhas da BOM de produção. Somente as linhas de material em que o princípio de liberação está definido como **Início** ou **Fim** serão consumidas durante o início da produção.
-   **Sempre** – as quantidades de materiais proporcionais à quantidade iniciada no trabalho sempre serão consumidas.
-   **Nunca** – as quantidades de materiais nunca serão consumidas.

### <a name="controlling-material-consumption-when-a-production-order-is-reported-as-finished"></a>Controle de consumo de materiais quando uma ordem de produção é relatada como concluída

O consumo de materiais durante o processo Relatar como concluído de uma ordem de produção é controlado pelo campo **Consumo automático de BOM** na página **Início**. Os valores a seguir estão disponíveis:

-   **Princípio de liberação** – quando uma ordem de produção é relatada como concluída, as quantidades de materiais serão consumidas de acordo com o princípio de liberação definido nas linhas da BOM de produção. Somente as linhas de material em que o princípio de liberação está definido como **Fim** serão consumidas.
-   **Sempre** – as quantidades de materiais proporcionais à quantidade relatada como concluída sempre serão consumidas.
-   **Nunca** – as quantidades de materiais nunca serão consumidas.





