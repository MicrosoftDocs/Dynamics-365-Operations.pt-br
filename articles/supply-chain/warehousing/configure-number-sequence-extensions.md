---
title: Configurar sequências numéricas para fluxos de depósito
description: Este tópico oferece uma visão geral da funcionalidade que fornece extensões de sequência numérica para IDs de placa de licença, IDs de etiqueta de onda, IDs de contêiner e IDs de conhecimento de embarque.
author: GarmMSFT
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSNumberSequenceExt
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: e6faab834b4c1c514bcc23a59d74e2bd0e069754
ms.sourcegitcommit: a26e4963d40796da21ce6581cfb2f4d9db4f6776
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "4422625"
---
# <a name="configure-number-sequences-for-warehouse-flows"></a>Configurar sequências numéricas para fluxos de depósito

[!include [banner](../includes/banner.md)]

O recurso *Extensões de sequência numérica* adiciona uma nova página de configuração para configurar sequências numéricas. Ele permite a configuração flexível de IDs regulamentadas pelo GS1, incluindo prefixos GS1 e dígitos de verificação (módulo 10), e impõe um limite de tamanho em sequências numéricas existentes.

Os segmentos da sequência numérica padrão não são adequados para a implementação do GS1, porque nenhum dígito de verificação é calculado e o prefixo GS1 da empresa deve ser atualizado manualmente.

Este recurso adiciona as seguintes funcionalidades:

- As IDs de conhecimento de embarque (BOL) podem ser geradas antecipadamente.
- Uma sequência numérica exclusiva pode ser gerada para números de SSCC (código série do contêiner de remessa).
- As sequências numéricas em conformidade com o GS1 podem ser criadas para números de BOL e SSCC. O recurso adiciona suporte imediato para IDs de placa de licença, IDs de contêiner, IDs de etiqueta de onda e IDs de BOL.
- A configuração dos números de IDs de placa de licença é flexível. Por exemplo, você pode incluir ou excluir identificadores do aplicativo (IA), como zeros à esquerda (00).

Essa funcionalidade torna mais eficiente o suporte à etiquetagem de caixas e o ajuste de novos números gerados pelo sistema.

## <a name="turn-on-the-number-sequence-extensions-feature"></a>Ativar o recurso Extensões de sequência numérica

Para que você possa usar o recurso, ele deve estar ativado no sistema. Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário. Nesse caso, o recurso é listado da seguinte maneira:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Extensões de sequência numérica*

## <a name="set-up-the-feature"></a>Configurar o recurso

Para configurar extensões de sequência numérica no sistema, siga estas etapas.

1. Vá para **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.
1. Na guia **Geral**, no campo **Prefixo GS1 da empresa**, insira o prefixo GS1 da sua empresa. Esse valor afetará todas as sequências numéricas nas quais o prefixo GS1 está incluído como um segmento.
1. Se você deseja gerar números de BOL para etiquetas de onda, na guia **Relatórios**, marque a caixa de seleção **Gerar um número de BOL durante a impressão de etiquetas de onda**.

    > [!NOTE]
    > Essa caixa de seleção só estará disponível se a funcionalidade para [impressão de etiquetas de onda](configure-wave-label-printing.md) estiver ativada.

1. Vá para **Gerenciamento de depósito** \> **Configuração** \> **Extensões de sequência numérica**
1. No Painel de Ação, selecione **Criar configuração padrão**. Uma sequência numérica de BOL em conformidade com o GS1 e três tipos de sequências numéricas de SSCC são criadas. Todas essas sequências numéricas levam em consideração o tamanho do prefixo GS1 da sua empresa.

    Para obter mais informações sobre como personalizar essas sequências numéricas padrão e/ou adicionar novas sequências, consulte a próxima seção. Você também pode remover qualquer uma dessas sequências se não precisar delas.

1. Volte para **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.
1. Na guia **Sequências numéricas**, selecione uma extensão de sequência numérica relevante para gerar números para as IDs de placa de licença, IDs de etiqueta de onda, IDs de contêiner (neste caso, selecione a sequência adequada do **número de SSCC-18**) e/ou IDs de BOL (neste caso, selecione a sequência de **BOL**). Por padrão, as extensões de sequência numérica têm suporte apenas nesses quatro tipos de IDs.

Na próxima vez que um novo número for gerado para uma dessas sequências numéricas, a nova lógica será usada.

> [!NOTE]
> Se você não selecionar uma extensão de sequência numérica para as IDs de placa de licença, serão usadas as regras atuais para geração de IDs de placa de licença. Caso contrário, a sequência numérica selecionada será usada. As outras IDs usarão uma sequência numérica simples até você aplicar uma extensão de sequência numérica para elas.

## <a name="create-and-edit-number-sequences"></a>Criar e editar sequências numéricas

Na seção anterior, você gerou um conjunto padrão de sequências numéricas. Esta seção explica como cada sequência numérica é definida. Ela também explica como criar sequências personalizadas e como editar as sequências padrão ou personalizadas.

Para criar e editar sequências numéricas, siga estas etapas.

1. Vá para **Gerenciamento de depósito** \> **Configuração** \> **Extensões de sequência numérica**.
1. No Painel de Ações, selecione **Novo**.
1. No campo **Extensão de sequência numérica**, insira um nome para a nova sequência. No campo **Descrição**, insira uma descrição.
1. Na FastTab **Segmentos**, use os botões na barra de ferramentas para montar o formato de numeração, adicionando, excluindo e organizando segmentos. No campo **Segmento** de cada linha, atribua um tipo de segmento para definir a finalidade e o conteúdo desse segmento. A tabela a seguir descreve os tipos de segmentos disponíveis.

    | Tipo de segmento | descrição |
    |---|---|
    | Constante | Este tipo de segmento adiciona o mesmo texto constante para cada número gerado na sequência. No campo **Valor**, insira o texto obrigatório. O campo **Tamanho** é atualizado automaticamente para o tamanho do texto inserido no campo **Valor**. |
    | Sequência numérica | No campo **Valor**, insira um sinal numérico (*\#*) para cada caractere que deve ser mostrado na sequência gerada. A sequência numérica pode gerar números mais longos, mas somente os caracteres mais à direita serão exibidos. O campo **Tamanho** é atualizado automaticamente para o número de sinais numéricos inseridos no campo **Valor**.<p>Para atender aos requisitos do GS1 para números de SSCC-18, verifique se o tamanho desse segmento é 16 menos o tamanho do seu prefixo GS1.</p> |
    | Prefixo GS1 | Este tipo de segmento adiciona o valor definido no campo **Prefixo GS1 da empresa** na página **Parâmetros de gerenciamento de depósito**. O campo **Valor** mostra o valor definido na página **Parâmetros de gerenciamento de depósito** e o campo **Tamanho** mostra o número de caracteres no valor. Os campos **Valor** e **Tamanho** são somente leitura. |
    | Identificador de aplicativo | No campo **Valor**, insira um identificador de aplicativo, conforme especificado pela política de GS1 relevante para esse tipo de sequência numérica. Por exemplo, insira *00* para SSCC ou *420* para BOL. O campo **Tamanho** é atualizado automaticamente para o tamanho do identificador inserido no campo **Valor**. |
    | Tipo de embalagem | Para os itens que podem ser claramente identificados, este tipo de segmento adiciona um valor de campo do grupo de sequências de unidade relevante (da página **Grupos de sequências de unidade**). (Esse comportamento corresponde à lógica existente para IDs de placa de licença.) Para as placas de licença que incluem várias unidades de manutenção de estoque (SKUs), este tipo de segmento adiciona *0* (zero) por padrão. Para este tipo de segmento, o campo **Valor** sempre é definido como *P* e o campo **Tamanho** sempre é definido como *1*.|
    | Dígito de Verificação | Este tipo de segmento adiciona um dígito de verificação, que é um cálculo de módulo 10. (Esse comportamento corresponde à lógica existente para IDs de placa de licença.) Para este tipo de segmento, o campo **Valor** sempre é definido como um acento circunflexo (*^*) e o campo **Tamanho** sempre é definido como *1*. |

1. Para exibir um exemplo do formato numérico final, inspecione o campo **Formato** na parte inferior da FastTab **Segmentos**.
