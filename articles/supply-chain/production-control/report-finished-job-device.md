---
title: Relatar como concluído no dispositivo de ficha de trabalho
description: Este tópico descreve como configurar o sistema para que os usuários de um dispositivo de ficha de trabalho possam relatar produtos concluídos de uma ordem de produção para o estoque.
author: johanhoffmann
manager: tfehr
ms.date: 05/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationSetupTouch
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: f5d34893ddc8adc3785ec50dbd72438cf8f68c5d
ms.sourcegitcommit: 52ba8d3e6af72df5dab6c04b9684a61454d353ad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/26/2020
ms.locfileid: "3403253"
---
# <a name="report-as-finished-from-the-job-card-device"></a>Relatar como concluído no dispositivo de ficha de trabalho

[!include [banner](../includes/banner.md)]

Os trabalhadores usam a página **Andamento do relatório** no dispositivo de ficha de trabalho para relatar quantidades que foram concluídas para um trabalho de produção.

## <a name="control-whether-quantities-that-are-reported-as-finished-are-added-to-inventory"></a>Controlar se as quantidades relatadas como concluídas são adicionadas ao estoque

Para controlar se e como as quantidades relatadas como concluídas na última operação devem ser adicionadas ao estoque, siga estas etapas.

1. Vá para **Controle de produto \> Configuração \> Execução de fabricação \> Padrões de ordem de produção**.
1. Na guia **Relatar como concluído**, defina o campo **Atualizar relatório de conclusão online** como um dos seguintes valores:

    - **Não** – nenhuma quantidade será adicionada ao estoque quando as quantidades forem relatadas na última operação. O status da ordem de produção nunca será alterado.
    - **Status + Quantidade** – o status da ordem de produção será alterado para *Relatado como concluído* e a quantidade será relatada como concluída para o estoque.
    - **Quantidade** – a quantidade será relatada como concluída para o estoque, mas o status da ordem de produção nunca será alterado.
    - **Status** - somente o status da ordem de produção será alterado. Nenhuma quantidade será adicionada ao estoque quando as quantidades forem relatadas na última operação.

> [!NOTE]
> As quantidades não serão rastreadas no estoque se as operações relatadas como concluídas não forem definidas como a última operação. No entanto, essas quantidades podem ser usadas para exibir o andamento. Eles também podem ser incluídos nas regras que controlam se os trabalhadores podem iniciar a próxima operação antes que um limite definido de quantidades relatadas na operação anterior seja alcançado. Você pode definir essas regras na guia **Validação de quantidade** da página **Padrões da ordem de produção**.

Para obter mais informações sobre como trabalhar com a página **Padrões de ordem de produção**, consulte [Parâmetros de produção na Execução de fabricação](production-parameters-manufacturing-execution.md).

## <a name="report-batch-controlled-items-as-finished"></a>Relatar itens controlados por lote como concluídos

O dispositivo de ficha de trabalho dá suporte a três cenários de relatório sobre itens de lote. Esses cenários se aplicam aos itens habilitados para processos de depósito avançados e a itens que não estão habilitados para processos avançados de depósito.

- **Números de lote atribuídos manualmente:** trabalhadores inserem um número de lote personalizado. Esse número de lote pode vir de uma fonte externa que não é conhecida pelo sistema.
- **Números de lote predefinidos:** trabalhadores selecionam um número de lote em uma lista de números de lote que o sistema gera automaticamente antes de a ordem de produção ser liberada para o dispositivo de ficha de trabalho.
- **Números de lote fixos:** os trabalhadores não inserem ou seleciona um número de lote. Em vez disso, o sistema atribui automaticamente um número de lote à ordem de produção antes de ser liberada.

Para habilitar cada cenário, siga estas etapas.

1. Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Selecione o produto a ser configurado.
1. Na Guia Rápida **Gerenciar estoque**, no campo **Grupo de números de lote**, selecione o grupo de números de rastreamento que está configurado para oferecer suporte ao seu cenário.

> [!NOTE]
> Por padrão, se nenhum grupo de números de lote for atribuído a um produto controlado por lote, o dispositivo de ficha de trabalho fornecerá a entrada manual para o número do lote durante o relatório de conclusão.

As subseções a seguir descrevem como configurar grupos de números de rastreamento para oferecer suporte a cada um dos três cenários de relatório sobre itens de lote.

### <a name="enable-batch-number-reporting-on-the-job-card-device"></a>Habilitar relatório de número de lote no dispositivo de ficha de trabalho

Para habilitar os dispositivos de fichas de trabalho para aceitar um número de lote durante o relatório de conclusão, você deverá usar o [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para ativar os seguintes recursos (nesta ordem):

1. Experiência de usuário aprimorada no diálogo Andamento do relatório do Dispositivo de Ficha de Trabalho
1. Habilitar para inserir números de lote e de série ao relatar como concluído no Dispositivo de Ficha de Trabalho (versão preliminar)

### <a name="set-up-a-tracking-number-group-that-lets-workers-manually-assign-a-batch-number"></a>Configurar um grupo de números de rastreamento que ajudam os trabalhadores a atribuir manualmente um número de lote

Para permitir números de lote atribuídos manualmente, siga estas etapas para configurar um grupo de números de rastreamento.

1. Vá para **Gerenciamento de estoque \> Configuração \> Dimensões \> Grupos de números de rastreamento**.
1. Crie ou selecione o grupo de números de rastreamento a ser configurado.
1. Na Guia Rápida **Geral**, defina a opção **Manual** como **Sim**.

    ![Página Grupos de números de rastreamento](media/tracking-number-group-manual.png "Página Grupos de números de rastreamento")

1. Defina outros valores conforme necessário e selecione o grupo de números de controle como o grupo de números de lote para produtos liberados para os quais você deseja usar este cenário.

Quando você usa esse cenário, o campo **Número de lote** que a página **Andamento do relatório** no dispositivo de ficha de trabalho fornece é uma caixa de texto na qual os trabalhadores podem inserir qualquer valor.

![Página Andamento de relatório com um campo para números de lote manuais](media/job-card-device-batch-manual.png "Página Andamento de relatório com um campo para números de lote manuais")

### <a name="set-up-a-tracking-number-group-that-provides-a-list-of-predefined-batch-numbers"></a>Configurar um grupo de números de rastreamento que forneça uma lista de números de lotes predefinidos

Para fornecer uma lista de números de lote predefinidos, siga estas etapas para configurar um grupo de números de rastreamento.

1. Vá para **Gerenciamento de estoque \> Configuração > Dimensões \> Grupos de números de rastreamento**.
1. Crie ou selecione o grupo de números de rastreamento a ser configurado.
1. Na Guia Rápida **Geral**, defina a opção **Somente para transações de estoque** como **Sim**.
1. Use o campo **Por qtd.** para dividir os números de lote por quantidade com base no valor inserido. Por exemplo, você tem uma ordem de produção de dez peças e o campo **Por qtd.** está definido como *2*. Nesse caso, cinco números de lote serão atribuídos à ordem de produção quando ela for criada.

    ![Página Grupos de números de rastreamento](media/tracking-number-group-predefined.png "A página Grupos de números de rastreamento")

1. Defina outros valores conforme necessário e selecione o grupo de números de controle como o grupo de números de lote para produtos liberados para os quais você deseja usar este cenário.

Quando você usa esse cenário, o campo **Número de lote** que a página **Andamento do relatório** no dispositivo de ficha de trabalho fornece é uma lista suspensa na qual os trabalhadores devem selecionar um valor predefinido.

![Página Andamento de relatório com uma lista de números de lote predefinidos](media/job-card-device-batch-predefined.png "Página Andamento de relatório com uma lista de números de lote predefinidos")

### <a name="set-up-a-tracking-number-group-that-automatically-assigns-batch-numbers"></a>Configurar um grupo de números de rastreamento que atribui automaticamente números de lote

Se os números de lote tiverem de ser atribuídos automaticamente, sem a entrada do trabalhador, siga estas etapas para configurar um grupo de números de rastreamento.

1. Vá para **Gerenciamento de estoque \> Configuração \> Dimensões \> Grupos de números de rastreamento**.
1. Crie ou selecione o grupo de números de rastreamento a ser configurado.
1. Na Guia Rápida **Geral**, defina a opção **Somente para transações de estoque** como **Não**.
1. Defina a opção **Manual** como **Não**.

    ![Página Grupos de números de rastreamento](media/tracking-number-group-fixed.png "Página Grupos de números de rastreamento")

1. Defina outros valores conforme necessário e selecione o grupo de números de controle como o grupo de números de lote para produtos liberados para os quais você deseja usar este cenário.

Quando você usa esse cenário, o campo **Número de lote** que a página **Andamento do relatório** no dispositivo de ficha de trabalho fornece mostra um valor, mas os trabalhadores não podem editá-lo.

![Página Andamento de relatório com um número de lote fixo](media/job-card-device-batch-fixed.png "Página Andamento de relatório com um número de lote fixo")

## <a name="report-as-finished-to-a-license-plate"></a>Relatar como concluído para uma placa de licença

Os processos de depósito avançados podem usar a dimensão de placa de licença para rastrear o estoque em locais de depósito que foram configurados para essa finalidade. Nesse caso, o número da placa de licença é necessário quando um trabalhador relata quantidades como concluídas.

### <a name="enable-license-plate-reporting-and-label-printing"></a>Habilitar relatórios e impressão de etiqueta da placa de licença

Para usar os recursos descritos nesta seção, você deverá usar o [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para ativar os seguintes recursos (nesta ordem):

1. Placa de licença para relatório de conclusão adicionada ao Dispositivo de ficha de trabalho
1. Habilitar a geração automática do número da placa de licença ao concluir o relatório de conclusão no dispositivo de ficha de trabalho
1. Imprimir etiqueta do Dispositivo de Ficha de Trabalho

### <a name="set-up-reporting-as-finished-to-a-license-plate"></a>Configurar o relatório de conclusão para uma placa de licença

Para controlar se os trabalhadores devem reutilizar uma placa de licença existente ou gerar uma nova chapa de licença ao relatar quantidades como concluídas, siga estas etapas.

1. Vá para **Controle de produção \> Configuração \> Execução de fabricação \> Configurar o cartão de trabalho para dispositivos**.
2. Defina as seguintes opções para cada dispositivo:

    - **Gerar placa de licença** - defina essa opção como **Sim** para gerar uma nova placa de licença para cada relatar como concluído. Defina-a como **Não** se uma chapa de licença existente for usada para cada relatar como concluído.
    - **Imprimir etiqueta** - defina esta opção como **Sim** se o trabalhador tiver de imprimir uma etiqueta da placa de licença para cada relatar como concluído. Configure-o como **Não** se nenhuma etiqueta for necessária. 

![Página Configurar ficha de trabalho para dispositivos](media/config-job-card-raf.png "Página Configurar ficha de trabalho para dispositivos")

> [!NOTE]
> Para configurar a etiqueta, vá para **Gerenciamento de depósito \> Configuração \> Roteiro de documento \> Roteiro de documento**. Para obter mais informações, consulte [Habilitar impressão de etiqueta de placa de licença](../warehousing/tasks/license-plate-label-printing.md).
