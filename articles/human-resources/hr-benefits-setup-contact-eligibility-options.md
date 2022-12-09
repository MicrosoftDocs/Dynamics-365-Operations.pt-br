---
title: Configurar opções de qualificação para contato pessoal
description: Este artigo explica como configurar opções de qualificação para contatos pessoais no Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/22/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e3e393002901f31c035a54bd8036ed20ecdf9e00
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2022
ms.locfileid: "9803874"
---
# <a name="configure-personal-contact-eligibility-options"></a>Configurar opções de qualificação para contato pessoal


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo explica como configurar os tipos de contato pessoal que podem ser usados em benefícios no Microsoft Dynamics 365 Human Resources. Os contatos pessoais são as pessoas que receberão cobertura dos seus planos (dependentes) ou que se beneficiarão dos seus planos (beneficiários). Normalmente, os dependentes são cônjuges ou filhos. Os beneficiários podem ser cônjuges, filhos, pessoas com as quais tem relações de confiança ou pais.

1. No espaço de trabalho **Gerenciamento de benefícios** em **Configuração**, selecione **Opções de qualificação para contato pessoal**.

2. Selecione **Novo**.

3. Especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **Opção de qualificação** | Um nome ou código exclusivo da opção de qualificação para identificar a opção de qualificação. |
   | **Descrição** | Uma breve descrição da opção de qualificação. |
   | **Código de qualificação do contato** | O código do sistema que melhor descreve a opção de qualificação pessoal. As opções são: <ul><li>Relacionamento</li><li>Estudante</li><li>Dependente excedente</li><li>Dependente incapaz maior de idade</li></ul> |
   | **Status** | O status da opção de qualificação. Se o status de uma opção de qualificação estiver definido como inativo, não será possível selecionar essa opção de qualificação de contato pessoal para contatos pessoais. |
   | **Relacionamento** | Especifica o relacionamento entre o contato pessoal e o funcionário. Esse campo estará ativo apenas se o código de qualificação do contato estiver definido como Relacionamento. |
   | **Classificar por vencimento** |Especifica a idade máxima de um contato pessoal qualificado para o plano de benefícios. Esse campo estará ativo apenas se você selecionar um relacionamento. Essa idade é comparada com a idade calculada do contato pessoal. A idade calculada é: (data de cobertura – data de nascimento do contato pessoal/365). Esse número é sempre um inteiro.
Para a opção de qualificação de contato **Pessoal dependente excedente**, a idade neste campo é a idade mínima. Por exemplo, se a idade for definida como 18 na opção **Dependente excedente**, os dependentes que estiverem marcados como dependentes excedentes, e que tiverem 18 ou mais, serão cobertos pela opção de qualificação.  |

4. Selecione **Salvar**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
