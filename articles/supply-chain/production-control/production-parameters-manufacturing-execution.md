---
title: "Parâmetros de produção em Execução de fabricação"
description: "Este tópico fornece informações sobre a configuração dos parâmetros de produção na execução da fabricação."
author: johanhoffmann
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JmgProdParameters
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: b24bb43e740835da25d44cb971e8f528db9cfacb
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="production-parameters-in-manufacturing-execution"></a>Parâmetros de produção em Execução de fabricação

[!include[banner](../includes/banner.md)]

Este tópico fornece informações sobre a configuração dos parâmetros de produção na execução da fabricação.

O módulo **Execução de fabricação** é destinada principalmente para empresas de manufatura. Ele pode ser usado para registrar a hora e o consumo de itens em trabalhos de produção ou de projetos. Antes de começar a usar a execução da fabricação para inscrições de trabalho, você deve configurar vários parâmetros de produção que definem como e quando os registros são postados durante o processo de produção. As configurações dos parâmetros de produção afetam o gerenciamento de estoque, gerenciamento de produção e cálculo de custos.

Antes de os trabalhadores começar a fazer inscrições em trabalhos de produção, você deve considerar cuidadosamente todas as configurações na página **Parâmetros de produção**. Clique em **Controle de produção** &gt; **Configuração** &gt; **Execução de fabricação** &gt; **Padrões de ordem de produção**. Se sua empresa usa a funcionalidade multisite, você pode querer configurar diferentes parâmetros de produção para cada site. Os parâmetros para integração com o módulo **Produção** são configurados nas seguintes guias na página **Parâmetros de produção**:

- **Geral** – Configurações de parâmetro geral para trabalhos de produção na execução de fabricação.
- **Início** – Parâmetros usados quando as operações de produção são iniciadas.
- **Operações** – parâmetros aplicados às operações e aos comentários de produção em operações durante o processo de produção.
- **Relatar como concluído** – Parâmetros usados quando os itens são relatados como concluídos na última operação da ordem de produção.
- **Validação de quantidade** – Parâmetros que são utilizados na validação de quantidades inicial e de comentário em ordens de produção.

## <a name="types-of-production-jobs"></a>Tipos de trabalhos de produção
Na guia **Operações**, selecione quais tipos de trabalhos de produção necessitam de registro na página **Registro de trabalho**.

Em geral, os funcionários fazem registro dos trabalhos de configuração e dos trabalhos de processo. No entanto, se o planejamento do trabalho for aplicado, você pode selecionar outros tipos de trabalho em que os funcionários devem fazer registros quando as ordens de produção forem processadas. Por exemplo, você pode exigir inscrições em trabalhos de transporte.

> [!IMPORTANT]
> Certifique-se de selecionar todos os tipos de trabalho relevantes. Caso contrário, os trabalhos podem não estar disponíveis para registro na página **Registro de trabalho**. As seleções devem corresponder às seleções na coluna **Gerenciamento de trabalho** na guia **Configuração** da página **Grupos de roteiros** (**Controle de produção** &gt; **Configuração** &gt; **Roteiros** &gt; **Grupos de roteiros**).

Se **Gerenciamento de trabalho** estiver selecionado no grupo de roteiros, este tipo de trabalho é relatado como concluído na ordem de produção quando o trabalho é relatado como concluído na execução da fabricação Quando todos os tipos de trabalhos para os quais **Gerenciamento de trabalhos** estiver selecionado tiverem sido relatados como concluídos em uma operação, Execução de fabricação também relatará a operação como concluída.

> [!NOTE]
> Alguns tipos de trabalho podem ser informados manualmente através de revistas de produção. Nesse caso, selecione **Gerenciamento de trabalhos** como o tipo de trabalho, mas não selecione o tipo de trabalho para registro na guia **Operações** da página **Parâmetros de produção** em Execução de fabricação.

## <a name="bom-consumption-and-picking-list-journals"></a>Diários de consumo de BOM e da lista de separação
É importante uma configuração consistente para o consumo de lista de materiais (BOM), porque ajuda a garantir que o gerenciamento de estoque seja eficiente. Por exemplo, se os parâmetros de consumo da BOM não estiverem configurados corretamente na execução da fabricação, os materiais podem ser deduzidos do inventário duas vezes ou não.

Na página **Parâmetros de produção**, o consumo automático de BOM é configurado em três estágios:

- No início de uma produção. Configure este estágio na guia **Início**.
- Durante o processo de produção quando uma operação é concluída. Configure este estágio na guia **Operações**.
- Quando uma ordem de produção é relatada como concluída. Configure este estágio na guia **Relatar como concluído**.

Para cada estágio, o campo **Consumo automático de BOM** permite selecionar um dos três métodos para separar itens de uma ordem de produção:

- **Princípio de liberação** – Esta opção é usada em combinação com uma opção definida para a lista de materiais no módulo **Produção**. Clique em **Controle de produção** &gt; **Comum** &gt; **Ordens de produção** &gt; **Todas as ordens de produção**. Na página **Todas as ordens de produção**, selecione uma ordem de produção na lista e, em seguida, no painel de ações, clique em **BOM**. Na página **BOM**, na guia **Configuração**, no campo **Princípio de liberação**, selecione uma destas opções:

    - **Iniciar**
    - **Concluir**
    - **Manual**
    - Em branco - nenhuma opção está selecionada.
    - **Disponível no local**

    Em Execução de fabricação, se **Princípio de liberação** estiver selecionado no campo **Consumo automático de BOM** na guia **Início**, todos os materiais que estão definidos como **Início** na BOM são deduzidos do estoque quando a operação for iniciada. A opção **Disponível no local** é usada para os produtos que são habilitados para processos avançados de depósito. Se você selecionar este princípio de liberação, o material é liberado quando o trabalho do depósito para a escolha da matéria-prima estiver concluído. O material também é liberado quando uma linha de lista de materiais que usa este princípio de liberação é liberada para depósito e o material está disponível no local de entrada de produção.
    
    > [!NOTE]
    > Se o campo **Princípio de liberação** for definido na guia **Iniciar** na execução de Fabricação, selecione o mesmo princípio na guia **Operações** ou na guia **Relatório de conclusão**. Este requisito ajuda a garantir que os materiais são deduzidos do estoque nas BOMs que usam **Finalizar** como princípio de liberação na ordem de produção. Se o mesmo princípio de liberação não for selecionado na guia **Operações** ou **Relatar como concluído**, os materiais podem ser deduzidos do estoque duas vezes.
 
- **Sempre** – Se você selecionar esta opção para uma fase, os materiais são deduzidos do estoque nessa fase. Por exemplo, os materiais da produção serão deduzidos quando a ordem de produção for iniciada. Esta configuração exige que **Nunca** seja selecionado nas guias **Operações** e **Relatar como concluído**. Este requisito ajuda a evitar que itens sejam deduzidos do estoque duas vezes.
- **Nunca** – Se você selecionar esta opção para uma fase, nenhum consumo de BOM ocorrerá neste estágio. Por exemplo, se você selecionar **Nunca** em todas as três guias (**Iniciar**, **Operações**, e **Relatar como concluído**), os materiais devem ser manualmente deduzidos do estoque.

> [!IMPORTANT]
> Considere cuidadosamente a sua configuração dos parâmetros de produção e certifique-se de que os parâmetros selecionados nas várias abas da página **Parâmetros de produção** não se contradigam.

Os exemplos a seguir ilustram as configurações de parâmetro que suportam princípios diferentes de consumo de BOM. Os parâmetros são definidos na **Parâmetros de produção** na execução de fabricação.

### <a name="example-1-backflushing-on-operations"></a>Exemplo 1: Baixa de estoque nas operações

Use as configurações a seguir se for necessário gerar os diários de lista de separação e o consumo de item de BOM quando os itens forem relatados como concluídos em uma operação.

| Guia                | Campo                          | Configuração                             |
|--------------------|--------------------------------|-------------------------------------|
| Início              | Atualizar inicialização online           | **Status** ou **Status + quantidade** |
| Início              | Consumo automático de BOM      | **Nunca**                           |
| Operations         | Consumo automático de BOM      | **Sempre**                          |
| Relatório de conclusão | Consumo automático de BOM      | **Nunca**                           |
| Relatório de conclusão | Atualizar relatório concluído online | **Status + quantidade**               |

### <a name="example-2-backflushing-on-production"></a>Exemplo 2: baixa de estoque na produção

Use as configurações a seguir se for necessário gerar os diários de lista de separação e o consumo de item de BOM quando os itens forem relatados como concluídos na ordem de produção.

| Guia                | Campo                          | Configuração                             |
|--------------------|--------------------------------|-------------------------------------|
| Início              | Atualizar inicialização online           | **Status** ou **Status + quantidade** |
| Início              | Consumo automático de BOM      | **Nunca**                           |
| Operations         | Consumo automático de BOM      | **Nunca**                           |
| Relatório de conclusão | Consumo automático de BOM      | **Sempre**                          |
| Relatório de conclusão | Atualizar relatório concluído online | **Status + quantidade**               |

### <a name="example-3-flushing-principle"></a>Exemplo 3: Princípio de liberação

Use as seguintes configurações se os diários da lista de seleção e o consumo do item da lista técnica precisarem ser gerados de acordo com o princípio de descarga que está configurado para os itens da lista técnica.

| Guia                | Campo                          | Configuração                |
|--------------------|--------------------------------|------------------------|
| Início              | Atualizar inicialização online           | **Status + quantidade**  |
| Início              | Consumo automático de BOM      | **Princípio de liberação** |
| Operations         | Consumo automático de BOM      | **Princípio de liberação** |
| Relatório de conclusão | Consumo automático de BOM      | **Nunca**              |
| Relatório de conclusão | Atualizar relatório concluído online | **Status + quantidade**  |

### <a name="example-4-deduction-of-materials-during-startup-of-a-production-order"></a>Exemplo 4 - Dedução de materiais durante o início de uma ordem de produção

Use as configurações a seguir se for necessário gerar os diários de lista de separação e o consumo de item de BOM quando uma produção for iniciada.

| Guia                | Campo                          | Configuração                             |
|--------------------|--------------------------------|-------------------------------------|
| Início              | Atualizar inicialização online           | **Status + quantidade**               |
| Início              | Consumo automático de BOM      | **Sempre**                          |
| Operations         | Consumo automático de BOM      | **Nunca**                           |
| Relatório de conclusão | Consumo automático de BOM      | **Nunca**                           |
| Relatório de conclusão | Atualizar relatório concluído online | **Status** ou **Status + quantidade** |

Com base nas seleções descritas anteriormente nesta seção, os diários de lista de separação são lançados em diversas fases do processo da ordem de produção:

- Quando uma operação é iniciada
- Quando os comentários de quantidade são relatados em uma operação
- Quando os itens são relatados como concluídos na ordem de produção

### <a name="example-5-manual-bom-consumption"></a>Exemplo 5: Consumo manual de BOM

Você pode usar as seguintes configurações se os materiais sempre devem ser deduzidos manualmente do inventário. Neste caso, os diários de lista de separação não são lançados.

| Guia                | Campo                          | Configuração    |
|--------------------|--------------------------------|------------|
| Início              | Atualizar inicialização online           | **Status** |
| Início              | Consumo automático de BOM      | **Nunca**  |
| Operations         | Consumo automático de BOM      | **Nunca**  |
| Relatório de conclusão | Consumo automático de BOM      | **Nunca**  |
| Relatório de conclusão | Atualizar relatório concluído online | **Status** |

