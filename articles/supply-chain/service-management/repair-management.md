---
title: Gerenciamento de reparos
description: Agrupe os problemas sistematicamente a fim de ajudar na sugestão de soluções que tiveram êxito no passado.
author: sorenva
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAConditionTable, SMASymptomArea, SMADiagnosisArea, SMAResolutionTable, SMARepairStage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f969224f48cdb1f12b48b9f5d839d7c88168e87d
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8674243"
---
# <a name="repair-management"></a>Gerenciamento de reparos       

[!include [banner](../includes/banner.md)]


Para o gerenciamento de reparos, é possível agrupar os problemas de forma sistemática. Isso é para ajudar com a sugestão de soluções bem-sucedidas no passado.

Você configura sintomas, diagnóstico e as configurações de resolução. Qualquer um deles poderá ser aplicado posteriormente, quando você receber um item semelhante para reparo. Você também poderá configurar estágios de reparo que podem acompanhar o progresso de um problema de reparo.

## <a name="setting-up-repair-management"></a>Configuração de gerenciamento de reparos

Use os formulários de configuração a seguir para inserir informações que serão usadas para especificar os sintomas, o diagnóstico e a resolução do reparo.

- **Gerenciamento de serviços** \> **Configuração** \> **Reparo** \> **Condições**.
- **Gerenciamento de serviços** \> **Configuração** \> **Reparo** \> **Áreas de sintoma**.
-  **Gerenciamento de serviços** \> **Configuração** \> **Reparo** \> **Áreas de diagnóstico**.
- **Gerenciamento de serviços** \> **Configuração** \> **Reparo** \> **Resoluções**.
- **Gerenciamento de serviços** \> **Configuração** \> **Reparo** \> **Estágios de reparo**.

## <a name="symptoms-and-conditions"></a>Sintomas e condições

Os sintomas são como o cliente caracteriza o problema. Os sintomas incluem as observações do cliente que indicam a necessidade de reparo.

Você pode configurar áreas de sintoma, códigos de sintoma e condições. A área de sintomas aborda a área do problema, e o código do sintoma aborda o sintoma do problema. A condição descreve a situação ou o ambiente presente quando o problema ocorre.

**Exemplo**

Um computador é trazido para reparo porque o disco rígido falha após um período estendido de uso. A falha do disco rígido causa de um erro de tela azul. O técnico que recebe o computador insere os seguintes sintomas e condições:

1.  A área de sintoma é o disco rígido

2.  O código do sintoma é o erro de tela azul

3.  A condição é que o disco rígido falha depois de uso estendido

## <a name="diagnosis-and-resolutions"></a>Diagnóstico e resoluções

Os campos de diagnóstico e resoluções são instruções da perspectiva do reparo. Essas são as etapas que o técnico seguiu para investigar o problema.

A área de diagnóstico indica a operação que deve ocorrer para solucionar o problema. O código de diagnóstico é como o problema foi tratado, e a resolução poderia ser que o item foi reparado, substituído ou que a ordem foi cancelada pelo cliente. Por exemplo, se o computador for reparado, a área de diagnóstico poderia ser "peça defeituosa", o código de diagnóstico poderia ser "nova placa de vídeo instalada", e a resolução, "substituído".

## <a name="repair-stages"></a>Estágios de reparo

Os estágios de reparo indicam o progresso do processo de reparo. O estágio de reparo possui um parâmetro de aprovação **Concluído** que indica que a linha de reparo foi concluída e que a data e a hora de término foram registradas.

## <a name="applying-repair-management"></a>Aplicando o gerenciamento de reparo

Para aplicar o gerenciamento de reparo a um item, este deve ser configurado com uma relação de objeto de serviço em uma ordem de serviço. Depois, você poderá criar na ordem de serviço uma linha de reparo com informações sobre o problema atual. Nessa linha, você definirá o objeto de serviço que está sendo reparado, bem como informações sobre sintomas, diagnóstico e execução. Você também pode criar uma nota para a linha de reparo.

É possível criar linhas de reparo para cada etapa do processo de reparo.

## <a name="create-a-repair-line-on-a-service-order"></a>Criar uma linha de reparo em uma ordem de serviço

1.  Acesse **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.

2.  Selecione a ordem de serviço com o objeto de serviço que precisa de reparo.

3.  Selecione **Reparo** \> **Linhas de reparo** para abrir o formulário **Linhas de reparo**.

4.  Selecione **Novo** para criar uma nova linha.

5.  Selecione uma objeto de serviço. Você pode selecionar qualquer objeto de serviço que tenha sido configurado com uma relação de objeto na ordem de serviço.

6.  Selecione um dos valores de sintomas, diagnóstico e execução predefinidos relevantes na linha de reparo e, em seguida, selecione a guia **Observação** para criar uma observação na linha de reparo, se necessário.

7.  Selecione **Salvar** para salvar a nova linha de reparo. O campo **Data e hora de criação** na guia **Geral** do formulário **Linhas de reparo** será atualizado com a hora em que foi salvo.

## <a name="tracking-progress-and-resolving-a-repair-issue"></a>Rastrear o progresso e resolver um problema de reparo

Você pode definir os estágios de uma linha de reparo para rastrear o progresso do reparo.

Quando um problema de reparo é resolvido, você pode fechar a linha de reparo. Defina a fase de reparo para um estágio com a propriedade **Concluído** habilitada. A data e a hora atuais são registradas como a hora de término na linha.

## <a name="close-a-repair-line-for-a-resolved-issue"></a>Fechar uma linha de reparo para um problema resolvido

1.  Abra o formulário **Linhas de reparo**. Siga o procedimento descrito anteriormente neste tópico para criar uma linha de reparo.

2.  Selecione a linha de reparo com o problema que você deseja fechar.

3.  No campo **Fase de reparo**, selecione um estágio com a propriedade **Concluído** habilitada.

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]