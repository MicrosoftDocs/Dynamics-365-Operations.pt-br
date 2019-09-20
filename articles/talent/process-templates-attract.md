---
title: Criar um modelo de processo no Attract
description: Este tópico fornece informações sobre como criar um modelo de processo no Attract.
author: andreabichsel
manager: AnnBe
ms.date: 10/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: AX 8.1
ms.openlocfilehash: 55e0d128cdc12843763f81014edd1846b35ed220
ms.sourcegitcommit: 7c49475402632069685df714546770d30804af7f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2019
ms.locfileid: "1739785"
---
# <a name="create-a-process-template"></a>Criar um modelo de processo

[!include [banner](includes/banner.md)]

Um *modelo de processo de contratação* contém todas as atividades que devem ser incluídas como parte do processo de contratação para um trabalho. Este tópico descreve os elementos de um modelo de processo no Microsoft Dynamics 365 for Talent: Attract. Ele também explica como criar um modelo.

> [!NOTE]
> A criação de modelo é parte do suplemento de contratação abrangente no Attract.

## <a name="template-management"></a>Gerenciamento de modelos

Organizações podem decidir se membros da equipe ou apenas administradores podem criar modelos no Attract. Para configurar o gerenciamento do modelo, vá para **Centro admin** \> **Gerenciamento do modelo**. Para deixar membros de equipe criarem seus próprios modelos, ative o gerenciamento do modelo. Se você não ativa o gerenciamento do modelo, apenas os administradores podem criar modelos.

## <a name="default-template"></a>Modelo padrão

Apenas os administradores podem definir o modelo padrão. O modelo padrão é usado se um modelo não for selecionado quando um trabalho for criado. Para definir o modelo padrão, vá para **Centro admin** \> **Gerenciamento do modelo**. No cartão do modelo que deve ser o modelo padrão, selecione o botão de reticências (**...**), e depois selecione **Definir como padrão**.

## <a name="create-a-process-template"></a>Criar um modelo de processo

Os administradores, os recrutadores e os gerentes de contratação podem criar modelos de processo. Um modelo de processo consiste de *estágios* e *atividades*. Os estágios agrupam uma ou mais atividades. Por padrão, cada método de processo tem atividades de cliente potencial, de aplicativos e oferta. Os estágios que contêm essas atividades podem ser renomeados. Você pode adicionar mais estágios selecionando **+ Novo estágio**. Você pode levar as atividades a um estágio arrastando-as para o estágio apropriado ou com clique duplo nelas na lista de atividade.

> [!NOTE]
> Os nomes de estágio são visíveis candidatos na página **Status de solicitação**. Considere esses fatos quando escolher nomes de estágios.

Para saber mais sobre atividades, consulte [Atividades do processo de contratação no Attract](./activities-attract.md).

Siga estas etapas para criar um modelo de processo de contratação.

1. Vá para **Modelos**.
2. Selecione **Novo**.
3. No campo **Nome do modelo**, insira um nome para o modelo, e depois selecione **Criar**.
4. Na lista **Escolha o processo de aprovação**, selecione **Padrão** para exigir aprovação para um trabalho.
5. Selecione para habilitar ou desabilitar candidatos potenciais.
6. Opcional: Adicione ou remova estágios.

    - Para adicionar um estágio, selecione **+ Novo estágio**.
    - Para remover uma remessa, coloque o ponteiro sobre o estágio, e selecione o botão de lixo que aparece.

        > [!NOTE]
        > O candidato potencial, solicitação de emprego e os estágios de oferta não podem ser removidos, mas podem ser renomeados.

7. Opcional: Adicione ou remova atividades.

    - Para adicionar uma atividade, arraste-a da lista de atividades para a direita do estágio apropriado. Outra opção é clicar duas vezes na atividade e selecionar o estágio para adicioná-la.
    - Para remover uma atividade, expanda-a e depois selecione o botão de lixeira no cabeçalho da atividade.

8. Selecione **Salvar**.
