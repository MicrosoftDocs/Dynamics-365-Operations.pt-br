---
title: Recomendações inteligentes no Attract
description: Este artigo explica como o aprendizado de máquina pode ser usado para fornecer recomendações para trabalhos e candidatos a trabalhos no Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 05/16/2019
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
ms.openlocfilehash: fa06821c98e42dcd8590a764db9beb4a5c33fca2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4460283"
---
# <a name="intelligent-recommendations-in-attract"></a>Recomendações inteligentes no Attract

[!include [banner](includes/banner.md)]

Machine learning pode ajudar a recrutar e contratar gerentes rapidamente a identificar os candidatos principais para uma posição. Também pode ajudar os clientes potenciais a encontrar a posição que melhor atenda seu perfil e juros. Conforme esses recursos são usados e comentários são fornecidos, recomendações são melhoradas.

> [!NOTE] 
> - Os recursos de recomendação inteligente estão disponíveis somente com o [complemento de Contratação abrangente](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).
> - A funcionalidade observada neste tópico está disponível para usuários como parte de uma revisão de versão prévia. O conteúdo e as funcionalidades estão sujeitos a alteração. Para usar o recurso, peça ao administrador habilitá-lo usando as **Centro de administração** no Attract. Defina **Recomendação de candidato**, **Recomendação de trabalho**, **Recomendação de colaborador potencial** como **Ativado**. Para obter mais informações, consulte [Acessar as versões prévias de recurso no Microsoft Dynamics 365 Talent](./access-preview-feature.md). 


## <a name="candidate-recommendations"></a>Recomendações de candidato

Como os lançamentos de trabalho podem atrair centenas de candidatos, pode ser difícil para recrutadores e gerentes de contratação encontrarem candidatos que possuem habilidades e experiência que melhor combinam com a posição. Ao analisar a correlação entre a descrição e os requisitos do trabalho, além de currículos dos candidatos e perfis, machine learning podem ser usados para produzir recomendações de candidato. As recomendações de candidatos podem ajudar recrutadores e gerentes de contratação a identificarem os principais talentos e movê-los para o estágio de entrevista mais rápido. Para alguns trabalhos, se houver mais de dez candidatos ou clientes potenciais com currículos ou perfis concluído, candidatos ou clientes potenciais que preenchem mais proximamente os requisitos de trabalho são exibidos na seção **Candidatos a considerar** na página **Trabalho**.

Para qualquer candidato recomendado, selecione **Exibir candidato** no cartão do candidato para examinar o perfil do candidato e para agir na solicitação. Você pode usar o botão de reticências (**...**) para abrir o perfil de um candidato em uma nova guia. Você também pode usar o botão de reticências para fornecer comentários sobre a recomendação. Assim, você ajuda a ajustar o mecanismo de recomendação e a melhorar recomendações futuras. Quaisquer recomendações que você não gostar são removidas da seção **Candidatos a considerar** ao atualizar a página **Trabalho**. Você pode usar o cartão de comentários para indicar porque não achou a recomendação útil.

## <a name="job-recommendations"></a>Recomendações de trabalho 

Quando um funcionário em potencial usa o site de carreiras para se candidatar a um trabalho, o Attract recomenda outras posições abertas na organização. Essas recomendações são baseadas nas nas solicitações de emprego anteriores, no perfil e no currículo do candidato. Portanto, recomendações de trabalho ajudam os candidatos a identificarem rapidamente os trabalhos que são melhores para eles. As recomendações de trabalho são fornecidas a candidatos se mais de dez trabalhos são postados no site de carreira. Os candidatos podem abrir os detalhes de um anúncio do cartão da recomendação. Também podem fornecer comentários sobre uma recomendação para ajudar a melhorar as recomendações futuras.

## <a name="prospect-recommendations"></a>Recomendação de candidato ao trabalho 

Quando uma nova posição torna-se disponível, avaliar todos os candidatos anteriores e todas a sua rede talentos pode levar algum tempo. Para que o Attract o ajude a fazer isso, você pode usar os algoritmos inteligentes de machine learning. Isso significa que Attract revisará todos os candidatos e fará sugestões daqueles que são uma boa correspondência assim que você criar os trabalhos. Para exibir essas recomendações, habilite o estágio **Colaborador potencial** para o trabalho. Podem levar até um minuto para que o Attract verifique o todo o banco de dados de candidatos para fazer recomendações.

As recomendações serão exibidas como cartões na guia **Colaboradores potenciais** de todos os trabalhos que tenha o estágio **Colaborador potencial** habilitado. Esses cartões listam as habilidades encontradas no perfil do colaborador potencial, bem como todas as informações de qualificação de educação. Se encontrar uma recomendação da qual goste, você poderá adicionar o candidato como um colaborador potencial para esse trabalho.

> [!NOTE]
> Se você começou a usar o Attract recentemente, será necessário esperar até que tenha 10 ou mais candidatos com perfis ou currículos completos para usar esse recurso.

Para evitar possíveis parcialidades nas recomendações, o Attract somente verifica os perfis dos candidatos para habilidades, qualificações e outras palavras-chave que correspondam à descrição do trabalho. Além disso, o Attract remove informações de identificação pessoal dos perfis dos candidatos antes da avaliação.


[!INCLUDE[footer-include](../includes/footer-banner.md)]