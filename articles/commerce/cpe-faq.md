---
title: Perguntas frequentes sobre o ambiente de avaliação do Dynamics 365 Commerce
description: Este tópico fornece respostas às perguntas frequentes sobre o ambiente de avaliação do Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a0c6f82432a4786f23f12122f3806c3b96a05c8f
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193585"
---
# <a name="dynamics-365-commerce-evaluation-environment-faq"></a>Perguntas frequentes sobre ambiente de avaliação do Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este tópico fornece respostas às perguntas frequentes sobre o ambiente de avaliação do Microsoft Dynamics 365 Commerce.

**É possível usar o ambiente de avaliação do Commerce como uma vitrine do e-Commerce para clientes que atualmente implementam o Retail?**

Não. O ambiente de avaliação do Commerce é somente para avaliação. Se você precisar de um ambiente para um cliente que implemente Varejo, contate a Microsoft.

**O ambiente de avaliação do Commerce pode ser usado para provisionar os recursos do e-Commerce sobre um aplicativo/ambiente existente que implementa o Retail?**

Não (normalmente). Os componentes de avaliação do Commerce estão disponíveis somente para ambientes que correspondam às configurações especificadas no guia de pré-requisitos e provisionamento. Além disso, os dados de demonstração base necessários não estarão disponíveis em ambientes implantados com uma versão inicial anterior à 10.0.8. 

**Quais são os custos envolvidos na implantação do ambiente de avaliação do Commerce no Microsoft Azure via Microsoft Dynamics Lifecycle Services (LCS)?**

Um ambiente de demonstração de sede tradicional (máquina virtual \[VM\]) do Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce será hospedado na sua assinatura do Azure. Você pode usar a [Calculadora de preços do Azure](https://azure.microsoft.com/pricing/calculator/) para estimar esse custo.

Outros componentes, como o Commerce Scale Unit, o construtor de sites do Commerce e seu site do e-Commerce, estarão disponíveis como software como serviço (SaaS) e serão hospedados pela Microsoft.

**Quais regiões do Azure são atualmente compatíveis com o ambiente de avaliação do Commerce?**

O ambiente de avaliação do Commerce só pode ser implantado na América do Norte.

**Há um disco rígido virtual (VHD) baixado que tem a opção de máquina virtual (VM) OneBox completa?**

O Dynamics 365 Commerce e o Commerce Scale Unit são totalmente software como serviço (SaaS) e devem ser hospedados na nuvem.

**Por quanto tempo o ambiente de avaliação do Commerce pode ser usado?**

O ambiente de avaliação do Commerce tem um limite de tempo de 30 dias a partir da data em que componentes SaaS, como o Commerce Scale Unit, o construtor de sites do Commerce e seu site do e-Commerce, são provisionados.

**É possível estender o limite de tempo para meu ambiente de avaliação do Commerce?**

A extensão do limite de tempo é uma exceção à norma e é considerada caso a caso. Fale com o contato do seu parceiro Microsoft para obter ajuda.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do ambiente de avaliação do Dynamics 365 Commerce](cpe-overview.md)

[Provisionar um ambiente de avaliação do Dynamics 365 Commerce](provisioning-guide.md)

[Configurar um ambiente de avaliação do Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurar BOPIS em um ambiente de avaliação do Dynamics 365 Commerce](cpe-bopis.md)

[Configurar recursos opcionais para um ambiente de avaliação do Dynamics 365 Commerce](cpe-optional-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]