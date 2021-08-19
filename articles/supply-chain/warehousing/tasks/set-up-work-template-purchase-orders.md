---
title: Configurar um modelo de trabalho para ordens de compra
description: Este tópico descreve como configurar um modelo de trabalho simples que será usado no armazenamento dos itens recebidos.
author: ShylaThompson
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkTemplateTable, SysQueryForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4fb9038a680bd804f12ea7debe1eb631f6631da1da9667e4c335ed8673a179f1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718819"
---
# <a name="set-up-a-work-template-for-purchase-orders"></a>Configurar um modelo de trabalho para ordens de compra

[!include [banner](../../includes/banner.md)]

Este tópico descreve como configurar um modelo de trabalho simples que será usado no armazenamento dos itens recebidos. Modelos de trabalho determinam o conjunto de instruções apresentadas ao trabalhador do depósito em um dispositivo móvel ao mover itens da área de recebimento. Você pode usar esse procedimento com os dados mencionados na empresa de dados de demonstração USMF. Antes de iniciar este guia, crie uma ID de grupo de trabalho. Neste exemplo, uma ID de grupo de trabalho chamada na Entrada é usada. Esse procedimento é destinado ao gerente do depósito.

1. No painel de navegação, Acesse **Módulos > Gerenciamento de depósito > Configuração > Trabalho > Modelos de trabalho**.
2. No campo **Tipo de ordem de trabalho**, selecione **Ordens de compra**.

## <a name="create-a-work-template-header"></a>Criar um cabeçalho do modelo de trabalho
1. Selecione **Novo**.
2. No campo **Número de sequência**, insira um número. Esta é a sequência em que os modelos de trabalho são avaliados. Você pode modificar a sequência, se necessário.  
3. No campo **Modelo de trabalho**, digite um valor. Este é o identificador exclusivo desse modelo.  
4. No campo **Descrição do modelo do trabalho**, digite um valor.
    - A opção **Válido** não será marcada até que você tenha concluído todas as informações exigidas pelo modelo e, depois, tenha selecionado **Salvar**.  
    - Uma ordem de trabalho do tipo **Ordem de compra** não pode ser processada automaticamente. Por isso, deixa a opção **Processar automaticamente** definida como **Não**.  
5. No campo **ID de grupo de trabalho**, digite um valor. As IDs de grupo de trabalho permitem organizar o trabalho em grupos. O valor definido aqui será o valor padrão de qualquer trabalho criado usando esse modelo.  
6. No campo **Prioridade de trabalho**, insira `1`. Isso indica a importância do trabalho, e o valor que você definiu aqui será o padrão de qualquer trabalho criado com esse modelo.  
7. Selecione **Salvar**. Você deve salvar o cabeçalho do modelo de trabalho antes que o botão **Editar consulta** fique disponível.  

## <a name="set-up-the-query-for-the-work-template"></a>Configurar a consulta do modelo de trabalho
1. Selecione **Editar consulta**. Definiremos uma limitação segundo a qual o modelo só pode ser usado em um depósito específico.  
2. Selecione **Adicionar**.
3. No campo **Campo** da nova coluna, digite `warehouse`.
4. No campo **Critérios**, digite um valor.
5. Selecione **OK**.
6. Selecione **Sim**.

## <a name="set-work-template-details"></a>Definir detalhes do modelo de trabalho
1. Selecione **Novo**.
2. No campo **Tipo de trabalho**, selecione **Separar**.
3. No campo **ID de classe de trabalho**, digite `purchase`. A classe de trabalho definida aqui será a padrão em todas as linhas de trabalho de tipo Separar criadas com esse modelo. A classe de trabalho não pode ser substituída nas linhas da ordem de trabalho. Classes de trabalho são usadas para direcionar e/ou limitar os tipos de linhas da ordem de trabalho que um funcionário do depósito pode processar em um dispositivo móvel.  
4. Selecione **Novo**.
5. No campo **Tipo de trabalho**, selecione **Colocar**.
6. No campo **ID da classe de trabalho**, digite um valor. As instruções de separação e armazenamento formam um conjunto. Cada conjunto separar/armazenar deve ter a mesma classe de trabalho. Use a mesma classe de trabalho que você forneceu para a instrução de separação.  
7. Selecione **Salvar**. Note que agora a caixa de seleção **Válido** está marcada.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]