---
title: Códigos de motivo de contagem de estoque
description: Este tópico descreve como configurar e aplicar códigos de motivo para tarefas de contagem.
author: Mirzaab
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCountingReasonCodePolicy
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 2f4332432ad73861cd9b6b6452685d3175ace56b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "320825"
---
# <a name="reason-codes-for-inventory-counting"></a>Códigos de motivo de contagem de estoque

[!include [banner](../includes/banner.md)]

Os códigos de motivo permitem analisar os resultados de um processo de contagem e quaisquer discrepâncias que ocorrem durante esse processo. Você pode especificar o motivo da contagem como um palete quebrado ou um ajuste de estoque que é baseado nas amostras de estoque.

## <a name="recommendation"></a>Recomendação

Antes de você configurar o sistema, recomendamos que você defina uma estratégia para trabalhar com códigos de motivo. Por exemplo, tente responder às seguintes questões:

- Os códigos de motivos devem ser obrigatórios nos depósitos?
- Os códigos de motivo devem ser obrigatórios ou opcionais em alguns itens?
- Quantos códigos de motivo você precisa?
- Como os usuários do scanner de código de barras usam os códigos de motivo? Os códigos de motivo devem ser pré-selecionados, obrigatórios ou não editáveis?
- Os funcionários do depósito precisam de código de motivo diferente nos scanners móveis? Se a resposta for sim, você pode criar mais itens de menu e atribuí-los a pessoas diferentes.

## <a name="where-reason-codes-apply"></a>Onde os códigos de motivo se aplicam

Você pode criar várias políticas de código de motivo e cada uma pode ter duas políticas de código de montagem de contagem. As políticas de código de motivo de contagem podem ser usadas para o nível de item ou o nível de depósito.

## <a name="set-up-reason-code-policies"></a>Configurar políticas de código de motivo

1. Selecione **Gerenciamento de estoque** \> **Configuração** \> **Estoque** \> **Políticas de código de motivo de contagem** e crie uma nova política de código de motivo.
2. No campo **Tipo de código de motivo de contagem** , selecione **Obrigatório** ou **Opcional** para especificar se a seleção de um código de motivo deve ser uma ação opcional ou obrigatória em um destes diários de contagem:

    - Contagem cíclica do (dispositivo móvel)
    - Contagem pontual (dispositivo móvel)
    - Contagem do limite (dispositivo móvel)
    - Ajuste de Entrada (dispositivo móvel)
    - Ajuste de Saída (dispositivo móvel)
    - Diário de Contagem (cliente avançado)

Você também pode configurar códigos de motivo para depósitos individuais e para produtos. A configuração de código de motivo para produtos pode desconsiderar a configuração de depósitos.

## <a name="mandatory-reason-codes"></a>Códigos de motivo obrigatórios

Se o parâmetro **Obrigatório** estiver definido na configuração de códigos de motivo para depósitos ou itens, o diário de contagem não poderá ser concluído e fechado até que um código de motivo seja fornecido.

### <a name="set-up-reason-codes-for-warehouses"></a>Configurar códigos de motivo para depósitos

1. Selecione **Gerenciamento de Estoque** \> **Configuração** \> **Divisão de estoque** \> **Depósitos**.
2. Na guia **Depósito**, no campo **Política de código de motivo de contagem**, selecione uma das seguintes opções:

    - **Em branco** – O parâmetro configurado para o item é usado para determinar se os diários de contagem são obrigatórios para o produto.
    - **Obrigatório** – Um código de motivo é sempre necessário em diários de contagem do depósito.
    - **Opcional** – Um código de motivo não é necessário em diários de contagem do depósito.

### <a name="set-up-reason-codes-for-products"></a>Configurar códigos de motivo para produtos

1. Selecione **Gerenciamento de informações sobre produto** \> **Produtos** \> **Produtos liberados**.
2. Na guia **Produto**, selecione **Política de código de motivo de contagem** e, em seguida, selecione uma das seguintes opções:

    - **Em branco** – O parâmetro configurado para o depósito é usado para determinar se os diários de contagem são obrigatórios para o produto.
    - **Obrigatório** – Um código de motivo é sempre necessário em diários de contagem do produto. Essa configuração substitui qualquer configuração de código de motivo em nível de depósito.
    - **Opcional** – Um código de motivo não é necessário em diários de contagem do produto. Essa configuração substitui qualquer configuração de código de motivo em nível de depósito.

### <a name="use-reason-codes-in-counting-journals"></a>Usar códigos de motivo em diários de contagem

Em um diário de contagem, você pode adicionar códigos de motivo a contagem dos seguintes tipos:

- Contagem Cíclica
- Contagem Pontual
- Contagem do Limite
- Ajuste de Entrada
- Ajuste de Saída

Os códigos de motivo são adicionados às linhas do diário nos diários de contagem do tipo **Diário de contagem** .

1. Selecione **Gerenciamento de estoque** \> **Entradas de diário** \> **Contagem de itens** \> **Contagem**.
2. Nos detalhes da linha do diário de contagem, no campo **Código de motivo de contagem**, selecione uma opção.

### <a name="view-the-counting-history-as-its-recorded-by-reason-codes"></a>Exiba o histórico de contagem como é registrado pelos códigos de motivo

- Selecione **Gerenciamento de estoque** \> **Consultas e relatórios** \> **Histórico de contagem** e no campo **Código de motivo de contagem**, exiba o histórico de contagem que foi registrado através de um código de motivo.

### <a name="use-a-reason-code-for-a-quantity-adjustment"></a>Use um código de motivo para um ajuste de quantidade

1. Na página **Estoque disponível**, selecione **Ajustar quantidade**. Você pode abrir a página **Estoque disponível** de várias formas. Por exemplo, selecione **Gerenciamento de estoque** \> **Consultas e relatórios** \> **Estoque disponível**.
2. Selecione **Ajustar quantidade** e no campo **Código de motivo de contagem**, selecione um código de motivo.

### <a name="configure-reason-codes-for-mobile-device-menu-items"></a>Configurar códigos de motivo para itens de menu de dispositivo móvel

Você pode configurar códigos de motivo para qualquer tipo de contagem em um item de menu de dispositivo móvel. A configuração de itens de menu de dispositivo móvel inclui as seguintes informações:

- Se o código será for mostrado ao trabalhador do dispositivo móvel durante a contagem.
- O código de motivo padrão que é mostrado em um item de menu do dispositivo móvel.
- Se o usuário pode editar o código de motivo.

### <a name="set-up-reason-codes-on-a-mobile-device"></a>Configurar códigos de motivo em um dispositivo móvel

1. Selecione **Gerenciamento de depósito** \> **Configuração** \> **Dispositivo móvel** \> **Itens de menu do dispositivo móvel**.
2. Na guia **Contagem cíclica** , selecione **Contagem cíclica**.
3. No campo **Código de motivo de contagem padrão** , defina o código de motivo padrão que deve ser registrado quando contagem é feita usando o item de menu de dispositivo móvel.
4. No campo **Exibir código de motivo de contagem** , selecione **Linha** para mostrar o código de motivo após cada variação ser registrada. Como alternativa, selecione **Ocultar** se o código de motivo não tiver que ser mostrado.
5. Defina a opção **Editar código de motivo de contagem** como **Sim** ou **Não**. Se você definir esta opção como **Sim**, o trabalhador poderá editar o código de motivo quando ele for mostrado no dispositivo móvel durante a contagem.

> [!NOTE]
> O botão **Contagem cíclica** pode ser habilitado em qualquer item de menu de dispositivo móvel onde a contagem pode ser feita. O exemplo inclui itens de menu para contagens pontuais, trabalho direcionado ao usuário e trabalho direcionado ao sistema.

## <a name="cycle-count-approvals"></a>Aprovações de contagem cíclica

Antes de uma contagem ser aprovada, o usuário pode alterar o código de motivo associado à contagem. Quando a contagem for aprovada, o código de motivo será inserido nas linhas de diário da contagem.

### <a name="modify-cycle-count-approvals"></a>Modificar aprovações de contagem cíclica

1. Selecione **Gerenciamento de depósito** \> **Contagem cíclica** \> **Trabalho de contagem cíclica com revisão pendente**.
2. Selecione **Contagem cíclica** e, em seguida, no campo **Código de motivo**, selecione um novo código de motivo.

### <a name="modify-the-mobile-device-menu-item-for-adjustment-in-and-adjustment-out"></a>Modificar o item de menu do dispositivo móvel para Ajuste de entrada e Ajuste de saída

1. Selecione **Gerenciamento de depósito** \> **Configuração** \> **Dispositivo móvel** \> **Itens de menu do dispositivo móvel** e depois **Ajuste de entrada e saída**.
2. Defina a opção **Usar trabalho existente** como **Não**.
3. No campo **Processo de criação de trabalho**, selecione **Ajuste de entrada**.

Os campos a seguir serão adicionados ao item de menu do dispositivo móvel quando **Ajuste de entrada** ou **Ajuste de saída** for selecionado durante o processo de criação de trabalho:

- Código de motivo de contagem padrão
- Exibir código de motivo de contagem
- Editar código de motivo de contagem
