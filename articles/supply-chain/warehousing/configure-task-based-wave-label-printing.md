---
title: Agendar a impressão da etiqueta de ciclo durante o ciclo
description: Este tópico descreve como configurar e usar a funcionalidade para impressão de etiqueta de ciclo baseada em tarefas.
author: MSFTGarm
ms.date: 06/09/2021
ms.topic: article
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-obaranov
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 4883f8a548645436e17b933d87d4ee6330570d48
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/09/2021
ms.locfileid: "7777856"
---
# <a name="schedule-wave-label-printing-during-wave"></a>Agendar a impressão da etiqueta de ciclo durante o ciclo

[!include [banner](../../includes/banner.md)]

Use o recurso *Impressão de etiqueta de ciclo baseada em tarefas* como parte do seu processo de ciclo para ajudar a melhorar a eficiência e fazer com que o sistema crie etiquetas de ciclos e trabalhe em tarefas separadas.

O processo de configuração da impressão da etiqueta de ciclo é complexo e depende de configurações precisas e dados mestres. Não é incomum que a geração de registros de etiqueta de ciclo falhe e, quando isso acontece, todo o processamento de ciclo é revertido. O recurso *Impressão de etiqueta de ciclo baseada em tarefa* ajuda você a evitar ter que recriar linhas de trabalho toda vez que uma etiqueta de ciclo for impressa incorretamente.

Quando você usa o recurso *Impressão de etiqueta de ciclo baseada em tarefa*, o sistema cria primeiramente trabalho e linhas de trabalho. Em seguida, ele cria e imprime as etiquetas de ciclo. Por fim, se as etiquetas de ciclo forem criadas corretamente, o recurso libera o trabalho e o ciclo para separação.

## <a name="turn-on-the-task-based-wave-label-printing-feature-in-feature-management"></a>Ativar o recurso de Impressão de etiqueta de ciclo baseada em tarefa no gerenciamento de recursos

Para usar os recursos que são descritos neste tópico, eles devem ser ativados para o seu sistema. Use o espaço de trabalho [Gerenciamento de recurso](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para ativar os recursos na seguinte ordem:

1. *Impressão de etiqueta de ciclo* – Este recurso é necessário para habilitar o método de processo de ciclo para impressão de etiqueta de ciclo.
1. *Bloqueio de trabalho em toda a organização* - Este recurso é necessário para a configuração manual e automática da criação de trabalho agendado. (Desde a versão 10.0.21 do Supply Chain Management, este recurso é obrigatório, portanto, é ativado por padrão e não pode ser desativado novamente.)
1. *Impressão de etiqueta de ciclo baseada em tarefas* – Esse recurso é necessário para dividir a impressão da etiqueta de ciclo em um escopo de transação separado.

## <a name="manually-enable-the-new-wave-step-method"></a>Habilitar manualmente o novo método de etapa do ciclo

Primeiro, você deve criar o novo método de etapa de ciclo e habilitar para o processamento de tarefas assíncronas paralelas.

1. Acesse **Gerenciamento de depósito \> Configuração \> Ondas \> Métodos de processo de onda**.
1. No Painel de Ações, selecione **Regenerar método**. Observe que *waveLabelPrinting* é adicionado à lista de métodos de processo de ciclo que você pode usar em seus modelos de ciclo de envio.
1. Selecione o registro em que o campo **Nome do método** esteja definido como *acenarLabelPrinting* e, em seguida, no Painel de Ações, selecione **Configuração de tarefa**.
1. No Painel de Ação, selecione **Novo** para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Depósito** - Selecione o depósito que você usará para agendar o processamento de criação de trabalho. (Se você estiver usando dados de demonstração para fins de teste, você pode selecionar o depósito *24*.)
    - **Número máximo de tarefas em lotes** - Especifique um número máximo de tarefas em lotes. Na maioria dos casos, o valor deve ser de *8* a *16*. No entanto, recomendamos que você experimente e encontre a configuração ideal para seus cenários.
    - **Grupo de lotes de processamento em ciclos** - Selecione um grupo de lotes de processamento em ciclos dedicados para otimizar o processamento da fila de lotes.

Agora você pode atualizar um modelo de ciclo existente para que ele use o método de processamento *Impressão de etiqueta de ciclo*. Como alternativa, você pode criar um novo modelo de ciclo que o use.

1. Acesse **Gerenciamento de depósito \> Configuração \> Ciclos \> Modelos de ciclo**.
1. No Painel de Ações, selecione **Editar**.
1. No painel de lista, selecione o modelo de ciclo a ser atualizado. (Se você estiver usando dados de demonstração para fins de teste, você pode selecionar o *24 Padrão de envio*.)
1. Na FastTab **Métodos**, na coluna **Métodos restantes**, selecione a linha na qual o campo **Nome** está definido como *waveLabelPrinting*.
1. Selecione **adicionar** (botão de seta para a direita) para mover a linha selecionada para a coluna **Métodos selecionados**.
1. No campo **Código de etapas do ciclo**, digite o código de etapa de ciclo que será usado para conectar o modelo de ciclo com um modelo de etiqueta de ciclo.

## <a name="set-wave-task-processing-threshold-data"></a>Definir dados do limite de processamento de tarefa de ciclo

Na primeira vez que o processo de ciclo for executado por qualquer processamento baseado em tarefa, o sistema cria os dados limites do processamento de tarefa de ciclo padrão. Esses dados são usados para controlar se o processamento de ciclo será executado assincronamente para que ele possa processar e criar etiquetas de ciclo em paralelo.

Os dados padrão usam inicialmente um valor limite de *1* para o número mínimo de IDs de trabalho (`MinimumWorkThresholdForLabelPrinting`). Portanto, quando o sistema processa um ciclo que tem mais de um ID de trabalho, ele usará o processamento baseado em tarefas de etiquetas de ciclo em uma transação separada. Você pode inserir ou atualizar manualmente esses dados na tabela `WHSWaveTaskProcessingThresholdParameters` em seus ambientes de teste. Para alterar a configuração em um ambiente de produção, deverá contatar o Suporte da Microsoft para solicitar a atualização.

## <a name="changes-to-the-wave-processing-logic-when-task-based-wave-label-printing-is-used"></a>Alterações na lógica de processamento de ciclo quando a impressão do rótulo de ciclo baseado em tarefas é usada

Se o processamento da etiqueta de ciclo exceder o limite de processamento da tarefa de ciclo, o processamento baseado em tarefas será iniciado. No processamento de ciclo seguinte que se encaixar no modelo de ciclo, a impressão da etiqueta de ciclo será executada em uma transação *ttsbegin*/*ttscommit* autônoma imediatamente após a criação do trabalho. Se a liberação de trabalho (desbloqueio) for configurada no modelo de ciclo para ser executada automaticamente, ela ocorrerá somente após o processo de impressão da etiqueta de ciclo ser concluído com sucesso.

Se a geração de etiquetas de ciclo falhar (por exemplo, se a conversão da quantidade de trabalho na quantidade de etiqueta de ciclo falhar e lançar um erro), apenas a transação apropriada falhará. O trabalho que foi criado anteriormente permanece congelado. Para corrigir erros e imprimir as etiquetas de ciclo, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Ondas de saída \> Ondas de remessa \> Todas as ondas**.
1. Selecione o ciclo relevante na grade.
1. No Painel de Ações, na guia **Onda**, no grupo **Imprimir**, selecione **Etiquetas de onda**.
1. Siga as instruções na tela para enviar as etiquetas para impressão.
1. No Painel de Ações, na guia **Ciclo**, no grupo **Ciclo**, selecione **Liberar** para liberar manualmente o trabalho para o ciclo selecionado.

## <a name="additional-resources"></a>Recursos adicionais

- [Impressão de etiqueta do ciclo](configure-wave-label-printing.md)
- [Agendar criação de trabalho durante o ciclo](configure-wave-schedule-work-creation.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
