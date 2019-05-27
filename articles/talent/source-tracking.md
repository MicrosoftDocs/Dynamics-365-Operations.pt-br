---
title: Rastrear origens de perfis de candidatos e solicitações de emprego
description: Este tópico fornece informações sobre como rastrear a origem de perfis de candidatos e solicitações de emprego.
author: hachandr
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: ebc82ada31d2803800358cd9aecfe389ada8f0dc
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517364"
---
# <a name="track-sources-for-candidate-profiles-and-applications"></a>Rastrear origens de perfis de candidatos e solicitações de emprego 

[!include[banner](../includes/banner.md)]

> [!NOTE] 
> A funcionalidade observada neste tópico está disponível para usuários como parte de uma revisão de versão prévia. O conteúdo e as funcionalidades estão sujeitos a alteração. Para usar o recurso, peça ao administrador habilitá-lo usando as **Configurações do administrador** no Attract. Uma versão futura fornecerá relatórios de rastreamento da origem. Para obter mais informações, consulte [Acessar os recursos de visualização no Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/access-preview-feature).

Quando os candidatos se candidatam a um trabalho, o Attract automaticamente rastreia a origem dessas solicitações de emprego, fornecendo informações valiosas que ajudam a direcionar os esforços de recrutamento. Os recrutadores e gerentes de projeto também podem selecionar uma origem de solicitação de emprego ao adicionar manualmente um candidato a um grupo de trabalhos ou de talentos.

Você pode exibir a origem da solicitação de emprego nos detalhes da atividade de solicitação de emprego na guia **Atividade** e no histórico de solicitações em **Perfil**, nos grupos de talentos. Você pode encontrar a origem do perfil de um candidato nos detalhes do candidato na guia **Perfil** em grupos de talentos e de solicitações de emprego.

> [!NOTE] 
> Você pode encontrar modelos de processo no [complemento de Contratação abrangente](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/attract-comprehensive-hiring).

## <a name="pre-configured-sources"></a>Fontes pré-configuradas

A lista de origens padrão contém fontes comuns de solicitação de emprego. Alguns tipos de fonte, como **Quadro de trabalho** e **Rede Social**, possuem outros detalhes. Por exemplo, **Rede Social** inclui Facebook e Twitter. O tipo de fonte **Indicação** permite especificar um funcionário interno como referenciador. A lista de origens padrão inclui as seguintes fontes pré-configuradas:

-   Site de carreiras Attract

-   Agência

-   Feiras de profissões

-   Marketing da empresa

-   Conferências e feiras de negócios

-   Associações profissionais

-   Quadro de trabalho

    -   Indeed

    -   Seek

    -   CareerBuilder

    -   Google Jobs

    -   Xing

    -   Glassdoor

    -   Monster Jobs

-   Revistas e publicações

-   Redes sociais

    -   Facebook

    -   Twitter

-   Recrutamento em universidades

-   LinkedIn

-   Classificados

-   Referência

-   Adicionado pelo recrutador

-   Outro

## <a name="customize-the-source-list"></a>Personalizar a lista de origens 

Você pode estender a lista de origens para incluir outras fontes de solicitação de emprego. Para personalizar essa lista, siga as instruções em [Extensão dos conjuntos de opções no Attract](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/extensibility-attract#extending-option-sets-in-attract). Edite a entidade **TalentSource** para incluir outras origens. 

Para não gerar um impacto negativo na interface do usuário, não edite nem exclua os valores de enumeração **TalentCategory** (não nomes) para o seguinte:

- **Referência**
- **LinkedIn**
- **Outro**

Em vez disso, você pode estender a enumeração **TalentSource** para adicionar outros tipos de origem.
